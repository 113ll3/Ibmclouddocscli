---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・セキュリティーの管理

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・コマンド">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・セキュリティー・コマンド</caption>

 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} インフラストラクチャー・セキュリティー・コマンド</th>
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

新規の SSH 鍵を追加します。
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --in-file</dt>
<dd>この鍵のためにインポートする id_rsa.pub ファイル。</dd>
<dt>-k, --key</dt>
<dd>実際の SSH 鍵。</dd>
<dt>--note</dt>
<dd>鍵に関連付けられる追加のメモ。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
このコマンドは、ファイル ~/.ssh/id_rsa.pub から SSH 鍵を、メモ「mykey」を付けて追加します。

## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

SSH 鍵を編集します。
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--label</dt>
<dd>鍵の新しいラベル。</dd>
<dt>--note</dt>
<dd>鍵についての新しいメモ。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
このコマンドは、ID 12345678 の SSH 鍵を更新し、ラベルを「Bluemix」に設定し、メモを「testing」に設定します。

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

ご使用のアカウントの SSH 鍵をリストします。
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、label、fingerprint、notes。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-list --sortby label
```
このコマンドは、現行アカウントのすべての SSH 鍵をリストし、それらをラベルによってソートします。

## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

SSH 鍵を画面に出力します。
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>SSH 公開鍵は、このファイルに書き込まれます。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
このコマンドは、ID 12345678 の SSH 鍵の ID、ラベル、およびメモを表示し、公開鍵をファイル ~/mykey.pub に書き込みます。

## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

SSH 鍵を永久に削除します。
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl security sshkey-remove 12345678 -f
```
このコマンドは、ID 12345678 の SSH 鍵を、確認を求めずに削除します。

## ibmcloud sl security cert-add
{: #sl_security_cert_add}

SSL 証明書の詳細を追加してアップロードします。
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--crt</dt>
<dd>証明書ファイル。</dd>
<dt>--csr</dt>
<dd>証明書署名要求ファイル。</dd>
<dt>--icc</dt>
<dd>中間証明書ファイル。</dd>
<dt>--key</dt>
<dd>秘密鍵ファイル。</dd>
<dt>--notes</dt>
<dd>追加のメモ。</dd>
</dl>

**例**:
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
このコマンドは、ドメイン ibm.com の証明書ファイル ~/ibm.com.cert と秘密鍵ファイル ~/ibm.com.key を追加します。

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

SSL 証明書を編集します。
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--crt</dt>
<dd>証明書ファイル。</dd>
<dt>--csr</dt>
<dd>証明書署名要求ファイル。</dd>
<dt>--icc</dt>
<dd>中間証明書ファイル。</dd>
<dt>--key</dt>
<dd>秘密鍵ファイル。</dd>
<dt>--notes</dt>
<dd>追加のメモ。</dd>
</dl>

**例**:
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
このコマンドは、ID 12345678 の証明書を編集し、ファイル ~/ibm.com.key でその秘密鍵を更新します。

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

SSL 証明書および鍵ファイルをダウンロードします。
```
ibmcloud sl security cert-download IDENTIFIER
```


**例**:
```
ibmcloud sl security cert-download 12345678
```
このコマンドは、現行ディレクトリーに ID 12345678 の証明書に関する 4 つのファイルをダウンロードします。 4 つのファイルというのは、証明書ファイル、証明書署名要求ファイル、中間証明書ファイル、および秘密鍵ファイルです。

## ibmcloud sl security cert-list
{: #sl_security_cert_list}

ご使用のアカウントの SSL 証明書をリストします。
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--status</dt>
<dd>指定の状況の証明書を表示します。デフォルトは all です。オプション: all、valid、expired。</dd>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、common_name、days_until_expire、notes。</dd>
</dl>

**例**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
このコマンドは、現行アカウントのすべての有効な証明書をリストし、それらを有効期限日によってソートします。

## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

SSL 証明書を削除します。
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl security cert-remove 12345678
```
このコマンドは、ID 12345678 の証明書を削除します。
