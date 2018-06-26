---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-26"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Installing and using {{site.data.keyword.Bluemix_notm}} CLI
{: #download_install}

{{site.data.keyword.Bluemix_notm}} CLI provides the command line interface to manage applications, containers, infrastructures, services and other resources in {{site.data.keyword.Bluemix_notm}}.

If you want to install both the {{site.data.keyword.Bluemix}} CLI and other recommended plugins and tools for developing applications for {{site.data.keyword.Bluemix_notm}}, follow the method described [here](/docs/cli/index.html).
{: tip}


## Getting started with {{site.data.keyword.Bluemix_notm}} CLI
{: #getting_started}

1. Select the installer of your OS to download

   Mac OS X 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64-bit (ppc64le): [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **32 bit releases and previous versions can be found [here](all_versions.html)

1. Run the installer
   * For macOS and windows, just run the installer.
   * For Linux, extract the package and run `install_bluemix_cli` script

1. Target an API endpoint and login to {{site.data.keyword.Bluemix_notm}}

  ![Example](example.gif){: gif}

Now you are ready to manage {{site.data.keyword.Bluemix_notm}} resouces. Type `ibmcloud help` to see the command descriptions.

If you are using a federated ID, follow the instructions [here](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) to log in with a one-time passcode or an API key.  
{: tip}

## Other links to further explore {{site.data.keyword.Bluemix_notm}} CLI

* [Extend {{site.data.keyword.Bluemix_notm}} CLI capabilities with plugins](extend_cli.html)
* [Document of {{site.data.keyword.Bluemix_notm}} CLI commands usage](ic_cli_cmds.html)


## Report issues and submit feedback
{: #issues}

Use the following options to report issues or submit new feature requests:
 * Create issues in [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![External link icon](../../../icons/launch-glyph.svg)
 * Leave messages in [Slack channel](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![External link icon](../../../icons/launch-glyph.svg)
