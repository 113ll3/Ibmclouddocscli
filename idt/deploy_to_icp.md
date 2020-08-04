---

copyright:
  years: 2019, 2020
lastupdated: "2020-08-03"

keywords: cli, ibmcloud private, icp, ibmcloud dev deploy, containers, kubernetes, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cli

---


{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:external: target="_blank" .external}

# Deploying applications to {{site.data.keyword.cloud_notm}} Private
{: #deploy-to-icp}

[{{site.data.keyword.cloud}} Private](https://www.ibm.com/developerworks/community/groups/service/html/communityoverview?communityUuid=fe25b4ef-ea6a-4d86-a629-6f87ccf4649e){: external} is an application platform for developing and managing on-premises, containerized applications. It is an integrated environment for managing containers that includes the container orchestrator Kubernetes, a private image repository, a management console, and monitoring frameworks. {{site.data.keyword.dev_cli_notm}} supports deployments to {{site.data.keyword.cloud_notm}} Private environments.
{: shortdesc}

To install the {{site.data.keyword.dev_cli_notm}} commands, follow these [instructions](/docs/cli?topic=cli-install-devtools-manually). Once installed, ensure that the [Helm](https://www.ibm.com/cloud/blog/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli){: external} version is appropriate for the {{site.data.keyword.cloud_notm}} Private environment. To install Helm from the {{site.data.keyword.cloud_notm}} Private Management console for use with {{site.data.keyword.cloud_notm}} Private 3.2.0, follow these [instructions](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.2.0/app_center/create_helm_cli.html){: external}.

## Before you begin
{: #before-deploy-icp}

You need a new or existing app that is ready for {{site.data.keyword.cloud_notm}} deployment.

* Create an app by selecting a starter app to deploy by using the `ibmcloud dev create` command. Then, follow the prompts to select the pattern, language, and starter. Node.js or Java&trade; Basic web starters are recommended as they are simple and easy to follow, but feel free to choose any language or starter.
* Enable an existing application for Kubernetes deployments by using the [ibmcloud dev enable](https://www.ibm.com/blogs/cloud-archive/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: external} command.

## Configure kubectl and helm
{: #configure-helm}

Once the app is ready, configure `kubectl` and `helm` locally to deploy to the {{site.data.keyword.cloud_notm}} Private environment. For {{site.data.keyword.cloud_notm}} Private 3.2.0, follow these instructions to install [cloudctl](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.2.0/manage_cluster/install_cli.html){: external} then afterward, log in to configure `kubectl` and `helm`.

To log in with `cloudctl`, run:
```
cloudctl login -a https://<Cluster Master Host>:<Cluster Master API Port> --skip-ssl-validation
```
{: codeblock}

To verify that `kubectl` and `helm` are configured correctly, run the following command:
```
helm version --tls
```
{: codeblock}

If the command is successful, create an environment variable `HELM_TLS_ENABLE` that equals to `true` so that the `--tls` flag isn't required for each subsequent `helm` command execution.
{: tip}

## Configure Docker registry access
{: #configure-docker}

{{site.data.keyword.cloud_notm}} Private contains a Private Registry that can store container images. To configure the Docker CLI to use the {{site.data.keyword.cloud_notm}} Private registry, the hosts file must contain an entry that routes to the [Master endpoint](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.2.0/manage_cluster/cluster_endpoints.html#master){: external}. Follow these [instructions](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.2.0/manage_images/configuring_docker_cli.html){: external} to configure the docker cli for {{site.data.keyword.cloud_notm}} Private 3.2.0 and the hosts file.

## Configure the service account
{: #configure-service-account}

Next, configure the service account in the {{site.data.keyword.cloud_notm}} Private Kubernetes cluster with the image pull secret. This account enables Kubernetes to pull images from the {{site.data.keyword.cloud_notm}} Private registry. Two techniques are provided, in both cases:

 - The user for the secret must be a user that is associated with the namespace to which the application is to be deployed to.
 - Must be logged in to {{site.data.keyword.cloud_notm}} Private previously with this user.

The first technique is to edit the `serviceaccounts` directly with `kubectl edit serviceaccounts` and add or update the following section by substituting `<the user>` with the actual user name:

```
imagePullSecrets:
  - name: <the user>.registrykey
```
{: codeblock}

The second technique uses [`jq`](https://stedolan.github.io/jq/){: external}, which can be installed by using `brew` (Mac), `yum` (Red Hat Linux&trade;), or `apt` (Ubuntu Linux&trade;).

```
kubectl get serviceaccounts default -o json |
jq  'del(.metadata.resourceVersion)'|
jq 'setpath(["imagePullSecrets"];[{"name":"admin.registrykey"}])' |
kubectl replace serviceaccount default -f -
```
{: codeblock}

Where “admin” is the user account that is associated with the namespace to which the app is to be deployed, and is logged in to {{site.data.keyword.cloud_notm}} Private previously. Upon completion of `jq`, an entry for the `serviceaccount` is noted as “replaced.”

## Deploy an app
{: #idt-deploy}

For the simplest deployment experience, update the application’s `cli-config.yml` file to point to the {{site.data.keyword.cloud_notm}} Private Kubernetes environment by adding these entries:

```yaml
deploy-target: "container"
deploy-image-target: "mycluster.icp:8500/<Namespace>/<App-Name>"
```
{: codeblock}

The `<Namespace>` is the namespace on {{site.data.keyword.cloud_notm}} Private to which it is to be deployed, for example `default`. The `<App-Name>` is the name of the app project.

The `deploy-target` value instructs the CLI to target a Kubernetes or container environment, and the `deploy-image-target` value tells the CLI what to tag the image with for the {{site.data.keyword.cloud_notm}} Private registry. If the `cli-config.yml` file is not updated, specify `-t container` for the `ibmcloud dev deploy` command, and then the deployment action prompts for the `deploy-image-target`.

For public {{site.data.keyword.cloud_notm}} users, run `ibmcloud logout` before you deploy to {{site.data.keyword.cloud_notm}} Private.
{: tip}

```
ibmcloud dev deploy -t container
```
{: codeblock}

In this case, the `deploy` command will:

 - Build and upload the Docker image of the application to the {{site.data.keyword.cloud_notm}} Private image repository.

 - Perform a deployment to the {{site.data.keyword.cloud_notm}} Private Kubernetes cluster by using the Helm chart that was generated with the `ibmcloud dev create` or `ibmcloud dev enable` command.

The application is now deployed to {{site.data.keyword.cloud_notm}} Private using the {{site.data.keyword.dev_cli_notm}} commands.

### Reference blogs and videos
{: #idt-deploy-reference}

- Blog: [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.dev_cli_notm}} commands](https://www.ibm.com/cloud/blog/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli){: external}

For more information, see the full `ibmcloud dev` [command reference](/docs/cli?topic=cli-idt-cli).
