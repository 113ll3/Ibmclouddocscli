---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, docker, docker container, ibmcloud docker, docker run, docker pull, ibmcloud cli, dockerfile, ibmcloud login

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} über einen Docker-Container verwenden
{: #using-idt-from-docker}

Mit dem {{site.data.keyword.dev_cli_notm}}-Docker-Container erhalten Sie die {{site.data.keyword.cloud}}-Befehlszeilenschnittstelle sowie die folgenden Tools:

* `Git`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}}-Plug-in
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}-Plug-in
* {{site.data.keyword.registrylong_notm}}-Plug-in
* {{site.data.keyword.containerlong_notm}}-Plug-in
* `sdk-gen`-Plug-in

## Vorbereitende Schritte
{: #idt-docker-prereq}

Sie benötigen ein [{{site.data.keyword.cloud_notm}}-Konto](https://{DomainName}/login){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") und Sie müssen die neueste stabile Docker-Version installieren, bevor Sie die folgenden Schritte ausführen.

## Schritt 1.Extrahieren Sie das Docker-Image vom Docker-Hub.
{: #step1-pull-docker-image}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Schritt 2. Starten Sie den Docker-Container.
{: #step2-start-docker}

Verwenden Sie den folgenden Befehl, um den {{site.data.keyword.dev_cli_notm}}-Docker-Container zu starten.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Schritt 3. Melden Sie sich an {{site.data.keyword.cloud_notm}} mit Ihrer IBMid an.
{: #step3-ibmcloud-login}

```
ibmcloud login
```
{: codeblock}

Wenn Ihre Berechtigungsnachweise zurückgewiesen werden, verwenden Sie möglicherweise eine föderierte ID. Weitere Informationen finden Sie unter [Mit föderierter ID anmelden](/docs/iam?topic=iam-federated_id#federated_id).
{: tip}

Das CLI-Plug-in von {{site.data.keyword.dev_cli_notm}} verwendet zwei Container, um das Erstellen und Testen Ihrer Anwendung zu vereinfachen. Der erste ist der Container 'tools', der die erforderlichen Dienstprogramme zum Erstellen und Testen Ihrer App enthält. Die `Dockerfile` für diesen Container ist durch den Parameter [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) definiert. Sie können ihn als Entwicklungscontainer ansehen, denn er enthält die Tools, die üblicherweise für die Entwicklung einer bestimmten Laufzeit verwendet werden.

Der zweite Container 'run' bildet die tatsächliche Laufzeitumgebung Ihrer App ab, sobald sie in der Cloud bereitgestellt ist. Dieser Container weist ein Format auf, das beispielsweise für die Bereitstellung zur Verwendung in {{site.data.keyword.cloud_notm}} geeignet ist. In der Folge wird ein Eingangspunkt definiert, der Ihre App startet. Wenn Ihre App über das {{site.data.keyword.dev_cli_notm}}-CLI-Plug-in ausgeführt werden soll, verwendet die App diesen Container. Die `Dockerfile` für diesen Container ist durch den Parameter [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) definiert.

Jetzt können Sie {{site.data.keyword.dev_cli_notm}} verwenden, um {{site.data.keyword.cloud_notm}}-Ressourcen zu verwalten und Ihre Apps zu entwickeln und bereitzustellen.
