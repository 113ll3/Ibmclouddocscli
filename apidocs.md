---



copyright:

  years: 2016, 2017

lastupdated: "2017-01-12"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Creating REST API docs for {{site.data.keyword.Bluemix_notm}}
{: #apidocs}

With the {{site.data.keyword.Bluemix_short}} REST API microservice, you must provide well-annotated and properly formatted documentation. The {{site.data.keyword.Bluemix_notm}} REST APIs follow the [Open API spec ![External link icon](../icons/launch-glyph.svg)](https://openapis.org/specification){: new_window} (Swagger) with extensions in order to provide additional information.
{:shortdesc}

## REST API annotations ##
{: #annotations}

Providing good annotations to the APIs makes it easier for a wider audience to adopt usage. Additionally, the annotations allow new users to learn what they can do with the APIs. Most of the descriptions fields support markdown [GFM ![External link icon](../icons/launch-glyph.svg)](https://help.github.com/articles/basic-writing-and-formatting-syntax/){: new_window}, which allows you to create more human-readable content than straight text allows.

Here's an overview of some of the important content fields, including some not in the [Open API 2.0 spec ![External link icon](../icons/launch-glyph.svg)](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md){: new_window}:

### API name ###
**Description**: The unique name of the API

### API description ###
**Description**: The purpose of the API. Provide general information about what system or service is provided with this API and what version of the API it is. Provide an overview of what will be changed or affected using this API. Include any additional links to information. A good description answers the following questions:
+ Who would use this API?
+ Why would the user want to use this API? Why *your* API as opposed to a competitor's?
+ What prerequisite knowledge does the user need?
+ What prerequisites does the API require?


### Getting started sections(New extension) ###
**Description**: The information about the whole API, not specific to one endpoint. Provide information that is common to the API. You can have more than one "getting started" section. Think of this as discussion topics that are relevant to all API endpoints. Consider these sections that might be relevant to your API:
* API design philosophies
* recurring parameters
* metadata that the API provides with all responses
* common errors
* authentication
* pagination

**Examples**: For an error handling section, explain common errors types and how to make use of the error details that the API returns.

### Endpoint name ###
**Description**: The unique name of the endpoint. The API Explorer has two fields:
* name: The technical name of the endpoint
* summary: The human-readable name that will be used in the UI
The summary values should be command statements not descriptions.

*Tip*: Tag your endpoints to allow you to group them together into sections. Tagging the endpoints creates a heading in the left navigation and groups the endpoints together under that heading. Use the getting started section element to define the overall structure and introduce the sections.

**Examples**: <br />
Name: `GET /images` <br />
Summary: Get recent images

Name: `POST /users/{user_id}/images` <br />
Summary: Add an image to a user's gallery

### Endpoint operation description ###
**Description**: The purpose of this operation on the specific endpoint. Identify the HTTP operations, and what the endpoint does in detail. Describe why the endpoint is useful to the user. Additionally, you should anticipate any confusion and address; for example "This endpoint only provides a list of IDs. For detailed user information, use endpoint X."

**Example**: This operation retrieves all images that are assigned to your {{site.data.keyword.Bluemix_notm}} private repository and have the status "safe to deploy" or "deploy with caution". The list of images is returned in the following format ....

### Response error messages ###
**Description**: The description of the error message, including the explanation of the message and the action(s) the user should take to resolve. Be sure to describe the possible errors that can be returned, and provide specific information to resolve each error.

**Example**: <br />
HTTP response code: 404 <br />
Message: Container not Foundry <br />
Description: The container ID entered in the request is unknown. Review the correct container ID by running
```
cf ic ps -a
```
{:codeblock}
or
```
docker ps -a
```
{:codeblock}

### Example request ###
**Description**: An example of the Header and Body request. Follow the specific format that your API uses. *Note*: The microservice UI does not take advantage of this at this time. Providing this information now will enable complete information if the microservice enables it at a later time.

### Example response ###
**Description**: An example of the Header and Body response. Follow the specific format that your API uses. *Note*: The microservice UI does not take advantage of this at this time. Providing this information now will enable complete information if the microservice enables it at a later time.

### Code snippets (New extension) ###
**Description**: Brief segments of sample code in various languages that demonstrate how to make a simple REST call for each endpoint. Good code snippets make it easier for users to adopt your API: the better the code snippets are, the faster users will be able to adapt your API. The snippets are automatically generated in various languages and can be flagged to automatically regenerate snippets. If you manually overwrite the content for any code snippet in any language, the content updates will not be included when generated. You will be responsible for maintaining that content.

[REVIEW QUESTION: How does one flag them to auto generate snippets?]

**Example**: [NEED TO FIND GOOD EXAMPLES]

## Registering an API for {{site.data.keyword.Bluemix_notm}} ##
{: #register}

To use the {{site.data.keyword.Bluemix_notm}} to display your REST API docs, you must make them available to {{site.data.keyword.Bluemix_notm}}.

### Creating the API files manually using API Connect

If you are not generating your JSON files automatically, you can manually code the files using API Connect. You must set up your API Connect environment and start the project.

1. Set up your API Connect environment:
   1. Install Node.js [https://nodejs.org/en/download/ ![External link icon](../icons/launch-glyph.svg)](https://nodejs.org/en/download/){: new_window}. API Connect supports the current Node.js long-term support (LTS) version.
   2. Install IBM API connect toolkit using the following command:
  ```
  $ npm install -g apiconnect
  ```
  {:codeblock}

    Installing IBM API Connect installs the following tools:
     * API Connect Developer Toolkit (Command line tool `apic` and API Designer visual tool)
     * LoopBack Node.js framework
     * API Connect Micro Gateway

 3. Create a project directory to use.
 4. Download the AES Extensions and put the YAML file in the new directory. Download the extensions from [https://github.ibm.com/Papillon/AES-extension ![External link icon](../icons/launch-glyph.svg)](https://github.ibm.com/Papillon/AES-extension){: new_window}.

2. Start your project:
   1. Start the API Designer using the following command:
  ```
  $ apic endpoint
  Express server listening on http://127.0.0.1:9000
  ```
  {:codeblock}

   2. Log in to {{site.data.keyword.Bluemix_notm}} with your ID and password.
   3. Copy your Swagger or YAML file into your project directory where you downloaded the extension files.

3. Add the AES Extensions:
   1. In the API Edit screen, scroll down to the Extensions section and click the Add icon (+). A window will appear with a list of extensions to add.
   2. Click *API Explorer MetaData (1.0.0) aes-metadata* and *Done*.

### Uploading and extending your API definition files

If you generate your API definition files (JSON or YAML) automatically or manually code them using the API Connect toolkit, you must import the files into the API Connect and then the AES Console. After you have imported the API into the API Explorer catalog, you should customize your API docs.


1. Log in to the AES Console using your Intranet ID and password:
   * Staging: [https://apiexplorer.swg.usma.ibm.com/test/fabric/index.html ![External link icon](../icons/launch-glyph.svg)](https://apiexplorer.swg.usma.ibm.com/test/fabric/index.html){: new_window} 
   * Production: [https://apiexplorer2.swg.usma.ibm.com/fabric/index.html ![External link icon](../icons/launch-glyph.svg)](https://apiexplorer2.swg.usma.ibm.com/fabric/index.html){: new_window}

   **NOTE:** {{site.data.keyword.Bluemix_notm}} only uses the production instance of API Explorer for both staging and production REST API Docs.

2. Import your API into the API Explorer Catalog:
   1. Click *Import* in the banner.
   2. Click *Swagger / YAML* for the source of the API, and then *YAML* or *JSON* for the Format.
   3. Click *Browse*. Locate your definition file, and click *Open*.
   4. Click *Start Importing* to add the file to the catalog.

3. Customize the API content so that the information is displayed properly in {{site.data.keyword.Bluemix_notm}} and as completely as possible to the users:
 - Config, Draft, and Production:
    - Select **Config** when you are drafting the REST API Docs but do not want them to show in the Bluemix REST API microservice (staging or production).
    - Select **Draft** when you are ready for your REST API Docs to show in staging only.
    - Select **Publish** when you are ready for your REST API Docs to start publishing in production. Docs set with Publish will also show in staging.
  - Company name: Enter **IBM**
  - Image: Import the SVG you want to use in the {{site.data.keyword.Bluemix_notm}} catalog
  - Backend server status:
    - Set to **Stage_Preview** for **Experimental** services
    - Set to **Stage_Beta** for **BETA** services
    - Set to **Stage_Live** for **GA** services
  - Link to product: Link to the catalog details page for your service. You can get the URL by going to {{site.data.keyword.Bluemix_notm}} catalog and selecting **View more**.
  - External Documentation Links: Add links to the service docs in the {{site.data.keyword.Bluemix_notm}} doc app.
  - Technology: Select the metadata value for your service.
  - Namespace: Select **bluemix** to define that your service should be pulled into the {{site.data.keyword.Bluemix_notm}} REST API microservice. To have your API docs show in the API Explorer catalog too, select **apiexplorer** from the list also. (If you select nothing, your API will appear in the API Explorer by default.)
  - Bluemix: Select the category your service belongs to. If you don't set this, your API docs will not show in the {{site.data.keyword.Bluemix_notm}} REST API microservice.
  - API Ownership: Add any additional users who can edit and update the API documentation.

4. Click **Save only** or **Save and Continue to Endpoint Definition** to save changes. After customizing the API doc, you could export at any time in a Swagger.JSON format. Click the **Export JSON** link in the upper right corner on your API docs home page.
