---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-18"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Deploying apps with IBM Eclipse Tools for IBM Cloud
{: #deploying-apps-with-ibm-eclipse-tools-for-ibm-cloud}

IBM® Eclipse Tools for {{site.data.keyword.Bluemix_notm}} provides plug-ins that can be installed into an existing Eclipse environment to assist in integrating the developer's integrated development environment (IDE) with Bluemix®. The tools allow you to deploy your JavaScript, WAR (web archive) and EAR (enterprise archive) files, and Liberty Profile packaged servers to the Cloud server right from your Eclipse IDE, or WebSphere® Application Server Developer Tools (WDT).  The tools also allow you to create and link services to your application and define environment variables as part of the deployment.

If you already have your application running in Eclipse using Websphere Application Developer Tools with Liberty Profile, you can install these tools on top of the running program.  You can deploy your applications by adding the application to the Cloud server in the workbench.  Thanks to the unique features of the Liberty buildpack for packaged server support, you also have an option to deploy the entire Liberty Profile server to Cloud.  You can also deploy Node.js JavaScript applications to Cloud.

## Installing the Eclipse Tools

Learn to install the IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. A Java™ 1.7 or later Execution Environment is required.

There are multiple ways to install the IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, including:
* Installing from the Marketplace.
* Installing from WASDev.
* Downloading from the IBM WebSphere Application Server Developer Tools (WDT) Installer.

### Installing from the Marketplace

Installation requires [Eclipse Oxygen for Java EE Developers (4.7)](https://www.eclipse.org/downloads/packages/release/oxygen/r/eclipse-ide-java-developers) or [Eclipse Neon for Java EE Developers (4.6)](http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers).

Then, follow the instructions here: [https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help](https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help).

### Installing from WASDev

1. Open the [Download](https://developer.ibm.com/wasdev/downloads/) page in WASDev.
2. Drag the `Install` icon to the toolbar in Eclipse.
3. By default, there are features that are selected for you. Click **Confirm**.
4. Accept the license agreement and click **Finish**.

### Downloading from the IBM WebSphere Application Server Developer Tools (WDT) Installer

1. Open **Help > Install WebSphere Software**. Search for Cloud
2. Select the `IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}` entry and click **Install**.
3. By default, there are features that are selected for you. Click **Confirm**.
4. Accept the license agreement and click **Finish**.

## Packaged server support

With IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, there are multiple scenarios for pushing a Liberty server or a packaged server to Cloud and confirming the deployment.

* Create the Cloud server.
* Create a Liberty Profile server with a WAR or EAR file.
* Stop the server.

Using the IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} for packaged server support, there are multiple scenarios for:

* Pushing a Liberty server to Cloud.
* Pushing a Liberty packaged server to Cloud.
* Confirming the successful deployment of the application with testing.

In addition, you can import packaged server compressed files into any project in your workspace.

### Scenario 1 - Adding a stopped Liberty Server to Cloud and testing an application

1. Right-click the `Cloud` server in the Servers View.
2. Select **Add and Remove**.
3. In the dialogue box, the Liberty server instances are shown. Select one and click **Add**.
4. Click **Finish**.
5. In the Application Dialogue, the default name is derived from the Liberty Server instance. You can change this name, but it must not contain spaces or special characters. The default is acceptable if it does not conflict with the name of the existing applications in the Cloud server.
6. Click **Finish** then wait for the application to publish on Cloud.
7. Right-click the added Liberty Server module under the Cloud server. Select **Open Home Page**. The packaged server root URL opens in your default web browser. Use this root URL as the base to build the URL for testing within the packaged WAR and EAR applications.

### Scenario 2 - Drag and drop a stopped Liberty Server to Cloud

Scenario 1 described how you can add and remove Liberty Server modules. This can be simplified with a drag and drop function.

1. If continuing from Scenario 1, remove the Liberty Server module from the Cloud server.
2. Select and drag the stopped Liberty server instance and drop it into the Cloud server in the Servers view. The Application Dialogue window appears.
3. Follow steps 5-10 from Scenario 1.

### Scenario 3 - Run a packaged server to Cloud

The context menu of the Liberty Profile service instance includes a Package Server action. This action packages the server into an archive file. In the Cloud, a new action has been added to package the server into a compressed file and deploy it to IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

1. If continuing from Scenario 1 or 2, remove the Liberty Server module from the Cloud server.
2. Right-click the Liberty Profile server instance in the Servers view.
3. Under the Utilities menu, select **Package Server to {{site.data.keyword.Bluemix_notm}}**.
4. In the dialogue box, choose the Cloud server where you want to deploy the application.
5. Click **OK**. The Application Dialogue window appears.
6. Follow steps 5-10 from Scenario 1.
7. If a progress dialogue window appears, choose **Run in background** and wait until the application is deployed.

### Scenario 4 - Working with Packaged Server compressed files - Run on Server

The previous scenarios describe how to work with existing Liberty Server instances in the Servers view and how you can deploy them to Cloud. You can also deploy existing packaged server compressed files to Cloud.

1. Create or obtain a packaged server compressed file.
2. Import the compressed file into any project in the workspace.
3. Right-click the compressed file and select **Run As > Run on Server**. The Run On Server dialogue window appears.
4. Select a Cloud server.
5. Click **Finish**. The Application Dialogue window appears.
6. Follow steps 5-10 from Scenario 1. The name of the module is derived from the compressed file.

### Scenario 5 - Working with Packaged Server compressed files - Drag and Drop

1. Select and drag the packaged server compressed file then drop it into the Cloud server in the Servers view. The application dialogue window appears.
2. Follow steps 5-10 from Scenario 1. The name of the module is derived from the name of the compressed file.

## Pushing an EAR file

Use the IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} to push an EAR to Cloud.

Define a new server.

1. To create a new Cloud server, select **File > New > Other**.
2. Select **Server** from the Server category, and then click **Next**.
3. Under IBM, find Cloud.
4. Click **Next**.
5. Enter your Cloud account information. Click **Sign Up** if you do not have an account.
6. Click **Next**.
7. Choose your Organizations and Spaces. The default is `dev`.
8. Click **Next**.
9. Click **Finish**.

Import an EAR file

1. Right-click and select **Import**.
2. Search for EAR file.
3. Browse for the EAR file you wish to import.
4. Ensure that the Target runtime is set to {{site.data.keyword.Bluemix_notm}} Runtime.

Deploy your application.

1. Right-click the started Cloud server. Choose **Add and Remove**.
2. Choose the EAR, and click **Add**.
3. Click **Finish**. The Application Details window opens.
4. Name the application then click **Next**. A valid name can contain A-Z, 0-9, -, and _. It cannot contain spaces or other special characters The Launch Deployment information is set by default.
5. Click **Next**.
6. If necessary, select services. Click **Next**.
7. If necessary, add variables. Click **Finish**.
8. After the application is pushed, right-click the project and choose **Open Home Page**.
9. Add the web module name and the application name to the URL.
10. To save the settings and variables that you specified, select the **Save to the manifest file** checkbox in the Application details window.

## Deploying a Node.js application
Use the IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} to deploy an existing or new Node.js project onto Cloud, set application deployment details, and verify the results in a browser.

