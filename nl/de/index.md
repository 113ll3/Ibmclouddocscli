---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Einführung in die {{site.data.keyword.cloud_notm}}-CLI
{: #overview}

In diesem Lernprogramm installieren Sie eine Reihe von {{site.data.keyword.cloud}}-Entwicklertools, überprüfen die Installation und konfigurieren die Umgebung. {{site.data.keyword.cloud_notm}}-Entwicklertools bieten eine Befehlszeilenmethode zum Erstellen, Entwickeln und Bereitstellen von Webanwendungen, Mobilanwendungen und Mikroserviceanwendungen.
{: shortdesc}

Mit dieser Installation rufen Sie die eigenständige {{site.data.keyword.cloud_notm}}-CLI sowie folgende Tools ab:

* `Homebrew` (nur Mac)
* `Git`
* `Docker`
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

Sie benötigen ein [{{site.data.keyword.cloud_notm}}-Konto](https://console.bluemix.net/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") und die folgenden Systemvoraussetzungen:

* Unter Windows werden einige Funktionen nicht unterstützt, wenn Sie nicht mit Windows 10 Pro arbeiten.
* Sie müssen den stabilen Kanal für Docker mit Version 1.13.1 oder höher verwenden.

## Schritt 1. Installationsbefehl ausführen
{: #step1}

* Führen Sie unter Mac und Linux den folgenden Befehl aus:

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Für Windows 10 Pro den folgenden Befehl als Administrator ausführen:

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Klicken Sie mit der rechten Maustaste auf das Symbol für Windows PowerShell und wählen Sie **Als Administrator ausführen** aus.
  {: tip}

  Das Installationsscript kann auch aus dem [GitHub-Repository](https://github.com/IBM-Cloud/ibm-cloud-developer-tools) heruntergeladen werden.

  Die Schritte zur manuellen Installation dieser Tools sind im Abschnitt [Tools erneut installieren](/docs/cli/ts_createapps.html#appendix) beschrieben.

## Schritt 2. Installation verifizieren
{: #step2}

Führen Sie den Befehl `help` aus, um zu überprüfen, dass die CLI und die Entwicklertools erfolgreich installiert wurden:

```
ibmcloud dev help
```
{: codeblock}
<br>
Die Ausgabe listet die Verwendungsanweisungen, die aktuelle Version und die unterstützten Befehle auf.

## Schritt 3. Umgebung konfigurieren
{: #step3}

1. Stellen Sie eine Verbindung zu einem API-Endpunkt an Ihrem {{site.data.keyword.cloud_notm}}-Standort her. Geben Sie beispielsweise den folgenden Befehl ein, um eine Verbindung zum {{site.data.keyword.cloud_notm}}-Standort Dallas herzustellen:

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Melden Sie sich bei {{site.data.keyword.cloud_notm}} mit Ihrer IBMid an.

	```
	ibmcloud login
	```
	{: codeblock}
    <br>

	Wenn Ihre Berechtigungsnachweise zurückgewiesen werden, verwenden Sie möglicherweise eine föderierte ID. Weitere Informationen finden Sie unter [Mit föderierter ID anmelden](/docs/iam/login_fedid.html#federated_id).
	{: tip}

3. Legen Sie Ihre Organisation (org) und Ihren Bereich (space) fest.

	```
	ibmcloud target --cf
	```
	{: codeblock}

	Optional können Sie die Ausgabe des vorigen Befehls verwenden, um Ihre Organisation und Ihren Bereich manuell mit dem folgenden Befehl festzulegen:

	```
	ibmcloud target -o <wert> -s <wert>
	```
	{: codeblock}

## Nächste Schritte
{: #next-steps}

Sie sind jetzt bereit, Ihre erste Anwendung zu entwickeln und bereitzustellen! Weitere Informationen finden Sie unter [Apps über die Befehlszeilenschnittstelle erstellen und bereitstellen](/docs/apps/create-deploy-cli.html).
