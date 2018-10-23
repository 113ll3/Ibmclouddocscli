---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 安全性

利用 SSH 密钥，无需使用密码即可从在设备上实现的每个公用密钥所对应的客户机来访问设备。通过向设备添加 SSH 密钥，随 SSH 密钥一起提供的设备无需使用密码即可访问该设备以获取相应的密钥。

SSL 证书是 Web 站点启用的一种安全措施，用来保护用户。需要将机密信息传输到 Web 站点时，通常会使用 SSL 证书。

使用以下命令可管理 {{site.data.keyword.Bluemix}} 基础架构 SSH 密钥和证书。
{: shortdesc}

<table summary="按字母顺序排序的 {{site.data.keyword.Bluemix_notm}} 基础架构安全命令（命令带有可获取命令更多信息的链接）">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl security sshkey-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_add)</td>
  <td>[ibmcloud sl security sshkey-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_edit)</td>
  <td>[ibmcloud sl security sshkey-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_list)</td>
  <td>[ibmcloud sl security sshkey-print](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_print)</td>
  <td>[ibmcloud sl security sshkey-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl security cert-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_add)</td>
  <td>[ibmcloud sl security cert-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_edit)</td>
  <td>[ibmcloud sl security cert-download](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_download)</td>
  <td>[ibmcloud sl security cert-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_list)</td>
  <td>[ibmcloud sl security cert-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

添加新的 SSH 密钥。
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --in-file</dt>
<dd>要为此密钥导入的 id_rsa.pub 文件。</dd>
<dt>-k, --key</dt>
<dd>实际 SSH 密钥。</dd>
<dt>--note</dt>
<dd>将与密钥关联的额外注释。</dd>
</dl>

**示例**：
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
此命令从 ~/.ssh/id_rsa.pub 文件添加 SSH 密钥，注释为“mykey”。



## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

编辑 SSH 密钥。
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--label</dt>
<dd>密钥的新标签。</dd>
<dt>--note</dt>
<dd>密钥的新注释。</dd>
</dl>

**示例**：
```
ibmcloud sl security sshkey-edit 12345678 --label ibmcloud --note testing
```
此命令更新标识为 12345678 的 SSH 密钥，并将标签设置为“ibmcloud”，注释设置为“testing”。

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

列出帐户的 SSH 密钥。
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要作为排序依据的列，选项为：id、label、fingerprint 或 notes。</dd>
</dl>

**示例**：
```
ibmcloud sl security sshkey-list --sortby label
```
此命令列出当前帐户的所有 SSH 密钥，并按标签对其排序。



## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

将 SSH 密钥输出到屏幕。
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --out-file</dt>
<dd>公用 SSH 密钥将写入此文件。</dd>
</dl>

**示例**：
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
此命令显示标识为 12345678 的 SSH 密钥的标识、标签和注释，并将公用密钥写入 ~/mykey.pub 文件。



## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

永久除去 SSH 密钥。
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl security sshkey-remove 12345678 -f
```
此命令除去标识为 12345678 的 SSH 密钥，而不要求确认。



## ibmcloud sl security cert-add
{: #sl_security_cert_add}

添加和上传 SSL 证书详细信息。
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--crt</dt>
<dd>证书文件。</dd>
<dt>--csr</dt>
<dd>证书签名请求文件。</dd>
<dt>--icc</dt>
<dd>中间证书文件。</dd>
<dt>--key</dt>
<dd>专用密钥文件。</dd>
<dt>--notes</dt>
<dd>其他注释。</dd>
</dl>

**示例**：
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
此命令为域 ibm.com 添加证书文件 ~/ibm.com.cert 和专用密钥文件 ~/ibm.com.key。

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

编辑 SSL 证书。
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--crt</dt>
<dd>证书文件。</dd>
<dt>--csr</dt>
<dd>证书签名请求文件。</dd>
<dt>--icc</dt>
<dd>中间证书文件。</dd>
<dt>--key</dt>
<dd>专用密钥文件。</dd>
<dt>--notes</dt>
<dd>其他注释。</dd>
</dl>

**示例**：
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
此命令编辑标识为 12345678 的证书，并使用 ~/ibm.com.key 文件更新其专用密钥。

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

下载 SSL 证书和密钥文件。
```
ibmcloud sl security cert-download IDENTIFIER
```


**示例**：
```
ibmcloud sl security cert-download 12345678
```
此命令将 4 个文件下载到标识为 12345678 的证书所在的当前目录。这 4 个文件为：证书文件、证书签名请求文件、中间证书文件和专用密钥文件。



## ibmcloud sl security cert-list
{: #sl_security_cert_list}

列出帐户的 SSL 证书。
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--status</dt>
<dd>显示具有此状态的证书，缺省值为：all，选项为： all、valid 或 expired。</dd>
<dt>--sortby</dt>
<dd>要作为排序依据的列，选项为：id、common_name、days_until_expire 或 notes。</dd>
</dl>

**示例**：
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
此命令列出当前帐户的所有有效证书，并按有效天数对其排序。



## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

除去 SSL 证书。
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl security cert-remove 12345678
```
此命令除去标识为 12345678 的证书。
