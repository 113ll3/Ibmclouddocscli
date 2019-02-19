---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-14"

---

{:shortdesc: .shortdesc}
{:gif: data-image-type='gif'}
{:new_window: target="_blank"}
{:tip: .tip}

# Getting started with {{site.data.keyword.cloud_notm}} CLI
{: #getting-started}

It's recommended that you install the {{site.data.keyword.cloud_notm}} CLI and all recommended dependencies by using the method that's described [here.](/docs/cli/index.html#ibmcloud-cli)
{: tip}

{{site.data.keyword.cloud_notm}} CLI provides the command line interface to manage applications, containers, infrastructures, services, and other resources in {{site.data.keyword.cloud_notm}}.

To get started with just the {{site.data.keyword.cloud_notm}} CLI:

1. Select the installer of your OS to download:
   Mac OS X 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64-bit (ppc64le): [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **32-bit releases and previous versions can be found [here](/docs/cli/reference/ibmcloud/all_versions.html#cli-releases)

2. Run the installer
   * For macOS and windows, run the installer.
   * For Linux, extract the package and run `install_bluemix_cli` script

3. Target an API endpoint and login to {{site.data.keyword.cloud_notm}}

  ![Example](example.gif){: gif}

Now you're ready to manage {{site.data.keyword.Bluemix_notm}} resouces. Type `ibmcloud help` to see the command descriptions.

If you're using a federated ID, follow the instructions [here](/docs/iam/login_fedid.html#federated_id) to log in with a one-time passcode or an API key.
{: tip}

## Other links to further explore {{site.data.keyword.cloud_notm}} CLI

* [More options to download and install {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud/download_cli.html#install-ibmcloud-cli)
* [Extend {{site.data.keyword.cloud_notm}} CLI capabilities with plug-ins](/docs/cli/reference/ibmcloud/extend_cli.html#plug-ins)
* [All versions of {{site.data.keyword.cloud_notm}} CLI and release notes](/docs/cli/reference/ibmcloud/all_versions.html#cli-releases)
* [Document of {{site.data.keyword.cloud_notm}} CLI commands usage](/docs/cli/reference/ibmcloud/bx_cli.html#ibmcloud_cli)


## Report issues and submit feedback
{: #issues}

Use the following options to report issues or submit new feature requests:
 * Create issues in [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![External link icon](../../../icons/launch-glyph.svg)
 * Leave messages in [Slack channel](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![External link icon](../../../icons/launch-glyph.svg)
