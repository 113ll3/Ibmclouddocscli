---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 安全

請使用下列指令管理 {{site.data.keyword.Bluemix_notm}} 基礎架構 SSH 金鑰及憑證。
{: shortdesc}

<table summary="按字母順序排序的 {{site.data.keyword.Bluemix_notm}} 基礎架構安全指令，其鏈結提供指令的相關資訊">
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

新增 SSH 金鑰。
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --in-file</dt>
<dd>要為此金鑰匯入的 id_rsa.pub 檔案。</dd>
<dt>-k, --key</dt>
<dd>實際 SSH 金鑰。</dd>
<dt>--note</dt>
<dd>將與金鑰相關聯的額外附註。</dd>
</dl>

**範例**：
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
這個指令會從檔案 ~/.ssh/id_rsa.pub 新增 SSH 金鑰及附註 "mykey"。


## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

編輯 SSH 金鑰。
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--label</dt>
<dd>金鑰的新標籤。</dd>
<dt>--note</dt>
<dd>金鑰的新附註。</dd>
</dl>

**範例**：
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
這個指令會更新 ID 為 12345678 的 SSH 金鑰、將標籤設為 "Bluemix"，並將附註設為 "testing"。

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

列出您帳戶上的 SSH 金鑰。
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--sortby</dt>
<dd>直欄排序方式，選項包含：id、label、fingerprint、notes。</dd>
</dl>

**範例**：
```
ibmcloud sl security sshkey-list --sortby label
```
 這個指令會列出現行帳戶上的所有 SSH 金鑰，並依標籤排序。

## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

將 SSH 金鑰印出至螢幕。
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --out-file</dt>
<dd>公用 SSH 金鑰將會寫入此檔案。</dd>
</dl>

**範例**：
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
這個指令會顯示 ID 為 12345678 的 SSH 金鑰的 ID、標籤及附註，並將公開金鑰寫入檔案：~/mykey.pub。

## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

永久移除 SSH 金鑰。
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl security sshkey-remove 12345678 -f
```
 這個指令會移除 ID 為 12345678 的 SSH 金鑰，而不要求確認。

## ibmcloud sl security cert-add
{: #sl_security_cert_add}

新增及上傳 SSL 憑證詳細資料。
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--crt</dt>
<dd>憑證檔。</dd>
<dt>--csr</dt>
<dd>憑證簽署要求檔。</dd>
<dt>--icc</dt>
<dd>中繼憑證檔。</dd>
<dt>--key</dt>
<dd>私密金鑰檔。</dd>
<dt>--notes</dt>
<dd>其他附註。</dd>
</dl>

**範例**：
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
這個指令會新增網域 ibm.com 的憑證檔 ~/ibm.com.cert 及私密金鑰檔 ~/ibm.com.key。

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

編輯 SSL 憑證。
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--crt</dt>
<dd>憑證檔。</dd>
<dt>--csr</dt>
<dd>憑證簽署要求檔。</dd>
<dt>--icc</dt>
<dd>中繼憑證檔。</dd>
<dt>--key</dt>
<dd>私密金鑰檔。</dd>
<dt>--notes</dt>
<dd>其他附註。</dd>
</dl>

**範例**：
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
這個指令會編輯 ID 為 12345678 的憑證，並以檔案 ~/ibm.com.key 來更新其私密金鑰。

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

下載 SSL 憑證及金鑰檔。
```
ibmcloud sl security cert-download IDENTIFIER
```


**範例**：
```
ibmcloud sl security cert-download 12345678
```
  這個指令會將 4 個檔案下載至 ID 為 12345678 的憑證的現行目錄。這 4 個檔案分別為：憑證檔、憑證簽署要求檔、中繼憑證檔及私密金鑰檔。

## ibmcloud sl security cert-list
{: #sl_security_cert_list}

列出您帳戶上的 SSL 憑證。
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--status</dt>
<dd>顯示具有以下狀態的憑證，預設值為：all，選項包含：all、valid、expired。</dd>
<dt>--sortby</dt>
<dd>直欄排序方式，選項包含：id、common_name、days_until_expire、notes。</dd>
</dl>

**範例**：
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
 這個指令會列出現行帳戶上的所有有效憑證，並依有效天數排序。

## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

移除 SSL 憑證。
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl security cert-remove 12345678
```
 這個指令會移除 ID 為 12345678 的憑證。
