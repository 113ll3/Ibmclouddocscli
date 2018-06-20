---

copyright:
  years: 2015, 2018
lastupdated: "2018-05-29"

---



{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}


# 调试
{: #debugging}

如果您遇到 {{site.data.keyword.Bluemix}} 问题，那么可以查看日志文件来调查问题并调试错误。
{:shortdesc}

日志提供了相关信息，例如，作业运行成功还是失败。另外，还提供了可用于调试问题和确定问题原因的相关信息。

日志为固定格式。对于详细日志，可过滤这些日志或使用外部日志记录主机来存储和处理这些日志。有关日志格式、查看和过滤日志以及配置外部日志记录的更多信息，请参阅[为 Cloud Foundry 上运行的应用程序进行日志记录 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](/docs/monitor_log/logging.html#logging){: new_window}。


## 调试编译打包错误
{: #debugging-staging-errors}
当您在 {{site.data.keyword.Bluemix_notm}} 上编译打包应用程序时，可能会遇到问题。如果应用程序未能编译打包，那么可以搜索及复查编译打包 (STG) 日志，以确定在应用程序部署期间发生的事项，并从问题进行恢复。有关查看 {{site.data.keyword.Bluemix}} 应用程序日志的方法的更多信息，请参阅[查看日志 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana){: new_window}。  

要了解您的应用程序可能在 {{site.data.keyword.Bluemix_notm}} 上失败的原因，需要知道应用程序如何在 {{site.data.keyword.Bluemix_notm}} 上部署和运行。有关详细信息，请参阅[应用程序部署 ![外部链接图标](../icons/launch-glyph.svg " 外部链接图标")](/docs/cfapps/depapps.html#appdeploy){: new_window}。


以下过程显示您可以如何使用 `cf logs` 命令来调试编译打包错误。在执行以下步骤之前，确保您已安装 cf 命令行界面。有关安装 cf 命令行界面的更多信息，请参阅[安装 cf 命令行界面 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](/docs/starters/install_cli.html){: new_window}。

  1. 通过在 cf 命令行界面中输入以下代码，连接 {{site.data.keyword.Bluemix_notm}}：
     ```
	 cf api https://api.stage1.ng.bluemix.net
	 ```

  2. 通过输入 `cf login` 登录到 {{site.data.keyword.Bluemix_notm}}。

  3. 通过输入 `cf logs appname --recent` 检索最近的日志。如果要过滤详细日志，请使用 `grep` 选项。例如，您可以输入以下代码以仅显示 [STG] 日志：
    ```
	cf logs appname --recent | grep '\[STG\]'
	```
  4. 查看日志中显示的第一个错误。

如果使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 插件来部署应用程序，那么可以在 Eclipse 工具的**控制台**选项卡中看到类似于 cf logs 输出的日志。部署应用程序时，还可以打开单独的 Eclipse 窗口来跟踪`日志`。

除 `cf logs` 命令之外，在 {{site.data.keyword.Bluemix_notm}} 中，您还可以使用 {{site.data.keyword.loganalysisshort}} 服务来收集日志详细信息。 

### 调试 Node.js 应用程序的编译打包错误

以下示例显示的是输入 `cf logs appname --recent` 之后显示的日志。以下示例假设 Node.js 应用程序发生了编译打包错误：

```
2014-08-11T14:19:36.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({name"=>"SampleExpressApp"}
2014-08-11T14:20:44.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STOPPED"})
2014-08-11T14:20:44.19+0100 [App/0]   ERR
2014-08-11T14:20:44.43+0100 [DEA]     OUT Stopping app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:44.44+0100 [DEA]     OUT Stopped app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:48.97+0100 [DEA]     OUT Got staging request for app with id 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:50.94+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STARTED"})
2014-08-11T14:20:51.66+0100 [STG]     OUT -----> Download app package (4.1M)
2014-08-11T14:20:51.90+0100 [STG]     OUT -----> Download app buildpack cache (1.1M)
2014-08-11T14:20:52.78+0100 [STG]     OUT -----> Buildpack Version: v1.1-20140717-1447
2014-08-11T14:20:52.78+0100 [STG]     ERR parse error: Expected another key-value pair at line 18, column 3
2014-08-11T14:20:52.79+0100 [STG]     OUT 0 info it worked if it ends with ok
```
{: screen}


日志中的第一个错误显示编译打包失败的原因。在该示例中，第一个错误是编译打包阶段中 DEA 组件的输出。

```
2014-08-11T14:20:52.78+0100 [STG]   ERR parse error: expected another key-value pair at line 18, column 3
```
{: screen}


对于 Node.js 应用程序，DEA 使用 `package.json` 文件中的信息来下载模块。根据这一错误信息，您可以知道模块发生错误。因此，您可能需要复查 `package.json` 文件中的第 18 行。

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*",
18   }
```
{: screen}


您会看到第 17 行的结尾有逗号，因此第 18 行上应该存在键/值对。要解决问题，请除去逗号：


```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*"
18   }
```
{: screen}


## 调试运行时错误
{: #debugging-runtime-errors}
如果在运行时遇到应用程序问题，应用程序日志可帮助查明错误原因并从该问题中进行恢复。

尤其是，可以启用 stdout 和 stderr 日志记录。有关如何为通过使用 {{site.data.keyword.Bluemix_notm}} 内置 buildpack 部署的应用程序配置日志文件的更多信息，请参阅以下列表：



  * 对于 Liberty for Java™ 应用程序，请参阅 [Liberty：记录和跟踪 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/support/knowledgecenter/en/SSEQTP_liberty/com.ibm.websphere.wlp.doc/ae/rwlp_logging.html){: new_window}。
  * 对于 Node.js 应用程序，请参阅 [Node.js debugging starts with better logging! ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/blogs/bluemix/2015/03/node-js-better-logging/){: new_window}。
  * 对于 PHP 应用程序，请参阅 [error_log ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](http://php.net/manual/en/function.error-log.php){: new_window}。
  * 对于 Python 应用程序，请参阅 [Logging HOWTO ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://docs.python.org/2/howto/logging.html){: new_window}。
  * 对于 Ruby on Rails 应用程序，请参阅 [The Logger ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](http://guides.rubyonrails.org/debugging_rails_applications.html#the-logger){: new_window}。
  * 对于 Ruby Sinatra 应用程序，请参阅 [Logging ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](http://www.sinatrarb.com/intro.html#Logging){: new_window}。

在 cf 命令行界面中输入 `cf logs appname --recent` 后，仅会显示最新的日志。要查看先前发生的错误的日志，必须检索所有日志并搜索错误。要检索应用程序的所有日志，请使用以下一种方法：
<dl>
<dt><strong>{{site.data.keyword.loganalysisshort}}</strong></dt>
<dd>{{site.data.keyword.loganalysisshort}} 服务的集成日志文件搜索和分析功能可以帮助您快速识别错误。有关更多信息，请参阅 <a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">{{site.data.keyword.loganalysisfull}}</a>。</dd>
<dt><strong>第三方工具</strong></dt>
<dd>您可以从应用程序收集日志并导出到外部日志主机。有关更多信息，请参阅<a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">配置外部日志记录</a>。</dd>
<dt><strong>用于收集和导出日志的脚本</strong></dt>
<dd>要使用脚本自动收集日志并导出到外部文件，必须从计算机连接到 {{site.data.keyword.Bluemix_notm}} 控制台，并且计算机上必须有足够的空间用于下载日志。有关更多信息，请参阅<a href="/docs/get-support/quicktickresp.html#collecting-diagnostic-information" target="_blank">收集诊断信息</a>。</dd>
</dl>

以前，缺省情况下，可以在 {{site.data.keyword.Bluemix_notm}} 控制台中应用程序视图的**文件** > **日志**下访问 `stdout.log` 和 `stderr.log` 文件。但是，对于托管 {{site.data.keyword.Bluemix_notm}} 的当前版本的 Cloud Foundry，应用程序日志记录不再可用。要继续保持可在 {{site.data.keyword.Bluemix_notm}} 控制台中的**文件** > **日志**下访问 stdout 和 stderr 应用程序日志记录，可以将日志记录重定向到 {{site.data.keyword.Bluemix_notm}} 文件系统中的其他文件，具体取决于正在使用的运行时。

  * 对于 Liberty for Java 应用程序，定向到 stdout 和 stderr 的输出已包含在 logs 目录下的 `messages.log` 文件中。分别查找以 SystemOut 和 SystemErr 为前缀的条目。

  * 对于 Node.js 应用程序，可以覆盖 console.log 函数来显式写入 logs 目录中的文件。
  * 对于 PHP 应用程序，可以使用 error_log 函数来写入 logs 目录中的文件。
  * 对于 Python 应用程序，可以让日志记录器写入 logs 目录中的文件：`logging.basicConfig(filename='/docs/logs/example.log',level=logging.DEBUG)`
  * 对于 Ruby 应用程序，可以让日志记录器写入 logs 目录中的文件。


### 调试代码更改
{: #debug_code_changes}

如果您对已经部署且正在运作的应用程序进行代码更改，但您的代码更改并未反映在 {{site.data.keyword.Bluemix_notm}} 中，那么您可以使用日志进行调试。无论您的应用程序运行与否，您都可以检查应用程序部署期间或运行时生成的日志，进行调试以找出新代码不运作的原因。



根据部署新代码的方式，选择下列其中一个方法来调试代码更改：

  

  * 对于通过 cf 命令行部署的新代码，请检查 *cf push* 命令的输出。此外，您还可以使用 *cf logs* 命令来查找解决问题的更多线索。有关如何使用 *cf logs* 命令的更多信息，请参阅[通过命令行界面查看日志](/docs/services/CloudLogAnalysis/manage_logs.html#manage_logs)。

  * 对于通过 GUI（如 {{site.data.keyword.Bluemix_notm}} 控制台、DevOps Delivery Pipeline 或 Travis-CI）部署的新代码，您可以在该界面中检查日志。例如，如果您从 {{site.data.keyword.Bluemix_notm}} 控制台部署新代码，那么您可以转至“仪表板”，查找应用程序，然后查看日志以获取线索。有关如何在 {{site.data.keyword.Bluemix_notm}} 控制台中查看日志的更多信息，请参阅[在 {{site.data.keyword.Bluemix}} 仪表板中查看日志](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana)。
