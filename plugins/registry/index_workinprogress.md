---



copyright:

  years: 2017

lastupdated: "2017-03-02"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# {{site.data.keyword.registrylong}} CLI
{: #containerregcli}

The {{site.data.keyword.registrylong}} CLI is a plug-in that lets you manage your registry resources, such as namespaces, images, and quotas, across your org.
{: shortdesc}

**Prerequisites**
* Before running the registry commands, log in to {{site.data.keyword.Bluemix_short}}
 with `bx login` to generate a {{site.data.keyword.Bluemix_short}}
 access token and authenticate your session.

<table summary="Manage your Containers Registry">
<caption>Table 1. Commands for managing {{site.data.keyword.registryshort}} on {{site.data.keyword.Bluemix_short}}
</caption>
 <thead>
 <th colspan="5">Commands for managing the registry</th>
 </thead>
 <tbody>
 <tr>
 <td>[bx cr login](#bx-cr-login)</td>
 <td>[bx cr api](#bx-cr-api)</td>
 <td>[bx cr namespace-add](#bx-cr-namespace-add)</td>
 <td>[bx cr namespace-rm](#bx-cr-namespace-rm)</td>
 <td>[bx cr namespace-list](#bx-cr-namespace-list)</td>
 </tr>
 <tr>
 <td>[bx cr image-list](#bx-cr-image-list)</td>
 <td>[bx cr image-inspect](#bx-cr-image-inspect)</td>
 <td>[bx cr image-rm](#bx-cr-image-rm)</td>
 <td>[bx cr quota-usage](#bx-cr-quota-usage)</td>
 <td>[bx cr quota-set](#bx-cr-quota-set)</td>
 <tr>
 <td>[bx cr info](#bx-cr-info)</td>
 <td>[bx cr va](#bx-cr-va)</td>
 </tr>
 </tbody></table>

 
## bx cr login
If Docker is installed, this command runs `docker login` against the registry. `docker login` is required to be able to `docker push` or `docker pull` to the registry. This command is not required to run other `bx cr` commands. If Docker is not installed, this command returns an error message.

```
bx cr login
```
{: codeblock}

## bx cr api
Returns which registry API endpoint the commands are run against.

```
bx cr api
```
{: codeblock}

## bx cr namespace-add
Add a namespace to your Bluemix org. 

```
bx cr namespace-add NAMESPACE
```
{: codeblock}

**Parameters**
<dl>
<dt>NAMESPACE</dt>
<dd>The namespace you want to add. The namespace must be unique across all orgs.</dd>
</dl>

## bx cr namespace-rm
Removes a namespace from your Bluemix org. Images in this namespace are deleted when the namespace is removed.

```
bx cr namespace-rm NAMESPACE
```
{: codeblock}

**Parameters**
<dl>
<dt>NAMESPACE</dt>
<dd>The namespace you want to remove.</dd>
</dl>

## bx cr namespace-list
View all namespaces within by your {{site.data.keyword.Bluemix_short}} org. You can also run this command as `bx cr namespaces`.

```
bx cr namespace-list
```
{: codeblock}

 
## bx cr image-list
View all images in your {{site.data.keyword.Bluemix_short}} org. You can also run this command as `bx cr images`.

```
 bx cr image-list [--no-trunc] [-q, --quiet] [--ibm-list] [--format FORMAT]
```
{: codeblock}

**Parameters**
<dl>
<dt>--no-trunc</dt>
<dd>(Optional) Do not truncate the output.</dd>
<dt>-q, --quiet</dt>
<dd>(Optional) Displays a unique identifier for the image in the format: `repository:tag`.</dd>
<dt>--ibm-list</dt>
<dd>(Optional) Includes IBM-provided public images in the output. Without this option, private images are listed only.</dd>
<dt>--format FORMAT</dt>
<dd>(Optional) Format the output using a Go template. Strings: `Tag`, `Digest`, `Vulnerable`, `Namespace`. Integer (64 bit): `Created`, `Size`.</dd>
</dl>

## bx cr image-inspect
View details about a specific image.

```
bx cr image-inspect IMAGE [--format FORMAT]
```
{: codeblock}

**Parameters**
<dl>
<dt>IMAGE</dt>
<dd>The full {{site.data.keyword.Bluemix_short}} registry path to the image that you want to inspect.</dd>
<dt>--format FORMAT</dt>
<dd>(Optional) Format the output using a Go template. Strings: `Tag`, `Digest`, `Vulnerable`, `Namespace`. Integer (64 bit): `Created`, `Size`.</dd>
</dl>

## bx cr image-rm
Delete a specified image from your registry.

```
bx cr image-rm IMAGE
```
{: codeblock}

**Parameters**
<dl>
<dt>IMAGE</dt>
<dd>The full, private {{site.data.keyword.Bluemix_short}} registry path to the image that you want to remove. If a tag is not specified in the image path, the image tagged latest is deleted by default. You can run this command with multiple images by listing each private {{site.data.keyword.Bluemix_short}} registry path in the command with a space in between.</dd>
</dl>

## bx cr quota-usage
View your current quotas for traffic and storage, and current usage information against those quotas.

```
bx cr quota-usage
```
{: codeblock}

## bx cr quota-set
Modify the specified quota.

```
bx cr quota-set [--traffic VALUE] [--storage VALUE]
```
{: codeblock}

**Parameters**
<dl>
<dt>--traffic VALUE</dt>
<dd>(Optional) Changes your traffic quota to the specified value. The operation fails if you are not authorized to set traffic, or if you have not purchased the additional traffic.</dd>
<dt>--storage VALUE</dt>
<dd>(Optional) Changes your storage quota to the specified value. The operation fails if you are not authorized to set storage quotas, or if you have not purchased the additional storage.</dd>
</dl>

## bx cr va
View a vulnerability assessment report for an image.

```
bx cr va IMAGE [--format FORMAT]
```
{: codeblock}

**Parameters**
<dl>
<dt>IMAGE</dt>
<dd>The full {{site.data.keyword.Bluemix_short}} registry path to the image that you want to get a report for.</dd>
<dt>--format FORMAT</dt>
<dd>(Optional) Format the output using a Go template. Strings: `Tag`, `Digest`, `Vulnerable`, `Namespace`. Integer (64 bit): `Created`, `Size`.</dd>
</dl>

<!-- audience blue staging only begin comment -->
**Draft comment: Staging-only content below. Remove before production push.**

`bx cr image-build`: `cf ic build`
`bx cr image-cp`: `cf ic cpi`
`bx cr image-search`: Search your visible repo(s) for images.
`bx cr namespace-rm`: Delete a namespace from your org. When you remove a namespace from your org, you also delete all the images in that namespace.
`bx cr namespace-acl`: Access control list to set per-namespace permissions.
`bx cr info `: Display information about which registry, org, and namespace you are logged into.
`bx cr token-add/revoke/list`: Management of tokens used to authenticate with the registry. These kind of tokens are useful for users wanting to automate registry interactions in build jobs etc. Having a command to manage them would be nice.
`bx cr image-list` Lists all images, but undecided what to show as flags. TBC.

<!-- audience blue staging only end comment -->
    
