---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# 常见问题及解答 (FAQ)
{: #ibm-cli-faq}

## {{site.data.keyword.cloud_notm}} 应用程序的文件结构是什么?
{: #cli-file-structure}

从 CLI 创建或启用的应用程序随附了 `cli-config.yml` 文件中封装的预配置设置。`cli-config.yml` 包含 CLI 命令使用的缺省条目，可由通过命令行传递的值覆盖。

部署到 DevOps 工具链的应用程序可能还包含诸如 `toolchain.yml` 和 `pipeline.yml` 的文件。手动部署的应用程序可包含 `manifest.yml` 和 Helm chart 文件（例如，部署到 Cloud Foundry 或 Kubernetes）。

## 如何使用本地容器？
{: #cli-faq-containers}

{{site.data.keyword.dev_cli_long}} CLI 插件使用两个容器来帮助构建和测试应用程序。第一个是 tools 容器，包含用于构建和测试应用程序的必要实用程序。此容器的 `Dockerfile` 由 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 参数定义。您可将其视为开发容器，因为它包含通常用于开发特定运行时的工具。

另一个容器是运行容器，它密切模拟应用程序在部署到云中以后的实际运行时环境。此容器的形式适合部署以供在 {{site.data.keyword.cloud_notm}} 等中使用。因此，将定义用于启动应用程序的入口点。选择通过 {{site.data.keyword.dev_cli_long}} CLI 插件来运行应用程序时，它将使用此容器。此容器的 `Dockerfile` 由 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) 参数定义。

# 如何部署现有代码?
要部署现有代码库，请执行以下步骤来[启用应用程序](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli)。

## 参考博客、视频和文档
{: #cli-faq-reference}

### 博客
{: #cli-blogs}

- [使用 {{site.data.keyword.dev_cli_long}} CLI 插件部署到 {{site.data.keyword.cloud_notm}} Private](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [使用 {{site.data.keyword.dev_cli_long}} CLI 插件部署到 Kubernetes on {{site.data.keyword.cloud_notm}}](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [使用 {{site.data.keyword.dev_cli_long}} CLI 插件启用 {{site.data.keyword.cloud_notm}} 的现有项目](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### 视频
{: #cli-videos}

- [如何使用 {{site.data.keyword.dev_cli_long}} CLI 插件部署到 Kubernetes on {{site.data.keyword.cloud_notm}}](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [如何使用 {{site.data.keyword.dev_cli_long}} CLI 插件将现有项目部署到 {{site.data.keyword.cloud_notm}}](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [使用 {{site.data.keyword.dev_cli_long}} CLI 插件和 VSCode 创建、调试和部署 Node.js 应用程序](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### 文档和教程
- [持续部署到 Kubernetes](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [{{site.data.keyword.dev_cli_long}} CLI 插件的故障诊断](/docs/cli?topic=cloud-cli-troubleshoot)
- [{{site.data.keyword.dev_cli_long}} CLI 插件 (ibmcloud dev) 命令](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [{{site.data.keyword.dev_cli_long}} CLI 插件的本地应用程序调试](/docs/cli/idt?topic=cloud-cli-local-debug)

**要报告问题或提供反馈，可使用 [{{site.data.keyword.cloud_notm}} Tech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com) - [在此处](https://slack-invite-ibm-cloud-tech.mybluemix.net/)请求团队访问。**
