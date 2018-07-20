---



copyright:

  years: 2015, 2018
lastupdated: "2018-07-09"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Eigenständige {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle installieren
{: #install_use}

Die {{site.data.keyword.Bluemix_notm}}-CLI stellt die Befehlszeilenschnittstelle zum Verwalten von Anwendungen, Containern, Infrastrukturen, Services und anderen Ressourcen in {{site.data.keyword.Bluemix_notm}} zur Verfügung.

Wenn Sie sowohl die {{site.data.keyword.Bluemix}}-CLI als auch andere empfohlene Plug-ins und Tools für die Anwendungsentwicklung für {{site.data.keyword.Bluemix_notm}} installieren möchten, verwenden Sie die [hier](/docs/cli/index.html) beschriebene Methode.
{: tip}

Führen Sie zum Einrichten der eigenständigen {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle die folgenden Schritte aus:

1. Wählen Sie das Installationsprogramm für Ihr Betriebssystem zum Herunterladen aus.

   Mac OS X 64 Bit: [Installationsprogramm](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 Bit: [Installationsprogramm](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 Bit: [Installationsprogramm](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 Bit (ppc64le): [Installationsprogramm](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **32-Bit-Releases und Vorgängerversionen finden Sie [hier.](all_versions.html)

1. Führen Sie das Installationsprogramm aus.
   * Für Mac OS und Windows führen Sie einfach das Installationsprogramm aus.
   * Für Linux müssen Sie das Paket extrahieren und das Script `install_bluemix_cli` ausführen.

1. Wählen Sie einen API-Endpunkt als Ziel aus und melden Sie sich bei {{site.data.keyword.Bluemix_notm}} an.

  ![Beispiel](example.gif){: gif}

Jetzt können Sie {{site.data.keyword.Bluemix_notm}}-Ressourcen verwalten. Geben Sie `ibmcloud help` ein, damit Beschreibungen der einzelnen Befehle angezeigt werden.

Wenn Sie eine föderierte ID verwenden, folgen Sie den [hier](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) angegebenen Anweisungen zur Anmeldung mit einem einmaligen Kenncode oder einem API-Schlüssel.  
{: tip}

## Weitere Optionen zum Installieren der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle
{: #more_options_install}


Neben dem [Installationsprogramm](install_use_cli.html#getting_started) können Sie auch die Shell zum Herunterladen und Installieren der Befehlszeilenschnittstelle verwenden. 


### Über die Shell installieren
{: #shell_install}


### MacOS

Kopieren Sie den folgenden Befehl und fügen Sie ihn auf einem Terminal Ihres Mac OS ein und führen Sie ihn aus:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Kopieren Sie den folgenden Befehl und fügen Sie ihn auf einem Terminal Ihres Linux-Betriebssystems ein und führen Sie ihn aus:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Kopieren Sie den folgenden Befehl und fügen Sie ihn in eine [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window}-Terminalkonsole ein und führen Sie ihn aus:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## Links mit weiterführenden Informationen zur {{site.data.keyword.Bluemix_notm}}-CLI

* [{{site.data.keyword.Bluemix_notm}}-CLI-Funktionen mit Plug-ins erweitern](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [Allgemeine Syntax der {{site.data.keyword.Bluemix_notm}}-CLI-Befehle](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [Allgemeine Syntax der {{site.data.keyword.Bluemix_notm}}-Befehle (ibmcloud sl)](/docs/cli/reference/softlayer/index.html)


## Probleme melden und Feedback abgeben
{: #issues}

Verwenden Sie die folgenden Optionen, um Probleme zu melden oder Anforderungen für neue Features abzuschicken:
 * Erstellen Sie Problemmeldungen in [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg)
 * Hinterlassen Sie Nachrichten im [Slack-Kanal](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg)