If you do not already have an existing Node.js application, begin with Step 1. If you already have an existing Node.js application, begin with Step 7.

1. Select **File > New > Project**.
2. Select **JavaScript project** from the JavaScript category.
3. Click **Next**.
4. Name the project.
5. Click **Finish**.

Define a new server.

1. To create a new Cloud server, select **File > New > Other**.
2. Select **Server** from the Server category, and then click **Next**.
3. Under IBM, find Cloud.
4. Click **Next**.
5. Enter your Cloud account information. Click **Sign Up** if you do not have an account.
6. Click **Next**.
7. Choose your Organizations and Spaces. The default is `dev`.
8. Click **Next**.
9. Click **Finish**.

Enable the application for publishing to Cloud

1. Right-click the project in the Project Explorer and choose **Properties > Project Facet**.
2. Click **Convert to faceted form**.
3. Under Project Facets, select **Node.js Application**.
4. Click **OK**.

Deploy your application.

1. Right-click the started Cloud server. Choose **Add and Remove**.
2. Choose the project, and click **Add**.
3. Click **Finish**. The Application Details window opens.
4. To save the deployment configuration to the application's manifest file, select the **Save to the manifest file** checkbox in the Application details window.
5. Name the application then click **Next**. A valid name can contain A-Z, 0-9, -, and _. It cannot contain spaces or other special characters.
6. Accept the defaults on the Launch Deployment information panel.
7. Click **Next**.
8. If necessary, select services. Click **Next**.
9. If necessary, add variables. Click **Finish**.
10. After the application is pushed, right-click the project and choose **Open Home Page**.

