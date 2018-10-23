---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 映像

使用以下命令可管理 {{site.data.keyword.Bluemix}} 计算映像。
{: shortdesc}

<table summary="按字母顺序排序的 {{site.data.keyword.Bluemix_notm}} 基础架构映像命令（命令带有可获取命令更多信息的链接）">
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

删除映像。
```
ibmcloud sl image delete IDENTIFIER
```
**示例**：
```
   ibmcloud sl image delete 12345678
```
此命令删除标识为 `12345678` 的映像。



## ibmcloud sl image detail
{: #sl_image_detail}

获取映像的详细信息。
```
ibmcloud sl image detail IDENTIFIER
```
**示例**：
```
 ibmcloud sl image detail 12345678
```
此命令获取标识为 12345678 的映像的详细信息。



## ibmcloud sl image edit
{: #sl_image_edit}

编辑映像的详细信息。
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--name</dt>
<dd>映像的名称。</dd>
<dt>--note</dt>
<dd>映像的其他注释。</dd>
<dt>--tag</dt>
<dd>映像的标记。</dd>
</dl>

*示例**：
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
此命令编辑标识为 `12345678` 的映像，并将其名称设置为 `ubuntu16`，注释设置为 `testing`，标记设置为 `staging`。




## ibmcloud sl image list
{: #sl_image_list}

列出帐户的所有映像。
```
ibmcloud sl image list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--name</dt>
<dd>过滤映像名称。</dd>
<dt>--public</dt>
<dd>仅显示公用映像。</dd>
<dt>--private</dt>
<dd>仅显示专用映像。</dd>
</dl>
