---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-07"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# {{site.data.keyword.Bluemix_notm}}-CLI herunterladen und installieren
{: #download_install}

Wir empfehlen, die {{site.data.keyword.Bluemix_notm}}-CLI und alle empfohlenen Abhängigkeiten mithilfe der [hier](/docs/cli/index.html) beschriebenen Methode zu installieren.
{: tip}


Sie können die CLI mit einem Installationsprogramm oder über eine Shell herunterladen und installieren.

## Installationsprogramm verwenden
{: #installer}

Laden Sie einfach das Installationsprogramm herunter, um die {{site.data.keyword.Bluemix_notm}}-CLI zu installieren:

| Version |  Aktualisiert  | Downloads | 
|---------|-----------|-----------|
| [0.7.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.7.1) | 2018-06-07 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/ppc64le/checksum) |
| [0.7.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.7.0) | 2018-05-31 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/ppc64le/checksum) |
| [0.6.7](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.7) | 2018-05-15 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/ppc64le/checksum) |
| [0.6.6](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.6) | 2018-03-19 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win32/checksum) |
| [0.6.5](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.5) | 2018-02-05 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win32/checksum) |
| [0.6.4](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.4) | 2017-12-19 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win32/checksum) |
| [0.6.3](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.3) | 2017-12-12 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win32/checksum) |
| [0.6.2](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.2) | 2017-11-16 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win32/checksum) |
| [0.6.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.1) | 2017-10-05 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win32/checksum) |
| [0.6.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.0) | 2017-09-30 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win32/checksum) |
| [0.5.6](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.6) | 2017-08-17 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win32/checksum) |
| [0.5.5](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.5) | 2017-07-03 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win32/checksum) |
| [0.5.4](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.4) | 2017-05-18 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win32/checksum) |
| [0.5.3](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.3) | 2017-05-16 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win32/checksum) | 
| [0.5.2](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.2) | 2017-04-10 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win32/checksum) | 
| [0.5.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.1) | 2017-03-18 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux64) / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux64/checksum) [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win32/checksum) | 

* Für MacOS und Windows führen Sie das Installationsprogramm aus. 
* Für Linux müssen Sie nach dem Herunterladen des Pakets mit dem Installationsprogramm die Dateien aus diesem Paket extrahieren und das Installationsscript mit Rootberechtigung ausführen.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## Über Shell installieren
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
