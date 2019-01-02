---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# IPSec VPN トンネルの管理

{{site.data.keyword.Bluemix}} VPN アクセスにより、ユーザーは、すべてのサーバーを {{site.data.keyword.Bluemix_notm}} プライベート・ネットワーク経由でセキュアにリモート管理できます。 お客様のロケーションからプライベート・ネットワークへの VPN 接続により、暗号化された VPN トンネル経由でのアウト・オブ・バンド管理とサーバー・レスキューが可能になります。

以下のコマンドを使用して、{{site.data.keyword.Bluemix_notm}} クラシック・インフラストラクチャーの IPSec VPN サービスの IPSec VPN トンネルを管理します。
{: shortdesc}

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の {{site.data.keyword.Bluemix_notm}} IPSec VPN コマンド">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl ipsec cancel](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_cancel)</td>
 <td>[ibmcloud sl ipsec config](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_config)</td>
 <td>[ibmcloud sl ipsec detail](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_detail)</td>
 <td>[ibmcloud sl ipsec list](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_list)</td>
 <td>[ibmcloud sl ipsec order](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_order)</td>
 <td>[ibmcloud sl ipsec subnet-add](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_subnet_add)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl ipsec subnet-remove](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_subnet_remove)</td>
 <td>[ibmcloud sl ipsec translation-add](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_translation_add)</td>
 <td>[ibmcloud sl ipsec translation-remove](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_translation_remove)</td>
 <td>[ibmcloud sl ipsec translation-update](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_translation_update)</td>
 <td>[ibmcloud sl ipsec update](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_update)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

IPSec VPN トンネル・コンテキストを取り消します。
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--immediate</dt>
<dd>請求応答日ではなく即時に、IPSec を取り消します。</dd>
<dt>--reason</dt>
<dd>取り消しの理由 (オプション)。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

## ibmcloud sl ipsec config
{: #sl_ipsec_config}

トンネル・コンテキストの構成を要求します。
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

IPSec VPN トンネル・コンテキストの詳細をリストします。
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-i, --include</dt>
<dd>追加リソースを組み込みます。オプション: at、is、rs、sr、ss。</dd>
</dl>

## ibmcloud sl ipsec list
{: #sl_ipsec_list}

IPSec VPN トンネル・コンテキストをリストします。
```
ibmcloud sl ipsec list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--order</dt>
<dd>IPSEC を購入した注文の ID を基準にフィルター操作します。</dd>
</dl>

## ibmcloud sl ipsec order
{: #sl_ipsec_order}

IPSec VPN トンネルを注文します。
```
ibmcloud sl ipsec order [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>必須。 IPSEC 用のデータ・センターの短縮名。例えば、dal09 など。</dd>
</dl>

## ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

IPSec トンネル・コンテキストにサブネットを追加します。
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>追加するサブネット ID (必須)。</dd>
<dt>-t, --subnet-type</dt>
<dd>追加するサブネット・タイプ (必須)。オプション: internal、remote、service。</dd>
<dt>-n, --network</dt>
<dd>作成するサブネット・ネットワーク ID。</dd>
</dl>

## ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

IPSEC トンネル・コンテキストからサブネットを削除します。
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

## ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

IPSec トンネルにアドレス変換を追加します。
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>静的 IP アドレス (必須)。</dd>
<dt>-r, --remote-ip</dt>
<dd>リモート IP アドレス (必須)。</dd>
<dt>-n, --note</dt>
<dd>注。</dd>
</dl>

## ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

IPSec から変換入力を削除します。
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

## ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

IPSec のアドレス変換を更新します。
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>静的 IP アドレス (必須)。</dd>
<dt>-r, --remote-ip</dt>
<dd>リモート IP アドレス (必須)。</dd>
<dt>-n, --note</dt>
<dd>注。</dd>
</dl>

## ibmcloud sl ipsec update
{: #sl_ipsec_update}

トンネル・コンテキストのプロパティーを更新します。
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --name</dt>
<dd>分かりやすい名前。</dd>
<dt>-r, --remote-peer</dt>
<dd>リモート・ピア IP アドレス。</dd>
<dt>-k, --preshared-key</dt>
<dd>事前共有鍵。</dd>
<dt>-a, --phase1-auth</dt>
<dd>フェーズ 1 認証。オプション: MD5、SHA1、SHA256。</dd>
<dt>-c, --phase1-crypto</dt>
<dd>フェーズ 1 暗号化。オプション: DES、3DES、AES128、AES192、AES256。</dd>
<dt>-d, --phase1-dh</dt>
<dd>フェーズ 1 Diffie-Hellman グループ。オプション: 0、1、2、5。</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>フェーズ 1 鍵存続時間。範囲: 120-172800。</dd>
<dt>-u, --phase2-auth</dt>
<dd>フェーズ 2 認証。オプション: MD5、SHA1、SHA256。</dd>
<dt>-y, --phase2-crypto</dt>
<dd>フェーズ 2 暗号化。オプション: DES、3DES、AES128、AES192、AES256。</dd>
<dt>-e, --phase2-dh</dt>
<dd>フェーズ 2 Diffie-Hellman グループ。オプション: 0、1、2、5。</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>フェーズ 2 Perfect Forward Secrecy。範囲: 0-1。</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>フェーズ 2 鍵存続時間。範囲: 120-172800。</dd>
</dl>
