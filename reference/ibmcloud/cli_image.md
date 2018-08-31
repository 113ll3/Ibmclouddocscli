---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} infrastructure Image

Use the following commands to manage {{site.data.keyword.Bluemix_notm}} infrastructure images.
{: shortdesc}

<table summary="Alphabetically ordered  {{site.data.keyword.Bluemix_notm}} infrastructure Image commands that have links that bring you to more info for the command">
 <tbody>
 <tr>
 <td>[ibmcloud sl image delete](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_delete)</td>
 <td>[ibmcloud sl image detail](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_detail)</td>
 <td>[ibmcloud sl image edit](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_edit)</td>
 <td>[ibmcloud sl image list](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl image delete
{: #sl_image_delete}

Delete an image.
```
ibmcloud sl image delete IDENTIFIER
```
**Examples**:
```
   ibmcloud sl image delete 12345678
```
This command deletes image with ID `12345678`.

## ibmcloud sl image detail
{: #sl_image_detail}

Get details for an image.
```
ibmcloud sl image detail IDENTIFIER
```
**Examples**:
```
 ibmcloud sl image detail 12345678
```
This command gets details for image with ID 12345678.

## ibmcloud sl image edit
{: #sl_image_edit}

Edit details of an image.
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--name</dt>
<dd>Name of the image.</dd>
<dt>--note</dt>
<dd>Additional note for the image.</dd>
<dt>--tag</dt>
<dd>Tags for the image.</dd>
</dl>

*Examples**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
This command edits image with ID `12345678` and set its name to `ubuntu16`, note to `testing`, and tag to `staging`.

## ibmcloud sl image list
{: #sl_image_list}

List all images on your account.
```
ibmcloud sl image list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--name</dt>
<dd>Filter on image name.</dd>
<dt>--public</dt>
<dd>Display only public images.</dd>
<dt>--private</dt>
<dd>Display only private images.</dd>
</dl>
