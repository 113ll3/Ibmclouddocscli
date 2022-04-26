---

copyright:
  years: 2021, 2022
lastupdated: "2022-04-26"

keywords: cli, command line, command-line, login, cli login, compute resource, token, iks, trusted profiles, cri, IBM Cloud

subcollection: cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:tip: .tip}
{:important: .important}
{:external: target="_blank" .external}
{:note: .note}

# Logging in with a Compute Resource Token
{: #cri-login}

You can use a trusted profile to set up fine-grained authorization for applications that are running in compute resources. As a result, you aren't required to create service IDs or API keys for the compute resources. The {{site.data.keyword.cloud_notm}} CLI supports logging in and authenticating to {{site.data.keyword.cloud_notm}} using a {{site.data.keyword.cloud_notm}} Kubernetes Service compute resource. For instructions about logging in as a Virtual Server Instance for VPC compute resource using the {{site.data.keyword.cloud_notm}} CLI, see [Logging in as a Virtual Server Instance Compute Resource Identity](/docs/cli?topic=cli-vsi-cri-login).
{: shortdesc}

For more information about managing trusted profiles and establishing trust with compute resources, see [Establishing trust with compute resources](/docs/account?topic=account-create-trusted-profile&interface=ui#create-profile-compute).

## Using the CLI to log in
{: #usingthecli_login}

To use the {{site.data.keyword.cloud_notm}} CLI Kubernetes Service compute resource login feature, you must give application pods that run in your {{site.data.keyword.cloud_notm}} Kubernetes Service cluster access to {{site.data.keyword.cloud_notm}} services. For more information, see [Authorizing pods in your cluster to {{site.data.keyword.cloud_notm}} services with IAM trusted profiles](/docs/containers?topic=containers-pod-iam-identity&interface=ui). For Red Hat OpenShift clusters, see [Authorizing pods in your OpenShift cluster to {{site.data.keyword.cloud_notm}} services with IAM trusted profiles](/docs/openshift?topic=openshift-pod-iam-identity&interface=ui).

### Using a Compute Resource Token to log in with the CLI
{: #tokenflag_login}

When you use the compute resource token option to log in with a service account projected token, you specify the compute resource token parameter to enter at login.

You can log in with a compute resource token with the CLI in any of the following ways:

* Call the Compute Resource token directly:
   1. Specify the `--cr-token` option with the `ibmcloud login` command, and provide the content of the compute resource token.
   2. Specify the `--profile` option with the `ibmcloud login` command, and provide the ID, name, or CRN of the IAM trusted profile that the cluster is linked to.

   ```text
   ibmcloud login --cr-token <token_string> --profile <profile_id_name_or_crn_string>
   ```
   {: codeblock}

* Call the Compute Resource token with the token file:
   1. Specify the `--cr-token` option with the `ibmcloud login` command, and provide the file path of a compute resource token file.
   2. Specify the `--profile` option with the `ibmcloud login` command, and provide the ID, name, or CRN of the IAM trusted profile that the cluster is linked to.

   ```text
   ibmcloud login --cr-token @token_file_name --profile <profile_id_name_or_crn_string>
   ```
   {: codeblock}
  
* Set the `IBMCLOUD_CR_TOKEN` environment variable. 
  
   Additionally, you can set the environment variable on your system. For example, set `IBMCLOUD_CR_TOKEN=token_string`, where `token_string` is the custom value of the compute resource token, or `IBMCLOUD_CR_TOKEN=@token_file_name`, where `@token_file_name` is the file path of a compute resource token file that contains the contents of the token. After the environment variable is set, you can simply specify `ibmcloud login --profile <profile_id_name_or_crn_string>` from the CLI.

* Set both `IBMCLOUD_CR_TOKEN` and `IBMCLOUD_CR_PROFILE` environment variables.
  
   Additionally, you can set both environment variables on your system. For example, `IBMCLOUD_CR_TOKEN=token_string`, where `token_string` is the custom value of the compute resource token, and `IBMCLOUD_CR_PROFILE=profile_id_name_or_crn_string`, where `profile_id_name_or_crn_string` is the ID, name, or CRN of the IAM trusted profile that the cluster is linked to. After both environment variables are set, you can simply specify `ibmcloud login` from the CLI.

The resulting login session is valid for 60 minutes.
{: note}
