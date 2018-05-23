---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-14"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} Übersicht
{: #overview}

{{site.data.keyword.dev_cli_notm}} ist eine Befehlszeilenmethode zum Erstellen, Entwickeln und Bereitstellen von Anwendungen für Entwickler, die über eine Befehlszeile End-to-End-Webanwendungen, -Mobilanwendungen und -Mikroserviceanwendungen entwickeln möchten.
Finden Sie einen schnellen Einstieg mit dem empfohlenen Toolset, indem Sie eines der folgenden Scripts ausführen.
{: shortdesc} 

## Voraussetzungen für {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Registrieren Sie sich für [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

* Wenn Sie mit Microsoft Windows&trade; arbeiten, müssen Sie Windows 10 oder höher verwenden.

* Sie müssen den stabilen Kanal für Docker mit Version 1.13.1 oder höher verwenden.

## Vorgehensweise zur Installation von {{site.data.keyword.dev_cli_notm}}
{: #installation}

Zum Installieren des Toolsets können Sie den entsprechenden Befehl ausführen, um das Installationsprogramm zu starten. Es werden die folgenden empfohlenen Tools für die {{site.data.keyword.Bluemix_notm}}-Entwicklung installiert (falls noch nicht geschehen): `Homebrew` (nur Mac), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, {{site.data.keyword.Bluemix_notm}}-CLI, {{site.data.keyword.dev_cli_notm}}-Plug-in, Cloud Functions-Plug-in, Container Registry-Plug-in, Container Service-Plug-in und `sdk-gen`-Plug-in. 

**Mac und Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Hinweis: Öffnen Sie die Windows PowerShell, indem Sie mit der rechten Maustaste klicken und die Option "Als Administrator ausführen" auswählen.

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}


## Links mit weiterführenden Informationen zur {{site.data.keyword.dev_cli_notm}}

- [Konfiguration im Detail](/docs/cli/idt/setting_up_idt.html)
- [Verwendung](/docs/cli/idt/index.html)
- [Befehle](/docs/cli/idt/commands.html)
- [CLI-Plug-ins](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [VSCode-IDE-Erweiterung](/docs/cli/idt/vscode.html)
- [IBM Cloud-CLI manuell installieren](/docs/cli/reference/bluemix_cli/get_started.html)
