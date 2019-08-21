---

copyright:
  years: 2019
lastupdated: "2019-08-07"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:external: target="_blank" .external}

# 常见问题
{: #ibm-cli-faq}

## 是否需要使用 {{site.data.keyword.cloud_notm}} CLI 的最新版本？
{: #cli-latest-version}

是的，您必须使用最新版本。您可以通过运行以下命令来检查使用的版本：

```
ibmcloud -v
```
{: codeblock}

## 如何更新 CLI
{: #cli-update-version}

运行以下命令来更新到 CLI 的最新版本：

```
ibmcloud update
```
{: codeblock}

## 如何获取有关新 CLI 发行版的通知？
{: #cli-get-notified}

是的，您可在 CLI 的新发行版可用时掌握最新情况。请预订 [{{site.data.keyword.cloud_notm}} CLI 发行版存储库](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external}。

## {{site.data.keyword.cloud_notm}} 应用程序的文件结构是什么?
{: #cli-file-structure}

从 CLI 创建或启用的应用程序随附了 `cli-config.yml` 文件中封装的预配置设置。`cli-config.yml` 包含 CLI 命令使用的缺省条目，可由通过命令行传递的值覆盖。

部署到 DevOps 工具链的应用程序可能还包含 `toolchain.yml` 和 `pipeline.yml` 之类的文件。手动部署的应用程序可包含 `manifest.yml` 和 Helm chart 文件（例如，部署到 Cloud Foundry 或 Kubernetes）。

## 如何使用本地容器？
{: #cli-faq-containers}

{{site.data.keyword.dev_cli_long}} CLI 插件使用两个容器来帮助构建和测试应用程序。第一个是 tools 容器，包含用于构建和测试应用程序的必要实用程序。此容器的 `Dockerfile` 由 [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) 参数定义。您可将其视为开发容器，因为它包含通常用于开发特定运行时的工具。

另一个容器是 run 容器，它能高度模拟应用程序在部署到云之后的实际运行时环境。此容器的形式适合部署以供在 {{site.data.keyword.cloud_notm}} 等中使用。因此，将定义用于启动应用程序的入口点。选择通过 {{site.data.keyword.dev_cli_long}} CLI 插件来运行应用程序时，它将使用此容器。此容器的 `Dockerfile` 由 [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) 参数定义。

## 如何部署现有代码？

要部署现有代码库，请参阅[生成部署和云支持资产](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli)。

