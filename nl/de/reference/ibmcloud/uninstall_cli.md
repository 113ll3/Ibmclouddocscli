---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle deinstallieren

Die folgenden Abschnitte enthalten Anweisungen zur Deinstallation von {{site.data.keyword.Bluemix_notm}} für bestimmte Plattformen.

## Deinstallation unter Windows

* Klicken Sie auf die Schaltfläche `Start` und wählen Sie dann die `Systemsteuerung` aus.
* Klicken Sie im Popup-Fenster auf `Programme und Funktionen - Programm deinstallieren oder ändern`.
* Suche Sie in der Pop-up-Liste der Anwendungen die `IBM Cloud-Befehlszeilenschnittstelle`.
* Klicken Sie mit der rechten Maustaste auf die `IBM Cloud-Befehlszeilenschnittstelle` und wählen Sie `Deinstallieren` aus.
* Das Deinstallationsprogramm wird gestartet. Führen Sie die entsprechenden Anweisungen aus, um die Deinstallation fertigzustellen.

## Deinstallation unter Linux/macOS

### Vor Version `0.9.0`

* Öffnen Sie ein Terminal und führen Sie die folgenden Befehle aus:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* Bereinigen Sie die Scripts für automatische Vervollständigung, falls diese konfiguriert sind. Weitere Details finden Sie in [Automatische Vervollständigung für die Befehlszeilenschnittstelle aktivieren](enable_cli_autocompletion.html).

### Ab Version `0.9.0`

* Öffnen Sie ein Terminal und führen Sie den folgenden Befehl aus:
  * `/usr/local/ibmcloud/uninstall`
* Bereinigen Sie die Scripts für automatische Vervollständigung, falls diese konfiguriert sind. Weitere Details finden Sie in [Automatische Vervollständigung für die Befehlszeilenschnittstelle aktivieren](enable_cli_autocompletion.html).
