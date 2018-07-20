---

copyright:

  years: 2015, 2018

lastupdated: "2018-07-05"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Einführung in die {{site.data.keyword.Bluemix_notm}}-CLI
{: #overview}

In diesem Lernprogramm installieren Sie eine Reihe von {{site.data.keyword.Bluemix}}-Entwicklertools, überprüfen die Installation und konfigurieren Ihre Umgebung. {{site.data.keyword.Bluemix}}-Entwicklertools bieten eine Befehlszeilenmethode zum Erstellen, Entwickeln und Bereitstellen von End-to-End-Webanwendungen, -Mobilanwendungen und -Mikroserviceanwendungen 
{:shortdesc}

Mit dieser Installation rufen Sie die {{site.data.keyword.Bluemix_notm}}-CLI sowie folgende Tools ab: 

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

Sie benötigen ein [{{site.data.keyword.Bluemix_notm}}-Konto](https://console.bluemix.net/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") und die folgenden Systemvoraussetzungen:

* Wenn Sie mit Microsoft Windows&trade; arbeiten, müssen Sie Windows 10 oder höher verwenden.
* Sie müssen den stabilen Kanal für Docker mit Version 1.13.1 oder höher verwenden.

## Schritt 1: Installationsbefehl ausführen
{: #step1}

* Führen Sie unter Mac und Linux den folgenden Befehl aus:

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}
<br>

* Führen Sie unter Windows 10 den folgenden Befehl als Administrator aus:

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}
<br>

  Klicken Sie mit der rechten Maustaste auf das Symbol für Windows PowerShell und wählen Sie **Als Administrator ausführen** aus.
  {: tip}

## Schritt 2: Installation verifizieren
{: #step2}

Führen Sie den Befehl `help` aus, um zu überprüfen, dass die CLI und die Entwicklertools erfolgreich installiert wurden:

```
ibmcloud dev help
```
{: codeblock}
<br>
Die Ausgabe listet die Verwendungsanweisungen, die aktuelle Version und die unterstützten Befehle auf.

## Schritt 3: Ihre Umgebung konfigurieren
{: #step3}

1. Stellen Sie eine Verbindung zu einem API-Endpunkt in Ihrer {{site.data.keyword.Bluemix_notm}}-Region her. Geben Sie beispielsweise den folgenden Befehl ein, um eine Verbindung mit der {{site.data.keyword.Bluemix_notm}}-Region 'Vereinigte Staaten (Süden)' herzustellen:

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Melden Sie sich bei {{site.data.keyword.Bluemix_notm}} mit Ihrer IBMid an.

	```
	ibmcloud login
	```
	{: codeblock}
<br>

	Wenn Ihre Berechtigungsnachweise zurückgewiesen werden, verwenden Sie möglicherweise eine föderierte ID. Weitere Informationen finden Sie unter [Mit eingebundener ID anmelden](/docs/iam/login_fedid.html#using-an-api-key).
	{: tip}

3. Legen Sie Ihre Organisation (org) und Ihren Bereich (space) fest.

	```
	ibmcloud target -o <wert> -s <wert>
	```
	{: codeblock}

## Nächste Schritte
{: #next-steps}

Sie können jetzt Ihre erste App entwickeln und bereitstellen. Weitere Informationen finden Sie unter [Apps entwickeln und bereitstellen](/docs/cli/idt/index.html).