## Incremental Publish

You can update application files incrementally without having to repush your entire application.
An incremental publish saves you from performing a complete redeployment for each change, saving time throughout the development process.

This feature supports web applications (WAR and EAR) and packaged servers.

To use incremental publishing, [Development Mode](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) must be enabled for the application or packaged server.

1. Add an application or packaged server to Cloud, unless one exists.
**Note:** This function cannot be enabled if the application deployment name has an underscore.

2. Enable development mode by right-clicking on the application or packaged server and selecting **Enable Development Mode**.

Once development mode is enabled, use the incremental publish function:

1. Modify the application as wanted.
   **Note:** For packaged servers, modifications to the configuration are not supported.

2. Save the changes.

3. Right-click on the Cloud server and select **Publish**.

Cached modes: After restarting the workbench, if the application was in development mode or debug mode, you see a progress window that says, "Retrieving development and debug states". Accordingly, after the progress finishes, development mode and debug mode are refreshed.

## Remote Debug

Run remote debugging against a Liberty or Node.js application.

[Development Mode](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) must be enabled to run the debug. This mode runs automatically upon selecting Enable Application Debug.

### Enable Debug of enterprise archive (EAR), web archive (WAR), or Liberty Server

Currently, a free local port is generated randomly, but if a client firewall blocks it, the debug scenario fails. To bypass this, start development mode, locate the bluemixcache.xml file, and add port="#", where the # is the port number of the local machine.

1. Under the Cloud server, right-click the application that you want to debug.

   **Note:** This function cannot be enabled if the application deployment name has an underscore. Change the name before enabling remote debug.

2. Click **Enable Application Debug**.

   The Progress View shows the status of `Establishing debug session for <AppName>``.

   The application shows that it is `Developing, Debugging <AppName>`.

   The debugger is running and ready to use.

### Disable Debug of EAR, WAR, or Liberty Server

You can disable the debug process and leave development mode enabled.

1. Right-click the application.
2. Click **Disable Application Debug**.
3. A dialog box asks if you want to disable development mode, also. Click **Yes** or **No**.

If development mode remains running, the application shows that it is `Developing <AppName>``.

 If both are disabled, the application shows that it is `Deployed as <AppName>`.

### Enable Debug of Node.js applications

**Note:** Before completing the following steps, ensure that you have an existing JavaScript application that is deployed to Cloud. See previous steps for more information on deploying a JavaScript application.

1. In the Servers view, right-click the Node.js application and select **Open** JavaScript Debugger. A dialog box appears and asks if you want to increase the memory limit of the application.
2. Click Yes. Enabling JavaScript Debugging increases the application memory requirements, and the application restarts more quickly with the updated memory limit.
3. Select a browser installation to use for debugging. Google Chrome is the only browser supported. If Google Chrome is not an available option, select the **Manage...** link and add a link to a local Google Chrome install.
4. Click **OK**. A progress monitor indicating Updating (your app) to debug mode appears. Once the debug is enabled, Google Chrome opens to the correct site.
5. Authenticate in Google Chrome with your login name and password. After a successful authentication, the debug console opens. You can now debug the application.

