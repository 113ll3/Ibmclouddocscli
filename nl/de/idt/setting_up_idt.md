---
copyright:

  years: 2018

lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# {{site.data.keyword.dev_cli_notm}} einrichten
{: #add-cli}

Die {{site.data.keyword.dev_cli_short}} ist eine Befehlszeilenmethode zum Erstellen, Entwickeln und Bereitstellen von Anwendungen für Entwickler, die über eine Befehlszeile End-to-End-Webanwendungen, -Mobilanwendungen und -Mikroserviceanwendungen entwickeln möchten.
{: shortdesc}

## Voraussetzungen
{: #prereq}

Registrieren Sie sich für [{{site.data.keyword.Bluemix_notm}}](https://www.bluemix.net). 

*  Wenn Sie mit Microsoft Windows&trade; arbeiten, müssen Sie Windows 10 oder höher verwenden. 

* Sie müssen den stabilen Kanal für Docker mit Version 1.13.1 oder höher verwenden. 

## Installieren
{: #installation}

Zum Installieren des Tools können Sie den entsprechenden Befehl ausführen, um unser Installationsprogramm aufzurufen. Dabei werden auch Abhängigkeiten installiert, z. B. IBM Cloud-CLI, Kubernetes, Helm und Docker. Führen Sie die folgenden Installationsschritte aus: 

**Mac und Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

Werten Sie aus, ob die Plug-in-Installation erfolgreich war, indem Sie den folgenden Befehl ausführen:   

```
bx dev
```
{: codeblock}

## Umgebung konfigurieren
{: #configure-environment}

1. Stellen Sie eine Verbindung zu einem API-Endpunkt in Ihrer [{{site.data.keyword.Bluemix_notm}}-Region](/docs/overview/cf.html#ov_intro_reg) her. Geben Sie beispielsweise den folgenden Befehl ein, um eine Verbindung mit der {{site.data.keyword.Bluemix_notm}}-Region 'Vereinigte Staaten (Süden)' herzustellen: 

	```
	bx api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Melden Sie sich bei {{site.data.keyword.Bluemix_notm}} mit Ihrer IBMid an. 

	```
	bx login
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
		bx login --apikey <value>
		```
		{: codeblock}

3. Legen Sie Ihre Organisation (ORG) und Ihren Bereich (SPACE) wie folgt fest: 

	```
	bx target -o <value> -s <value>
	```
	{: codeblock}

## Weitere Informationen
{: #learn}

Nachdem die {{site.data.keyword.dev_cli_short}} installiert wurde, können Sie lernen, wie Sie mit diesem leistungsfähigen Tool effektiver arbeiten können: 
- [Einführung in die IDT-CLI](index.html)
- [IDT -Befehle (bx dev)](commands.html)
- [Developer Tools für VS Code](vscode.html)
- [Developer Tools für Jetbrains-IDEs](jetbrains.html)

Sehen Sie sich die [Lernprogramme](/docs/apps/tutorials/tutorial_bff.html) an, die zeigen, wie Sie cloudnative Apps mithilfe der {{site.data.keyword.dev_cli_short}} erstellen. 

## Weitere Referenzen
{: #learn-more}

Die folgenden Ressourcen können bei der Entwicklung von cloudnativen Apps mit der IBM Developer Tools-CLI nützlich sein: 

- [IBM Cloud Developer Tools-Landing-Page](https://www.ibm.com/cloud/cli) - Hauptproduktseite für die IDT-CLI
- [IBM Developer Tools-Installationsprogramm](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - Öffentliches GitHub-Repository mit detaillierten Installationsanweisungen
- [IBM Cloud-App-Service](https://console.bluemix.net/developer/appservice) - IBM Cloud-Konsolenseite mit Begleitinformationen für die IDT-Tools zum Erstellen und Verwalten von cloudnativen Apps
- [IBM Cloud Tech's Slack - #developer-tools-Kanal](https://ibm-cloud-tech.slack.com) - Besprechungen von IDT-Tools, Fragen und Antworten, Ideenvorschläge usw. 
	- [Teamzugriff anfordern](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**Fokus auf die Sprache**

- [Node,js in IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blogs und Lernprogramme**

- [Deploying to IBM Cloud private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
