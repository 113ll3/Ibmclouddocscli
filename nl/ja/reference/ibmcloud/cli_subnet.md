---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: manage subnets, classic infrastructure, subnets, ibmcloud sl subnet

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# サブネットの作成、取り消し、および表示
{: #sl-manage-subnets}

サブネットは、IP ネットワークの論理区画であり、複数の小さいネットワーク・セグメントに分割されます。 以下のコマンドを使用して、{{site.data.keyword.cloud}} クラシック・インフラストラクチャーのサブネットを管理します。
{: shortdesc}

## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

サブネットを取り消します。
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl subnet cancel 12345678 -f
```
このコマンドは、ID `12345678` のサブネットを、確認を求めずに取り消します。

## ibmcloud sl subnet create
{: #sl_subnet_create}

ご使用のアカウントに新規サブネットを追加します。
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>IPv6 アドレスを注文します。</dd>
<dt>--test</dt>
<dd>サブネットを注文せず、見積もりを取るだけです。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl subnet create public 16 567
```
{: codeblock}

このコマンドは、16 個の IPv4 アドレスを持つパブリック・サブネットを作成し、ID `567` の VLAN に配置します。

## ibmcloud sl subnet detail
{: #sl_subnet_detail}

サブネットの詳細を取得します。
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--no-vs</dt>
<dd>仮想サーバー・リストを非表示にします。</dd>
<dt>--no-hardware</dt>
<dd>ハードウェア・リストを非表示にします。</dd>
</dl>

**例**:
```
ibmcloud sl subnet detail 12345678
```
{: codeblock}

このコマンドは、仮想サーバーおよびハードウェア・サーバーの情報を含め、ID `12345678` のサブネットに関する詳細情報を表示します。

## ibmcloud sl subnet list
{: #sl_subnet_list}

ご使用のアカウントのすべてのサブネットをリストします。
```
ibmcloud sl subnet list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準にする列。 オプション: id、identifier、type、network_space、datacenter、vlan_id、IPs、hardware、vs。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>--identifier</dt>
<dd>ネットワーク ID を基準にフィルター操作します。</dd>
<dt>-t, --subnet-type</dt>
<dd>サブネット・タイプを基準にフィルター操作します。</dd>
<dt>--network-space</dt>
<dd>ネットワーク・スペースを基準にフィルター操作します。</dd>
<dt>--v4, --ipv4</dt>
<dd>IPv4 サブネットのみを表示します。</dd>
<dt>--v6, --ipv6</dt>
<dd>IPv6 サブネットのみを表示します。</dd>
<dt>--order</dt>
<dd>サブネットを購入した注文の ID を基準にフィルター操作します。</dd>
</dl>

**例**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
{: codeblock}

このコマンドは、現行アカウントの IP V4 サブネットをリストします。フィルター基準のデータ・センターは `dal09`、サブネット・タイプは `PRIMARY`、およびネットワーク・スペースは `PUBLIC` です。

## ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

IP アドレスを検出し、そのサブネットとデバイスの情報を表示します。
```
ibmcloud sl subnet lookup IP_ADDRESS
```

**例**:
```
ibmcloud sl subnet lookup 9.125.235.255
```
{: codeblock}

このコマンドは、IP アドレス `9.125.235.255` の IP アドレス・レコードを検出し、そのサブネットとデバイスの情報を表示します。
