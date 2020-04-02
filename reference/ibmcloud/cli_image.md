---

copyright:
  years: 2018, 2020
lastupdated: "2020-03-31"

keywords: cli, classic infrastructure, ibmcloud sl image, manage compute images, create compute image cli, compute image cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Creating, editing, and deleting compute images (ibmcloud sl image)
{: #sl-manage-compute-images}

Use the following commands to manage {{site.data.keyword.cloud}} compute images.
{: shortdesc}

## ibmcloud sl image delete
{: #sl_image_delete}

Delete an image:
```
ibmcloud sl image delete IDENTIFIER
```

**Examples**:
```
ibmcloud sl image delete 12345678
```
{: codeblock}

This command deletes image with ID `12345678`.

## ibmcloud sl image detail
{: #sl_image_detail}

Get details for an image:
```
ibmcloud sl image detail IDENTIFIER 
```

**Examples**:
```
ibmcloud sl image detail 12345678
```
{: codeblock}

This command gets details for image with ID `12345678`.

## ibmcloud sl image edit
{: #sl_image_edit}

Edit the details of an image:
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--name</dt>
<dd>Name of the image.</dd>
<dt>--note</dt>
<dd>Add notes for the image.</dd>
<dt>--tag</dt>
<dd>Tags for the image.</dd>
</dl>

**Examples**:
```
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
{: codeblock}

This command edits an image with ID `12345678` and set its name to `ubuntu16`, note to `testing`, and tag to `staging`.

## ibmcloud sl image list
{: #sl_image_list}

List all images on your account:
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

**Examples**:
```
ibmcloud sl image list --public
```
{: codeblock}

This command list all public images on current account.

