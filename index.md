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

# {{site.data.keyword.dev_cli_notm}} Overview
{: #overview}

{{site.data.keyword.dev_cli_notm}} is a command line approach for creating, developing, and deploying applications for developers who want to use a command line to develop end-to-end web, mobile, and microservice applications. Quickly get started with the recommended toolset by running one of the following scripts.
{: shortdesc} 

## Prerequisites for {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Sign up for [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

* If you're using Microsoft Windows &trade;, you must use Windows 10 or later.

* You must use the stable channel for Docker, with a minimum version of 1.13.1.

## How to install {{site.data.keyword.dev_cli_notm}}
{: #installation}

To install the toolset, you can run the relevant command to start the installer. This installs the following recommended tools for {{site.data.keyword.Bluemix_notm}} development (if not already installed): `Homebrew` (Mac only), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, {{site.data.keyword.Bluemix_notm}} CLI, {{site.data.keyword.dev_cli_notm}} plug-in, Cloud Functions plug-in, Container Registry plug-in, Container Service plug-in, and `sdk-gen` plug-in.

**Mac and Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Note: Open Windows PowerShell by right-clicking and select "Run as Administrator".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}


## Other links to further explore {{site.data.keyword.dev_cli_notm}}

- [Detailed Setup](/docs/cli/idt/setting_up_idt.html)
- [Usage](/docs/cli/idt/index.html)
- [Commands](/docs/cli/idt/commands.html)
- [CLI Plug-ins](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [VSCode IDE Extension](/docs/cli/idt/vscode.html)
- [Install IBM Cloud CLI Manually](/docs/cli/reference/bluemix_cli/get_started.html)
