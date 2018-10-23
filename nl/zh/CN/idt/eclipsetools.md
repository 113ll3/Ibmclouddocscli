---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-18"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 部署应用程序
{: #deploying-apps-with-ibm-eclipse-tools-for-ibm-cloud}

IBM® Eclipse Tools for {{site.data.keyword.Bluemix}} 提供了可安装到现有 Eclipse 环境中的插件，用于帮助将开发者的集成开发环境 (IDE) 与 Bluemix® 相集成。通过这些工具，您可以直接将 JavaScript、WAR（Web 归档）和 EAR（企业归档）文件以及 Liberty Profile 打包服务器从 Eclipse IDE 或 WebSphere® Application Server Developer Tools (WDT) 部署到云服务器。这些工具还允许您在部署期间创建服务并将服务链接到应用程序，以及定义环境变量。

如果已经使用带 Liberty Profile 的 WebSphere Application Developer Tools 在 Eclipse 中运行应用程序，那么可以基于正在运行的程序来安装这些工具。您可以通过将应用程序添加到工作台中的云服务器来部署这些应用程序。由于 Liberty buildpack 支持打包服务器的独特功能，您还可以选择将整个 Liberty Profile 服务器部署到云。此外，可以将 Node.js JavaScript 应用程序部署到云。

## 安装 Eclipse Tools

了解安装 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}。需要 Java™ 1.7 或更高版本执行环境。

有多种方式可安装 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}，包括：
* 通过 Marketplace 进行安装。
* 通过 WASDev 进行安装。
* 通过 IBM WebSphere Application Server Developer Tools (WDT) 安装程序下载。

### 通过 Marketplace 进行安装

