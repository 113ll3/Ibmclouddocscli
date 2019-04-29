---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# 常見問題 (FAQ)
{: #ibm-cli-faq}

## {{site.data.keyword.cloud_notm}} 應用程式的檔案結構為何？
{: #cli-file-structure}

從 CLI 建立或啟用的應用程式，會隨附 `cli-config.yml` 檔中所封裝的預先配置設定。`cli-config.yml` 包含 CLI 的指令所使用的預設項目，其可置換為透過指令行所傳遞的值。

已部署至 DevOps 工具鏈的應用程式也可能包含 `toolchain.yml` 和 `pipeline.yml` 之類的檔案。手動部署的應用程式可以包含 `manifest.yml` 及 Helm 圖表檔案（比方說，用於部署至 Cloud Foundry 或 Kubernetes）。

## 如何使用本端容器？
{: #cli-faq-containers}

{{site.data.keyword.dev_cli_long}} CLI 外掛程式使用兩個容器來協助建置及測試應用程式。第一個是 tools 容器，其中包含用來建置及測試應用程式的必要公用程式。此容器的 `Dockerfile` 是透過 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 參數所定義。您可能會將它視為一個開發容器，因為它包含一般用於開發特定運行環境的工具。

第二個容器是 run 容器，一旦您的應用程式部署至雲端，該容器便會緊密模擬您應用程式的實際運行環境。此容器為適合部署以供在例如 {{site.data.keyword.cloud_notm}} 中使用的形式。因此，定義的進入點可啟動您的應用程式。當您選擇透過 {{site.data.keyword.dev_cli_long}} 執行應用程式時，它會使用此容器。此容器的 `Dockerfile` 是透過 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) 參數所定義。

# 如何部署現有的程式碼？
若要部署現有的程式碼庫，請遵循下列步驟來啟用應用程式：[啟用應用程式](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli)。

## 參考部落格、影片及文件
{: #cli-faq-reference}

### 部落格
{: #cli-blogs}

- [使用 {{site.data.keyword.dev_cli_long}} CLI 外掛程式部署至 {{site.data.keyword.cloud_notm}} Private](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [使用 {{site.data.keyword.dev_cli_long}} CLI 外掛程式部署至 {{site.data.keyword.cloud_notm}} 上的 Kubernetes](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [使用 {{site.data.keyword.dev_cli_long}} CLI 外掛程式啟用 {{site.data.keyword.cloud_notm}} 現有專案](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### 影片
{: #cli-videos}

- [如何使用 {{site.data.keyword.dev_cli_long}} CLI 外掛程式部署至 {{site.data.keyword.cloud_notm}} 上的 Kubernetes](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [如何使用 {{site.data.keyword.dev_cli_long}} CLI 外掛程式將現有專案部署至 {{site.data.keyword.cloud_notm}}](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [使用 {{site.data.keyword.dev_cli_long}} CLI 外掛程式和 VSCode 建立、除錯及部署 Node.js 應用程式](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### 文件及指導教學
- [持續部署至 Kubernetes](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [疑難排解 {{site.data.keyword.dev_cli_long}} CLI 外掛程式](/docs/cli?topic=cloud-cli-troubleshoot)
- [{{site.data.keyword.dev_cli_long}} CLI 外掛程式 (ibmcloud dev) 指令](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [{{site.data.keyword.dev_cli_long}} CLI 外掛程式的本端應用程式除錯](/docs/cli/idt?topic=cloud-cli-local-debug)

**若要報告問題或提供意見，您可以使用 [{{site.data.keyword.cloud_notm}} Tech 的 Slack - #developer-tools 頻道](https://ibm-cloud-tech.slack.com) - 在[這裡](https://slack-invite-ibm-cloud-tech.mybluemix.net/)要求團隊存取。**
