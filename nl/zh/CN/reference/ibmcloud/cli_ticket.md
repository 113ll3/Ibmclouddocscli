---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 管理经典基础架构凭单
{: #manage-sl-tickets}

使用以下命令可管理 {{site.data.keyword.cloud}} 经典基础架构凭单。
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

要将设备附加到凭单，请执行以下操作：
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--hardware</dt>
<dd>要附加的硬件的标识。</dd>
<dt>--virtual</dt>
<dd>要附加的虚拟服务器的标识。</dd>
</dl>

**示例**：
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

要创建支持凭单，请执行以下操作：
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--attachment</dt>
<dd>要附加到凭单的初始对象标识号。</dd>
<dt>--rootpwd</dt>
<dd>与附加的设备标识关联的 root 用户密码。</dd>
<dt>--subject-id</dt>
<dd>必需。要用于凭单的主题标识，发出 `ibmcloudsl ticket subjects` 以获取列表。</dd>
<dt>--title</dt>
<dd>必需。凭单的标题。</dd>
<dt>--body</dt>
<dd>凭单主体。</dd>
<dt>--priority</dt>
<dd>凭单优先级 [1|2|3|4]，从 1（关键）到 4（最小影响）。仅具有高级和高端支持时可设置。请参阅 https://www.ibm.com/cloud/support。</dd>
<dt>--attachment-type</dt>
<dd>指定类型 attachment、hardware 或 virtual。缺省值为 hardware。</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

要从凭单拆离设备，请执行以下操作：
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--hardware</dt>
<dd>要拆离的硬件的标识。</dd>
<dt>--virtual</dt>
<dd>要拆离的虚拟服务器的标识。</dd>
</dl>

**示例**：
```
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail 
{: #sl_ticket_detail} 

要查看凭单详细信息，请执行以下操作：
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--count</dt>
<dd>更新数。</dd>
</dl>

**示例**：
```
ibmcloud sl ticket detail 767676
```
{: codeblock}

```
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list 
{: #sl_ticket_list} 

要列出凭单，请执行以下操作：
```
ibmcloud sl ticket list[OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--open</dt>
<dd>仅显示打开的凭单。</dd>
<dt>--closed</dt>
<dd>仅显示已关闭的凭单。</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

要列出用于创建凭单的主题标识，请执行以下操作：
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

要查看有关凭单的摘要信息，请执行以下操作：
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

要向现有凭单添加更新，请执行以下操作：
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**示例**：
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

要将附件添加到现有凭单，请执行以下操作：
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>命令选项</strong>：
<dl>
<dt>--name</dt>
<dd>凭单中显示的附件的名称。</dd>
</dl>

**示例**：
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