安装需要 [Eclipse Oxygen for Java EE Developers (4.7)](https://www.eclipse.org/downloads/packages/release/oxygen/r/eclipse-ide-java-developers) 或 [Eclipse Neon for Java EE Developers (4.6)](http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers)。

然后，遵循此处的指示信息进行操作：[https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help](https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help)。

### 通过 WASDev 进行安装

1. 在 WASDev 中打开[下载](https://developer.ibm.com/wasdev/downloads/)页面。
2. 将`安装`图标拖至 Eclipse 中的工具栏。
3. 缺省情况下，已选择一些功能。请单击**确认**。
4. 接受许可协议，然后单击**完成**。

### 通过 IBM WebSphere Application Server Developer Tools (WDT) 安装程序下载

1. 打开**帮助 > 安装 WebSphere 软件**。搜索 Cloud。
2. 选择 `IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}` 条目，然后单击**安装**。
3. 缺省情况下，已选择一些功能。请单击**确认**。
4. 接受许可协议，然后单击**完成**。

## 打包服务器支持

使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 时，有多种场景可用于将 Liberty 服务器或打包服务器推送到云并确认部署。

* 创建云服务器。
* 使用 WAR 或 EAR 文件创建 Liberty Profile 服务器。
* 停止该服务器。

使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 支持打包服务器时，有多种场景可用于：

* 将 Liberty 服务器推送到云。
* 将 Liberty 打包服务器推送到云。
* 通过测试确认应用程序是否成功部署。

此外，还可以将打包服务器压缩文件导入到工作空间的任何项目。

### 场景 1 - 将已停止的 Liberty 服务器添加到云并测试应用程序

1. 在“服务器”视图中，右键单击`云`服务器。
2. 选择**添加和除去**。
3. 在对话框中，将显示 Liberty 服务器实例。选择其中一个实例，然后单击**添加**。
4. 单击**完成**。
5. 在“应用程序”对话框中，缺省名称将从 Liberty 服务器实例中派生。可以更改此名称，但名称中不能包含空格或特殊字符。如果缺省名称与云服务器中现有应用程序的名称不冲突，那么可接受缺省值。
6. 单击**完成**，然后等待应用程序在云上发布。
7. 右键单击在云服务器下添加的 Liberty 服务器模块。选择**打开主页**。打包服务器根 URL 将在缺省 Web 浏览器中打开。使用此根 URL 作为基础来构建用于在打包 WAR 和 EAR 应用程序中进行测试的 URL。

### 场景 2 - 将已停止的 Liberty 服务器拖放到云

场景 1 描述了可以如何添加和除去 Liberty 服务器模块。此场景可以通过拖放功能进行简化。

1. 如果是从场景 1 继续操作，请从云服务器中除去 Liberty 服务器模块。
2. 在“服务器”视图中，选择已停止的 Liberty 服务器实例，并将其拖放到云服务器中。这将显示“应用程序”对话框窗口。
3. 执行场景 1 中的步骤 5-10。

### 场景 3 - 将打包服务器运行到云

Liberty Profile 服务实例的上下文菜单包含“打包服务器”操作。此操作将服务器打包成归档文件。在云中，添加了一个新操作，用于将服务器打包成压缩文件，然后将其部署到 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}。

1. 如果是从场景 1 或 2 继续操作，请从云服务器中除去 Liberty 服务器模块。
2. 在“服务器”视图中，右键单击 Liberty Profile 服务器实例。
3. 在“实用程序”菜单下，选择**将服务器打包到 {{site.data.keyword.Bluemix_notm}}**。
4. 在对话框中，选择要部署应用程序的云服务器。
5. 单击**确定**。这将显示“应用程序”对话框窗口。
6. 执行场景 1 中的步骤 5-10。
7. 如果显示进度对话框窗口，请选择**在后台运行**，然后等待应用程序部署完成。

### 场景 4 - 使用打包服务器压缩文件 - 在服务器上运行

先前的场景描述了如何在“服务器”视图中使用现有 Liberty 服务器实例以及如何将其部署到云。您还可以将现有的打包服务器压缩文件部署到云。

1. 创建或获取打包服务器压缩文件。
2. 将压缩文件导入到工作空间中的任何项目。
3. 右键单击压缩文件，并选择**运行方式 > 在服务器上运行**。这将显示“在服务器上运行”对话框窗口。
4. 选择云服务器。
5. 单击**完成**。这将显示“应用程序”对话框窗口。
6. 执行场景 1 中的步骤 5-10。模块的名称将从压缩文件派生。

### 场景 5 - 使用打包服务器压缩文件 - 拖放

1. 在“服务器”视图中，选择打包服务器压缩文件，然后将其拖放到云服务器中。这将显示“应用程序”对话框窗口。
2. 执行场景 1 中的步骤 5-10。模块的名称将从压缩文件的名称派生。

## 推送 EAR 文件

使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 将 EAR 推送到云。

定义新服务器。

1. 要创建新的云服务器，请选择**文件 > 新建 > 其他**。
2. 从“服务器”类别中选择**服务器**，然后单击**下一步**。
3. 在 IBM 下，找到“云”。
4. 单击**下一步**。
5. 输入您的云帐户信息。如果您没有帐户，请单击**注册**。
6. 单击**下一步**。
7. 选择“组织”和“空间”。缺省值为 `dev`。
8. 单击**下一步**。
9. 单击**完成**。

导入 EAR 文件

1. 右键单击并选择**导入**。
2. 搜索 EAR 文件。
3. 浏览以找到要导入的 EAR 文件。
4. 确保“目标运行时”设置为 {{site.data.keyword.Bluemix_notm}} Runtime。

部署应用程序。

1. 右键单击启动的云服务器。选择**添加和除去**。
2. 选择 EAR，然后单击**添加**。
3. 单击**完成**。这将打开“应用程序详细信息”窗口。
4. 命名应用程序，然后单击**下一步**。有效名称可以包含 A-Z、0-9、- 和 _，但不能包含空格或其他特殊字符。缺省情况下，已设置“启动部署”信息。
5. 单击**下一步**。
6. 根据需要选择服务。单击**下一步**。
7. 根据需要添加变量。单击**完成**。
8. 推送应用程序后，右键单击项目，并选择**打开主页**。
9. 向 URL 添加 Web 模块名称和应用程序名称。
10. 要保存指定的设置和变量，请在“应用程序详细信息”窗口中选中**保存到清单文件**复选框。

## 部署 Node.js 应用程序
使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 可将现有 Node.js 项目或新 Node.js 项目部署到云，设置应用程序部署详细信息，并在浏览器中验证结果。

如果您还没有现有的 Node.js 应用程序，请从步骤 1 开始。如果您已有现有的 Node.js 应用程序，请从步骤 7 开始。

1. 选择**文件 > 新建 > 项目**。
2. 从 JavaScript 类别中，选择 **JavaScript 项目**。
3. 单击**下一步**。
4. 命名项目。
5. 单击**完成**。

定义新服务器。

1. 要创建新的云服务器，请选择**文件 > 新建 > 其他**。
2. 从“服务器”类别中选择**服务器**，然后单击**下一步**。
3. 在 IBM 下，找到“云”。
4. 单击**下一步**。
5. 输入您的云帐户信息。如果您没有帐户，请单击**注册**。
6. 单击**下一步**。
7. 选择“组织”和“空间”。缺省值为 `dev`。
8. 单击**下一步**。
9. 单击**完成**。

启用应用程序以发布到云

1. 在 Project Explorer 中右键单击项目，并选择**属性 > 项目构面**。
2. 单击**转换为构面形式**。
3. 在“项目构面”下，选择 **Node.js 应用程序**。
4. 单击**确定**。

部署应用程序。

1. 右键单击启动的云服务器。选择**添加和除去**。
2. 选择项目，然后单击**添加**。
3. 单击**完成**。这将打开“应用程序详细信息”窗口。
4. 要将部署配置保存到应用程序清单文件，请在“应用程序详细信息”窗口中选中**保存到清单文件**复选框。
5. 命名应用程序，然后单击**下一步**。有效名称可以包含 A-Z、0-9、- 和 _，但不能包含空格或其他特殊字符。
6. 接受“启动部署”信息面板上的缺省值。
7. 单击**下一步**。
8. 根据需要选择服务。单击**下一步**。
9. 根据需要添加变量。单击**完成**。
10. 推送应用程序后，右键单击项目，并选择**打开主页**。

## 递增发布

您可以通过递增方式更新应用程序文件，而不必重新推送整个应用程序。利用递增发布，您就不必为了每个更改而执行完整的重新部署，因此可节省整个开发流程的时间。

此功能支持 Web 应用程序（WAR 和 EAR）以及打包服务器。

要使用递增发布，必须为应用程序或打包服务器启用[开发方式](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html)。

1. 将应用程序或打包服务器添加到云（除非已存在应用程序或打包服务器）。
**注：**如果应用程序部署名称带下划线，那么无法启用此功能。

2. 通过右键单击应用程序或打包服务器，并选择**启用开发方式**来启用开发方式。

在启用开发方式之后，请使用递增发布功能：

1. 根据需要修改应用程序。
   **注：**对于打包服务器，不支持修改配置。

2. 保存更改。

3. 右键单击云服务器，并选择**发布**。

高速缓存方式：重新启动工作台后，如果应用程序处于开发方式或调试方式，那么您会看到一个进度窗口，其中显示“正在检索开发和调试状态”。进度完成后，将相应地刷新开发方式和调试方式。

## 远程调试

针对 Liberty 或 Node.js 应用程序运行远程调试。

必须启用[开发方式](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html)才可运行调试。此方式会在选择“启用应用程序调试”时自动运行。

### 启用调试企业归档 (EAR)、Web 归档 (WAR) 或 Liberty 服务器

目前，系统会随机生成一个空闲本地端口，但如果客户机防火墙阻止该端口，那么调试场景会失败。要绕过防火墙，请启动开发方式，找到 bluemixcache.xml 文件，然后添加 port="#"，其中 # 是本地计算机的端口号。

1. 在云服务器下，右键单击要调试的应用程序。

   **注：**如果应用程序部署名称带下划线，那么无法启用此功能。先更改名称，然后再启用远程调试。

2. 单击**启用应用程序调试**。

   “进度”视图会显示状态：`正在建立对 <AppName> 的调试会话`。

   应用程序会显示它`正在开发，正在调试 <AppName>`。

   调试器正在运行，可随时使用。

### 禁用调试 EAR、WAR 或 Liberty 服务器

可以禁用调试过程，但使开发方式保持启用状态。

1. 右键单击应用程序。
2. 单击**禁用应用程序调试**。
3. 这将显示一个对话框，询问您是否还要禁用开发方式。单击**是**或**否**。

如果开发方式保持运行，那么应用程序会显示它`正在开发 <AppName>`。

 如果同时禁用了调试和开发方式，那么应用程序会显示它`已部署为 <AppName>`。

### 启用调试 Node.js 应用程序

**注：**在完成以下步骤之前，确保您已具有部署到云的现有 JavaScript 应用程序。请参阅先前的步骤，以获取有关部署 JavaScript 应用程序的更多信息。

1. 在“服务器”视图中，右键单击 Node.js 应用程序，并选择**打开** JavaScript 调试器。这将显示一个对话框，询问您是否要增大应用程序的内存限制。
2. 单击“是”。启用 JavaScript 调试会增大应用程序内存需求，并且应用程序会在更新后的内存限制下更快地重新启动。
3. 选择要用于调试的浏览器安装。Google Chrome 是唯一支持的浏览器。如果 Google Chrome 选项不可用，请选择**管理...** 链接，然后添加本地 Google Chrome 安装的链接。
4. 单击**确定**。这将显示一个进度监视器，指示正在将（应用程序）更新为调试方式。启用调试后，Google Chrome 会打开到正确的站点。
5. 使用您的登录名和密码在 Google Chrome 中进行认证。认证成功后，将打开调试控制台。现在，您可以调试应用程序。

高速缓存方式：重新启动工作台后，如果应用程序处于开发方式或调试方式，那么您会看到一个进度窗口，其中显示“正在检索开发和调试状态”。进度完成后，将刷新开发方式和调试方式。

## 连接到远程 Liberty 服务器

了解如何使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 连接到远程 Liberty 服务器。您可以连接到将 WebSphere Application Server 作为服务运行的远程 Liberty 服务器。

要连接到远程 Liberty 服务器，必须安装 Liberty Tools。您还必须在云上创建 WebSphere Application Server 服务。

1. 右键单击云服务器，并选择**配置远程服务器...**。

   仅当安装了 Liberty Tools 时，此选项才可用。

2. 选择 WebSphere Application Server 服务。

   如果您没有 WebSphere Application Server 服务，那么会收到错误消息。您必须先在云上创建 WebSphere Application Server 服务，然后才能完成此设置。

3. 要定义运行时环境，请选择**配置运行时环境...**。

   **注：**如果先前已创建运行时环境，那么可以跳过此步骤。

4. 单击**下一步**。

5. 输入服务器连接信息。

6. 单击**完成**。

您已使用 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 连接到远程 Liberty 服务器。

## 在云应用程序上启用 Cloud Foundry Diego

在 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 中启用 Diego 体系结构功能。要启用 Diego，您需要在“服务器”视图中定义的云服务器。

Diego 是一种新的 Cloud Foundry 体系结构，供 Cloud Foundry 实例用于管理正在运行的应用程序容器。Diego 体系结构取代了 Cloud Foundry 先前使用的 Droplet Execution Agents (DEA) 体系结构。Cloud Foundry 安装将移至 Diego，并且用户应用程序将自动且透明地切换到新体系结构。

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 支持 Diego 和 DEA。您可以发布应用程序，启用增量应用程序发布，并调试应用程序。Diego 还支持 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 在部署的云应用程序中创建安全 Shell (SSH) 隧道，从而允许在调试期间更快、更可靠地连接到云应用程序。您还可以启用 SSH，以便创建自己的隧道来访问应用程序资源。

在云切换到缺省情况下使用 Diego 进行部署之前，完成以下步骤将 Diego 体系结构用于应用程序：

1. 在“服务器”视图中，右键单击部署的应用程序。
2. 如果云服务器上支持 Diego，并且应用程序尚未使用 Diego 进行部署，请从菜单中选择**启用 Diego**。
3. 如果服务器支持 SSH 隧道，那么程序将询问您是否要为应用程序启用 SSH。SSH 隧道是用于与应用程序进行通信的更可靠机制。但是，如果选择**否**，那么 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 中的功能将继续使用不需要 SSH 隧道的机制运行。

然后，应用程序可使用 Diego 体系结构重新部署。

## 使用 Cloud Enterprise Federation 创建服务器

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 支持 Cloud Enterprise Federation，这是一种单点登录服务，支持用户安全地访问云服务。通过 Cloud Enterprise Federation，您可以启用自己组织提供的定制第三方认证，供其他用户安全地访问应用程序，而无需使用标准登录认证。

Cloud Enterprise Federation 可对一组要访问云服务的用户进行认证。启用 Cloud Enterprise Federation 后，用户将通过单点登录选项接收启用云的应用程序的认证。用户必须选择单点登录选项，才能在 Eclipse 工作台中创建服务器，并使用组织登录名和密码登录。启用 Cloud Enterprise Federation 后，Eclipse Tools 中的传统云用户标识和密码不再用于对用户进行认证。

1. 在 IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} 中，选择**文件 > 新建 > 其他...**。
2. 选择**服务器 > 服务器 > 下一步**。
3. 从树中，选择 **IBM > {{site.data.keyword.Bluemix_notm}} > 下一步**。
4. 选中**使用一次性密码登录 (SSO)** 复选框。
5. 这将在“登录”对话框中显示一个超链接。单击该超链接可打开“云认证”页面。
6. 输入您的电子邮件地址和您打算使用的密码。
7. 成功登录后，将为您提供一次性通行码。将此通行码复制到“云新建服务器”对话框中 Eclipse Tools 的“通行码：”字段中。
8. 单击**完成**。

“服务器”视图中会列出云服务器条目，其中“服务器状态”为“已连接”。
