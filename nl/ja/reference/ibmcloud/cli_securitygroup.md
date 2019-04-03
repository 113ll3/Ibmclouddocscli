---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: manage security groups, ingress, egress, traffic, virtual server, classic infrastructure, securitygroup, ibmcloud sl securitygroup

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 仮想サーバー・トラフィックのセキュリティー・グループの管理
{: #sl-manage-securitygroups}

セキュリティー・グループとは、仮想サーバー・インスタンスのパブリック・インターフェースとプライベート・インターフェースの両方について、入力 (ingress) および出力 (egress) トラフィックを処理する方法を定義する一連の IP フィルター・ルールです。 セキュリティー・グループに追加するルールをセキュリティー・グループ・ルールと呼びます。

以下のコマンドを使用して、{{site.data.keyword.cloud}} クラシック・インフラストラクチャーのセキュリティー・グループ・サービスを使用してセキュリティー・グループを管理します。
{: shortdesc}

## ibmcloud sl securitygroup create
{: #sl_securitygroup_create}

セキュリティー・グループを作成します。
```
ibmcloud sl securitygroup create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --name</dt>
<dd>セキュリティー・グループの名前。</dd>
<dt>-d, --description</dt>
<dd>セキュリティー・グループの説明。</dd>
</dl>

## ibmcloud sl securitygroup delete
{: #sl_securitygroup_delete}

指定されたセキュリティー・グループを削除します。
```
ibmcloud sl securitygroup delete SECURITYGROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

## ibmcloud sl securitygroup detail
{: #sl_securitygroup_detail}

セキュリティー・グループについての詳細を取得します。
```
ibmcloud sl securitygroup detail SECURITYGROUP_ID [OPTIONS]
```

## ibmcloud sl securitygroup edit
{: #sl_securitygroup_edit}

セキュリティー・グループの詳細を編集します。
```
ibmcloud sl securitygroup edit SECURITYGROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --name</dt>
<dd>セキュリティー・グループの名前。</dd>
<dt>-d, --description</dt>
<dd>セキュリティー・グループの説明。</dd>
</dl>

## ibmcloud sl securitygroup interface-add
{: #sl_securitygroup_interface_add}

インターフェースにセキュリティー・グループを接続します。
```
ibmcloud sl securitygroup interface-add SECURITYGROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --network-component</dt>
<dd>セキュリティー・グループに関連付けるネットワーク・コンポーネント ID。</dd>
<dt>-s, --server</dt>
<dd>セキュリティー・グループに関連付けるサーバー ID。</dd>
<dt>-i, --interface</dt>
<dd>関連付けるサーバーのインターフェース (パブリック/プライベート)。</dd>
</dl>

## ibmcloud sl securitygroup interface-list
{: #sl_securitygroup_interface_list}

セキュリティー・グループに関連付けられたインターフェースをリストします。
```
ibmcloud sl securitygroup interface-list SECURITYGROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、virtualServerId、hostname。</dd>
</dl>

## ibmcloud sl securitygroup interface-remove
{: #sl_securitygroup_interface_remove}

セキュリティー・グループからインターフェースを切り離します。
```
ibmcloud sl securitygroup interface-remove SECURITYGROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --network-component</dt>
<dd>セキュリティー・グループから削除するネットワーク・コンポーネント。</dd>
<dt>-s, --server</dt>
<dd>セキュリティー・グループから削除するサーバー ID。</dd>
<dt>-i, --interface</dt>
<dd>削除するサーバーのインターフェース (パブリック/プライベート)。</dd>
</dl>

## ibmcloud sl securitygroup list
{: #sl_securitygroup_list}

セキュリティー・グループをリストします。
```
List security groups
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、description、created。</dd>
</dl>

## ibmcloud sl securitygroup rule-add
{: #sl_securitygroup_rule_add}

セキュリティー・グループにセキュリティー・グループ・ルールを追加します。
```
ibmcloud sl securitygroup rule-add SECURITYGROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-r, --remote-ip</dt>
<dd>強制するリモート IP/CIDR。</dd>
<dt>-s, --remote-group</dt>
<dd>強制するリモート・セキュリティー・グループの ID。</dd>
<dt>-d, --direction</dt>
<dd>強制するトラフィックの方向 (ingress、egress)、必須。</dd>
<dt>-e, --ether-type</dt>
<dd>強制するイーサネット・タイプ (IPv4 または IPv6)。デフォルトは IPv4 です (指定されていない場合)。</dd>
<dt>-M, --port-max</dt>
<dd>強制するバインド済み上部ポート。</dd>
<dt>-m, --port-min</dt>
<dd>強制するバインド済み下部ポート。</dd>
<dt>-p, --protocol</dt>
<dd>強制するプロトコル (icmp、tcp、udp)。</dd>
</dl>

## ibmcloud sl securitygroup rule-edit
{: #sl_securitygroup_rule_edit}

セキュリティー・グループ内のセキュリティー・グループ・ルールを編集します。
```
ibmcloud sl securitygroup rule-edit SECURITYGROUP_ID RULE_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-r, --remote-ip</dt>
<dd>強制するリモート IP/CIDR。</dd>
<dt>-s, --remote-group</dt>
<dd>強制するリモート・セキュリティー・グループの ID。</dd>
<dt>-d, --direction</dt>
<dd>強制するトラフィックの方向 (ingress、egress)、必須。</dd>
<dt>-e, --ether-type</dt>
<dd>強制するイーサネット・タイプ (IPv4 または IPv6)。デフォルトは IPv4 です (指定されていない場合)。</dd>
<dt>-M, --port-max</dt>
<dd>強制するバインド済み上部ポート。</dd>
<dt>-m, --port-min</dt>
<dd>強制するバインド済み下部ポート。</dd>
<dt>-p, --protocol</dt>
<dd>強制するプロトコル (icmp、tcp、udp)。</dd>
</dl>

## ibmcloud sl securitygroup rule-list
{: #sl_securitygroup_rule_list}

セキュリティー・グループ・ルールをリストします。
```
ibmcloud sl securitygroup rule-list SECURITYGROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準にする列。オプション: id、remoteIp、remoteGroupId、direction、ethertype、portRangeMin、portRangeMax、protocol。</dd>
</dl>

## ibmcloud sl securitygroup rule-remove
{: #sl_securitygroup_rule_remove}

セキュリティー・グループからルールを削除します。
```
ibmcloud sl securitygroup rule-remove SECURITYGROUP_ID RULE_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>
