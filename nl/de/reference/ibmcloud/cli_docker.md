---

copyright:

  years: 2018
lastupdated: "2018-11-13"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} über einen Docker-Container verwenden

Mit dem {{site.data.keyword.dev_cli_notm}}-Docker-Container erhalten Sie die {{site.data.keyword.Bluemix}}-Befehlszeilenschnittstelle sowie die folgenden Tools:

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
{: #prereq}

Sie benötigen ein [{{site.data.keyword.Bluemix_notm}}-Konto](https://console.bluemix.net/){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link") und Sie müssen die neueste stabile Docker-Version installieren, bevor Sie die folgenden Schritte ausführen.

## Schritt 1.Extrahieren Sie das Docker-Image vom Docker-Hub.
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Schritt 2. Starten Sie den Docker-Container.
{: #step2}

Verwenden Sie den folgenden Befehl, um den {{site.data.keyword.dev_cli_notm}}-Docker-Container zu starten.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Schritt 3. Melden Sie sich an {{site.data.keyword.Bluemix_notm}} mit Ihrer IBMid an.
{: #step3}

```
ibmcloud login
```
{: codeblock}


Wenn Ihre Berechtigungsnachweise zurückgewiesen werden, verwenden Sie möglicherweise eine föderierte ID. Weitere Informationen finden Sie unter [Mit eingebundener ID anmelden](/docs/iam/login_fedid.html#federated_id).
{: tip}

Das {{site.data.keyword.dev_cli_notm}}-CLI-Plug-in verwendet zwei Container, um das Erstellen und Testen Ihrer Anwendung zu vereinfachen. Der erste ist der Container 'tools', der die erforderlichen Dienstprogramme zum Erstellen und Testen Ihrer Anwendung enthält. Die `Dockerfile` für diesen Container ist durch den Parameter [`dockerfile-tools`](/docs/cli/idt/commands.html#command-parameters) definiert. Sie können ihn als Entwicklungscontainer ansehen, denn er enthält die Tools, die üblicherweise für die Entwicklung einer bestimmten Laufzeit verwendet werden.

Der zweite Container ist der Container 'run', der die tatsächliche Ausführungsumgebung Ihrer App genau abbildet, sobald sie in der Cloud bereitgestellt wurde. Dieser Container weist ein Format auf, das beispielsweise für die Bereitstellung zur Verwendung in {{site.data.keyword.Bluemix_notm}} geeignet ist. In der Folge wird ein Eingangspunkt definiert, der Ihre Anwendung startet. Wenn Sie entscheiden, dass Ihre Anwendung über die {{site.data.keyword.dev_cli_notm}}-CLI ausgeführt werden soll, verwendet die Anwendung diesen Container. Die `Dockerfile` für diesen Container ist durch den Parameter [`dockerfile-run`](/docs/cli/idt/commands.html#run-parameters) definiert.

Jetzt können Sie {{site.data.keyword.dev_cli_notm}} zum Verwalten der {{site.data.keyword.Bluemix_notm}}-Ressourcen sowie zum Entwickeln und Bereitstellen der Anwendungen verwenden.