Cached modes: After restarting the workbench, if the application was in development mode or debug mode, you see a progress window that says, Retrieving development and debug states. After the progress finishes, development mode and debug mode are refreshed.

## Connecting to a remote Liberty server

Learn to use IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} to connect to a remote Liberty server. You can connect to a remote Liberty server that runs WebSphere Application Server as a service.

To connect to a remote Liberty server, Liberty Tools must be installed. You must also create a WebSphere Application Server service on Cloud.

1. Right-click your Cloud server and select **Configure remote servers...**.

   This option is only available if Liberty Tools are installed.

2. Select a WebSphere Application Server service.

   If you do not have a WebSphere Application Server service, you can receive an error message. You must create a WebSphere Application Server service on Cloud before you can complete this setup.

3. To define a runtime environment, select **Configure runtime environments...**.

   **Note:** If you previously created a runtime environment, you can skip this step.

4. Click **Next**.

5. Enter the server connection information.

6. Click **Finish**.

You connected to a remote Liberty server by using IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

## Enabling Cloud Foundry Diego on Cloud Applications

Enable the Diego architecture function from within IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. To enable Diego, you need a Cloud server that is defined in the Servers view.

Diego is a new Cloud Foundry architecture that Cloud Foundry instances use to manage running application containers. Diego architecture replaces the Droplet Execution Agents (DEA) architecture that Cloud Foundry previously used. Cloud Foundry installations are going to be moved to Diego, and user applications automatically and transparently switch to the new architecture.

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} support Diego and DEA. You can publish applications, enable incremental application publishing, and debug applications. Diego also allows IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} to create Secure Shell (SSH) tunnels into deployed Cloud applications, which allows faster and more reliable connections to Cloud applications while debugging. You can also enable SSH so that you can create your own tunnels to access application resources.

Complete the following steps to use the Diego architecture for your applications before Cloud switches to deploying with Diego by default:

1. Right-click on the deployed application in the Servers view.
2. If Diego is supported on your Cloud server, and your application is not already deployed with Diego, select **Enable Diego** from the menu.
3. If the server supports SSH tunneling, the program asks if you want to enable SSH for your application. SSH tunnels are a more reliable mechanism for communicating with your application. However, if you select **No**, functions in IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} continue to work by using a mechanism that does not require SSH tunneling.

The application then redeploys by using Diego architecture.

## Creating a server with Cloud Enterprise Federation

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} support Cloud Enterprise Federation, a single sign-on service that enables users to securely access cloud services. With Cloud Enterprise Federation, you can enable a custom third-party authentication that is provided by your own organization, without the standard login authentication, for other users to securely access applications.

Cloud Enterprise Federation authenticates a set of users to access cloud services. After you enable Cloud Enterprise Federation, your users receive authentication for cloud-enabled applications through the single sign-on option. Users must select the single sign-on option to create a server in the Eclipse workbench and log-in with the organization log-in and password. After you enable Cloud Enterprise Federation, the traditional Cloud User ID and password in Eclipse Tools is no longer used to authenticate users.

1. In IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, select **File > New > Other...**.
2. Select **Server > Server > Next**.
3. From the tree, select **IBM > {{site.data.keyword.Bluemix_notm}} > Next**.
4. Select the **Use a one-time password to log in (SSO)** check box.
5. A hyperlink appears in the log-in dialog. Click the hyperlink to open the Cloud authentication page.
6. Enter your email address and your intended password.
7. After a successful log-in, you are provided with a one-time passcode. Copy this passcode into the Passcode: field of Eclipse Tools for Cloud New Server dialog.
8. Click **Finish**.

A Cloud server entry is listed in the Servers view with Connected as the Server Status.
