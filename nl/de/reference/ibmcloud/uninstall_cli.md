---

copyright:
  years: 2019
lastupdated: "2019-04-26"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# Eigenständige {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle deinstallieren
{: #uninstall-ibmcloud-cli}

Führen Sie zur Deinstallation der eigenständigen {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle auf bestimmten Plattformen die folgenden Schritte aus:{: shortdesc}

## Deinstallation unter Windows
{: #uninstall-cli-windows}

1. Klicken Sie auf die Schaltfläche **Start** und wählen Sie dann die **Systemsteuerung** aus.
2. Klicken Sie im Popup-Fenster auf **Programme und Funktionen - Programm deinstallieren oder ändern**.
3. Suchen Sie in der Popup-Liste der Anwendungen die **IBM Cloud-Befehlszeilenschnittstelle**.
4. Klicken Sie mit der rechten Maustaste auf die **IBM Cloud-Befehlszeilenschnittstelle** und wählen Sie **Deinstallieren** aus.
5. Das Deinstallationsprogramm wird gestartet. Führen Sie die entsprechenden Anweisungen aus, um die Deinstallation fertigzustellen.

## Deinstallation unter Linux und MacOS
{: #uninstall-cli-linux-macos}

Die Deinstallationsschritte unterscheiden sich abhängig von der installierten Version der CLI.

Führen Sie folgende Schritte aus, um Ihre {{site.data.keyword.cloud_notm}}-CLI-Version zu ermitteln:
```
ibmcloud -v
```
{: codeblock}

Um Versionen vor Version `0.9.0` zu deinstallieren, führen Sie die folgenden Befehle aus: 
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

Bereinigen Sie die Scripts für automatische Vervollständigung, sofern Sie diese konfiguriert haben. Weitere Details finden Sie in [Automatische Vervollständigung für die Shell für die {{site.data.keyword.cloud_notm}}-CLI (nur Linux und Mac)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

Um die Version `0.9.0` und nachfolgende Versionen zu deinstallieren, führen Sie den folgenden Befehl aus: 
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

Bereinigen Sie alle angepassten Scripts für automatische Vervollständigung. Weitere Details finden Sie in [Automatische Vervollständigung für die Shell für die {{site.data.keyword.cloud_notm}}-CLI (nur Linux und Mac)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).
