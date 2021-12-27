---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, classic infrastructure, ibmcloud sl image, manage compute images, create compute image cli, compute image cli

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Creating, editing, and deleting compute images (ibmcloud sl image)
{: #sl-manage-compute-images}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} compute images.
{: shortdesc}

## ibmcloud sl image delete
{: #sl_image_delete}

Delete an image:
```bash
ibmcloud sl image delete IDENTIFIER
```

**Examples**:
```bash
ibmcloud sl image delete 12345678
```
{: codeblock}

This command deletes image with ID `12345678`.

## ibmcloud sl image detail
{: #sl_image_detail}

Get details for an image:
```bash
ibmcloud sl image detail IDENTIFIER 
```

**Examples**:
```bash
ibmcloud sl image detail 12345678
```
{: codeblock}

This command gets details for image with ID `12345678`.

## ibmcloud sl image edit
{: #sl_image_edit}

Edit the details of an image:
```bash
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

**Command options**:

--name
:   Name of the image.

--note
:   Add notes for the image.

--tag
:   Tags for the image.

**Examples**:
```bash
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
{: codeblock}

This command edits an image with ID `12345678` and set its name to `ubuntu16`, note to `testing`, and tag to `staging`.

## ibmcloud sl image list
{: #sl_image_list}

List all images on your account:
```bash
ibmcloud sl image list [OPTIONS]
```

**Command options**:

--name
:   Filter on image name.

--public
:   Display only public images.

--private
:   Display only private images.

**Examples**:
```bash
ibmcloud sl image list --public
```
{: codeblock}

This command list all public images on current account.

