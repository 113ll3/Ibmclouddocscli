---



copyright:

  years: 2015, 2019
lastupdated: "2019-01-03"

---


{:shortdesc: .shortdesc}
{:gif: data-image-type='gif'}
{:new_window: target="_blank"}
{:tip: .tip}



# 開始使用 {{site.data.keyword.Bluemix_notm}} CLI
{: #getting-started}

建議您使用[這裡](/docs/cli/index.html)所述的方法，安裝 {{site.data.keyword.Bluemix_notm}} CLI 及所有建議的相依關係。
{: tip}


{{site.data.keyword.Bluemix_notm}} CLI 提供指令行介面，來管理應用程式、容器、基礎架構、服務及 {{site.data.keyword.Bluemix_notm}} 中的其他資源。


若要開始使用 {{site.data.keyword.Bluemix_notm}} CLI，請執行下列動作：

1. 選取要下載的 OS 安裝程式

   Mac OS X 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 位元 (ppc64le)：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **在[這裡](/docs/cli/reference/ibmcloud/all_versions.html)可以找到 32 位元版次及舊版本

1. 執行安裝程式
   * 若為 macOS 及 Windows，執行安裝程式。
   * 若為 Linux，擷取套件並執行 `install_bluemix_cli` Script。

1. 將目標設為 API 端點並登入 {{site.data.keyword.Bluemix_notm}}

  ![範例](example.gif){: gif}

現在，您已準備好管理 {{site.data.keyword.Bluemix_notm}} 資源。鍵入 `ibmcloud help` 以查看指令說明。

如果您使用聯合 ID，請遵循[這裡](/docs/iam/login_fedid.html#federated_id)的指示，使用一次性密碼或 API 金鑰進行登入。
{: tip}

## 可進一步探索 {{site.data.keyword.Bluemix_notm}} CLI 的其他鏈結

* [下載並安裝 {{site.data.keyword.Bluemix_notm}} CLI 的其他選項](/docs/cli/reference/ibmcloud/download_cli.html)
* [使用外掛程式延伸 {{site.data.keyword.Bluemix_notm}} CLI 功能](/docs/cli/reference/ibmcloud/extend_cli.html)
* [所有 {{site.data.keyword.Bluemix_notm}} CLI 版本及版本注意事項](/docs/cli/reference/ibmcloud/all_versions.html)
* [{{site.data.keyword.Bluemix_notm}} CLI 指令用法的文件](/docs/cli/reference/ibmcloud/bx_cli.html)


## 報告問題及提交意見
{: #issues}

使用下列選項，以報告問題或提交新的特性要求：
 * 在 [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg) 中建立問題
 * 在 [Slack 頻道](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg) 中留言
