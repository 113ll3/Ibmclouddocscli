---



copyright:

  years: 2015, 2018
lastupdated: "2018-05-21"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# 下載並安裝 {{site.data.keyword.Bluemix_notm}} CLI
{: #download_install}

建議您使用[這裡](/docs/cli/index.html)所述的方法，安裝 {{site.data.keyword.Bluemix_notm}} CLI 及所有建議的相依關係。
{: tip}


您可以使用安裝程式或 Shell 下載並安裝 CLI。

## 使用安裝程式
{: #installer}

若要安裝 {{site.data.keyword.Bluemix_notm}} CLI，只需下載安裝程式：

|版本 |前次更新日期|下載| 
|---------|-----------|-----------|
|[0.6.7](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.7) | 2018-05-15 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/ppc64le/checksum) |
|[0.6.6](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.6) |2018-03-19 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win32/checksum) |
|[0.6.5](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.5) |2018-02-05 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win32/checksum) |
|[0.6.4](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.4) |2017-12-19 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win32/checksum) |
|[0.6.3](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.3) |2017-12-12 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win32/checksum) |
|[0.6.2](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.2) |2017-11-16 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win32/checksum) |
|[0.6.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.1) |2017-10-05 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win32/checksum) |
|[0.6.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.0) |2017-09-30 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win32/checksum) |
|[0.5.6](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.6) |2017-08-17 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win32/checksum) |
|[0.5.5](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.5) |2017-07-03 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win32/checksum) |
|[0.5.4](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.4) |2017-05-18 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win32/checksum) |
|[0.5.3](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.3) |2017-05-16 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win32/checksum) | 
|[0.5.2](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.2) |2017-04-10 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win32/checksum) | 
|[0.5.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.1) |2017-03-18 |[macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux64) / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux64/checksum) [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win32/checksum) | 

* 若為 MacOS 及 Windows，請執行安裝程式。 
* 若為 Linux，在下載安裝程式套件之後，解壓縮該套件，並使用 root 許可權來執行安裝 Script。

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## 從 Shell 安裝
{: #shell_install}


### MacOS

複製下列指令，並將其貼入 Mac OS 的終端機，然後予以執行：

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

複製下列指令，並將其貼入 Linux OS 的終端機，然後予以執行：

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

複製下列指令，並將其貼入 [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} 終端機主控台，然後予以執行：

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}
