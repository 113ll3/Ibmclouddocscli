---
copyright:

  years: 2018

lastupdated: "2018-10-31"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# {{site.data.keyword.dev_cli_notm}}-CLI einrichten
{: #add-cli}

Die {{site.data.keyword.dev_cli_short}}-CLI ist eine Befehlszeilenmethode zum Erstellen, Entwickeln und Bereitstellen von Anwendungen für Entwickler, die über eine Befehlszeile End-to-End-Webanwendungen, -Mobilanwendungen und -Mikroserviceanwendungen entwickeln möchten. Finden Sie einen schnellen Einstieg mit dem empfohlenen Toolset, indem Sie eines der folgenden Scripts ausführen.
{: shortdesc}

## Vorbereitende Schritte für {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Registrieren Sie sich für [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

*  Wenn Sie mit Microsoft Windows&trade; arbeiten, müssen Sie Windows 10 oder höher verwenden.

* Sie müssen den stabilen Kanal für Docker mit Version 1.13.1 oder höher verwenden.

## Vorgehensweise zur Installation von {{site.data.keyword.dev_cli_notm}}
{: #installation}

Zum Installieren des Toolsets können Sie den entsprechenden Befehl ausführen, um das Installationsprogramm zu starten. Es werden die folgenden empfohlenen Tools für die {{site.data.keyword.Bluemix_notm}}-Entwicklung installiert (falls noch nicht geschehen): `Homebrew` (nur Mac), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, {{site.data.keyword.Bluemix_notm}}-CLI, {{site.data.keyword.dev_cli_notm}}-Plug-in, Cloud Functions-Plug-in, Container Registry-Plug-in, Container Service-Plug-in und `sdk-gen`-Plug-in. Führen Sie die folgenden Installationsschritte aus:

**Mac und Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Hinweis: Öffnen Sie die Windows PowerShell, indem Sie mit der rechten Maustaste auf das PowerShell-Symbol klicken und die Option "Als Administrator ausführen" auswählen.

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

## Überprüfen der Installation
Führen Sie zum Überprüfen der Installation den Befehl `help` wie folgt aus:

```
ibmcloud dev help
```
{: codeblock}

Bei erfolgreicher Installation enthält die Ausgabe Verwendungsanweisungen, die aktuelle Version sowie eine Auflistung der unterstützten Befehle.

Der Abschnitt [Tools erneut installieren](/docs/troubleshoot/ts_createapps.html#appendix) enthält Informationen zum individuellen Installieren aller Abhängigkeiten.

## Umgebung konfigurieren
{: #configure-environment}

1. Stellen Sie eine Verbindung zu einem API-Endpunkt an Ihrem {{site.data.keyword.Bluemix_notm}}-Standort her. Geben Sie beispielsweise den folgenden Befehl ein, um eine Verbindung zum {{site.data.keyword.Bluemix_notm}}-Standort Dallas herzustellen:

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Melden Sie sich bei {{site.data.keyword.Bluemix_notm}} mit Ihrer IBMid an.

	```
	ibmcloud login
	```
	{: codeblock}

	**Hinweis:** Wenn Ihre Berechtigungsnachweise zurückgewiesen werden, verwenden Sie möglicherweise eine föderierte ID. Führen Sie die folgenden Schritte aus, um sich mithilfe einer föderierten ID zu authentifizieren.

	1. Melden Sie sich bei [{{site.data.keyword.iamshort}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.bluemix.net/iam/#/apikeys){: new_window} an.
	2. Wählen Sie **API-Schlüssel erstellen** aus.
		* Geben Sie einen Namen und eine Beschreibung für den API-Schlüssel ein.
	3. Laden Sie Ihren API-Schlüssel herunter.
	4. Öffnen Sie die Datei und kopieren Sie den Wert aus dem Feld `apiKey`.
	5. Melden Sie sich mithilfe des folgenden Befehls an.

		```
		ibmcloud login --apikey <wert>
		```
		{: codeblock}

3. Legen Sie Ihre Organisation (ORG) und Ihren Bereich (SPACE) wie folgt fest:

	```
	ibmcloud target -o <wert> -s <wert>
	```
	{: codeblock}

## Weitere Informationen
{: #learn}

Nachdem die {{site.data.keyword.dev_cli_short}}-CLI installiert wurde, können Sie lernen, wie Sie mit diesem leistungsfähigen Tool effektiv arbeiten:
- [Einführung in die IDT-CLI](index.html)
- [IDT-Befehle (ibmcloud dev)](commands.html)
- [Developer Tools für VS Code](vscode.html)
- [Developer Tools für JetBrains-IDEs](jetbrains.html)

Sehen Sie sich die [Lernprogramme](/docs/apps/tutorials/tutorial_bff.html) an, die zeigen, wie Sie cloudnative Apps erstellen, die die {{site.data.keyword.dev_cli_short}}-CLI verwenden.

## Weitere Referenzen
{: #learn-more}

Die folgenden Ressourcen können bei der Entwicklung von cloudnativen Apps mit der IBM Developer Tools-CLI nützlich sein:

- [IBM Cloud Developer Tools-Landing-Page](https://www.ibm.com/cloud/cli) - Hauptproduktseite für die IDT-CLI
- [IBM Developer Tools-Installationsprogramm](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - Öffentliches GitHub-Repository mit detaillierten Installationsanweisungen
- [IBM Cloud App Service](https://console.bluemix.net/developer/appservice) - IBM Cloud-Konsolenseite mit Begleitinformationen für die IDT-Tools zum Erstellen und Verwalten von cloudnativen Apps
- [Probleme auf GitHub melden](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [Slack für IBM Cloud Tech - Kanal für Entwicklertools (#developer-tools)](https://ibm-cloud-tech.slack.com) - Fordern Sie [hier](https://slack-invite-ibm-cloud-tech.mybluemix.net/) Zugriff für Ihr Team an.

**Fokus auf die Sprache**

- [Node.js in IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blogs und Lernprogramme**

- [Deploying to IBM Cloud Private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
