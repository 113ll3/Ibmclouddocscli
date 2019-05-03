---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Häufig gestellte Fragen (FAQ)
{: #ibm-cli-faq}

## Wie ist die Dateistruktur für {{site.data.keyword.cloud_notm}}-Anwendungen?
{: #cli-file-structure}

Anwendungen, die über die CLI erstellt oder aktiviert werden, enthalten vorkonfigurierte Einstellungen, die in der Datei `cli-config.yml` zusammengefasst sind. Die Datei `cli-config.yml` enthält Standardeinträge, die von den Befehlen der CLI verwendet werden und durch an die Befehlszeile übergebene Werte überschrieben werden können.

Anwendungen, die in einer DevOps-Toolchain bereitgestellt wurden, können ebenfalls Dateien wie z. B. `toolchain.yml` und `pipeline.yml` enthalten. Anwendungen, die manuell bereitgestellt werden, können eine `manifest.yml`-Datei und Helm-Diagrammdateien enthalten (z. B. für die Bereitstellung in Cloud Foundry oder Kubernetes).

## Wie werden lokale Container verwendet?
{: #cli-faq-containers}

Das {{site.data.keyword.dev_cli_long}}-CLI-Plug-in verwendet zwei Container, um das Erstellen und Testen Ihrer Anwendung zu vereinfachen. Der erste ist der Container 'tools', der die erforderlichen Dienstprogramme zum Erstellen und Testen Ihrer Anwendung enthält. Die `Dockerfile` für diesen Container ist durch den Parameter [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) definiert. Sie können ihn als Entwicklungscontainer ansehen, denn er enthält die Tools, die üblicherweise für die Entwicklung einer bestimmten Laufzeit verwendet werden.

Der zweite Container ist der Ausführungscontainer, der die tatsächliche Laufzeitumgebung Ihrer App recht genau abbildet, nachdem diese in der Cloud bereitgestellt wurde. Dieser Container weist ein Format auf, das beispielsweise für die Bereitstellung zur Verwendung in {{site.data.keyword.cloud_notm}} geeignet ist. In der Folge wird ein Eingangspunkt definiert, der Ihre Anwendung startet. Wenn Sie entscheiden, dass Ihre Anwendung über die {{site.data.keyword.dev_cli_long}}-CLI ausgeführt werden soll, verwendet die Anwendung diesen Container. Die `Dockerfile` für diesen Container ist durch den Parameter [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) definiert.

# Wie implementiere ich vorhandenen Code?
Zur Implementierung einer vorhandenen Codebasis führen Sie die folgenden Schritte aus, um [App zu aktivieren](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

## Referenzblogs, Videos und Dokumentation
{: #cli-faq-reference}

### Blogs
{: #cli-blogs}

- [Bereitstellung in {{site.data.keyword.cloud_notm}} Private mit dem {{site.data.keyword.dev_cli_long}}-CLI-Plug-in](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [Bereitstellung in Kubernetes in {{site.data.keyword.cloud_notm}} mit dem {{site.data.keyword.dev_cli_long}}-CLI-Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Vorhandene Projekte für {{site.data.keyword.cloud_notm}} mit dem {{site.data.keyword.dev_cli_long}}-CLI-Plug-in aktivieren](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### Videos
{: #cli-videos}

- [Vorgehensweise zur Bereitstellung in Kubernetes in {{site.data.keyword.cloud_notm}} mit dem {{site.data.keyword.dev_cli_long}}-CLI-Plug-in](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [Vorgehensweise zur Bereitstellung vorhandener Projekte in {{site.data.keyword.cloud_notm}} mit dem {{site.data.keyword.dev_cli_long}}-CLI-Plug-in](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [Erstellen, Debuggen und Bereitstellen einer Node.js-App mit dem {{site.data.keyword.dev_cli_long}}-CLI-Plug-in und VSCode](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### Dokumentation und Lernprogramme
- [Kontinuierliche Bereitstellung in Kubernetes](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [Fehlerbehebung für das {{site.data.keyword.dev_cli_long}}-CLI-Plug-in](/docs/cli?topic=cloud-cli-troubleshoot)
- [{{site.data.keyword.dev_cli_long}}-CLI-Plug-in (ibmcloud dev) - Befehle](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [Lokales Anwendungsdebugging für das {{site.data.keyword.dev_cli_long}}-CLI-Plug-in](/docs/cli/idt?topic=cloud-cli-local-debug)

**Zur Meldung von Problemen oder um Feedback zu geben, können Sie den [{{site.data.keyword.cloud_notm}} Tech-Slack-Kanal für Entwicklertools](https://ibm-cloud-tech.slack.com) - Teamzugriff [hier anfordern](https://slack-invite-ibm-cloud-tech.mybluemix.net/) - nutzen.**
