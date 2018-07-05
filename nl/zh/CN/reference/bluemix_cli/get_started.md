---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-21"

---


{:shortdesc: .shortdesc}
{:gif: data-image-type='gif'}
{:new_window: target="_blank"}
{:tip: .tip}



# {{site.data.keyword.Bluemix_notm}} CLI 入门
{: #getting-started}

建议您使用[此处](/docs/cli/index.html)描述的方法来安装 {{site.data.keyword.Bluemix_notm}} CLI 和所有建议的依赖项。
{: tip}


{{site.data.keyword.Bluemix_notm}} CLI 提供了用于管理 {{site.data.keyword.Bluemix_notm}} 中应用程序、容器、基础架构、服务和其他资源的命令行界面。


要仅开始使用 {{site.data.keyword.Bluemix_notm}} CLI，请执行以下操作：

1. 选择要下载的适用于您操作系统的安装程序

   Mac OS X 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 位 (ppc64le)：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window}<br>

   **32 位发行版及先前版本可以在[此处](all_versions.html)找到

1. 运行安装程序
   * 对于 macOS 和 Windows，请运行安装程序。
   * 对于 Linux，请解压缩程序包，并运行 `install_bluemix_cli` 脚本

1. 将 API 端点定为目标并登录到 {{site.data.keyword.Bluemix_notm}}

  ![示例](example.gif){: gif}

现在，您可以随时管理 {{site.data.keyword.Bluemix_notm}} 资源。输入 `ibmcloud help` 以查看命令描述。

如果要使用联合标识，请遵循[此处](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id)的指示信息，以使用一次性密码或 API 密钥进行登录。
{: tip}

## 用于进一步探索 {{site.data.keyword.Bluemix_notm}} CLI 的其他链接

* [用于下载和安装 {{site.data.keyword.Bluemix_notm}} CLI 的更多选项](download_cli.html)
* [使用插件扩展 {{site.data.keyword.Bluemix_notm}} CLI 功能](extend_cli.html)
* [所有版本的 {{site.data.keyword.Bluemix_notm}} CLI 和发行说明](all_versions.html)
* [{{site.data.keyword.Bluemix_notm}} CLI 命令用法文档](bx_cli.html)


## 报告问题并提交反馈
{: #issues}

使用以下选项来报告问题或提交新的功能请求：
 * 在 [GitHub ](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window}![外部链接图标](../../../icons/launch-glyph.svg) 中创建问题
 * 在 [Slack 通道 ](https://dwopen.slack.com/messages/bluemix-cli/){: new_window}![外部链接图标](../../../icons/launch-glyph.svg) 中留言
