---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ipsec, vpn, ibmcloud sl ipsec, tunnel, vpn access, datacenter, encryption

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理 IPSec VPN 通道
{: #sl-manage-ipsec-vpn-tunnels}

{{site.data.keyword.cloud}} VPN 存取容許使用者透過 {{site.data.keyword.cloud_notm}} 專用網路，由遠端安全地管理所有伺服器。從您的位置至專用網路的 VPN 連線，讓您能透過已加密的 VPN 通道進行頻外管理，以及伺服器救援。

請使用下列指令在 {{site.data.keyword.cloud_notm}} 標準基礎架構 IPSec VPN 服務中管理 IPSec VPN 通道。
{: shortdesc}

## ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

取消 IPSec VPN 通道環境定義。
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--immediate</dt>
<dd>立即取消 IPSec，而不是在計費週年日取消。</dd>
<dt>--reason</dt>
<dd>選用性的取消原因。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl ipsec config
{: #sl_ipsec_config}

通道環境定義的要求配置。
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

列出 IPSec VPN 通道環境定義詳細資料。
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-i, --include</dt>
<dd>包括其他資源，選項包含：at、is、rs、sr、ss。</dd>
</dl>

## ibmcloud sl ipsec list
{: #sl_ipsec_list}

列出 IPSec VPN 通道環境定義。
```
ibmcloud sl ipsec list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--order</dt>
<dd>依購買 IPSEC 的訂單 ID 進行過濾。</dd>
</dl>

## ibmcloud sl ipsec order
{: #sl_ipsec_order}

訂購 IPSec VPN 通道。
```
ibmcloud sl ipsec order [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-d, --datacenter</dt>
<dd>必要。IPSEC 資料中心的簡稱，例如：dal09。</dd>
</dl>

## ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

將子網路新增至 IPSec 通道環境定義。
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-s, --subnet-id</dt>
<dd>要新增的子網路 ID，必要項目。</dd>
<dt>-t, --subnet-type</dt>
<dd>要新增的子網路類型，必要項目，選項包含：internal、remote、service。</dd>
<dt>-n, --network</dt>
<dd>要建立的子網路 ID。</dd>
</dl>

## ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

從 IPSEC 通道環境定義移除子網路。
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

## ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

將位址轉換新增至 IPSec 通道。
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-s, --static-ip</dt>
<dd>靜態 IP 位址，必要項目。</dd>
<dt>-r, --remote-ip</dt>
<dd>遠端 IP 位址，必要項目。</dd>
<dt>-n, --note</dt>
<dd>附註。</dd>
</dl>

## ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

從 IPSec 移除轉換項目。
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

## ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

更新 IPSec 的位址轉換。
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-s, --static-ip</dt>
<dd>靜態 IP 位址，必要項目。</dd>
<dt>-r, --remote-ip</dt>
<dd>遠端 IP 位址，必要項目。</dd>
<dt>-n, --note</dt>
<dd>附註。</dd>
</dl>

## ibmcloud sl ipsec update
{: #sl_ipsec_update}

更新通道環境定義內容。
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-n, --name</dt>
<dd>一般名稱。</dd>
<dt>-r, --remote-peer</dt>
<dd>遠端對等節點 IP 位址。</dd>
<dt>-k, --preshared-key</dt>
<dd>預先共用金鑰。</dd>
<dt>-a, --phase1-auth</dt>
<dd>階段 1 鑑別，選項包含：MD5、SHA1、SHA256。</dd>
<dt>-c, --phase1-crypto</dt>
<dd>階段 1 加密，選項包含：DES、3DES、AES128、AES192、AES256。</dd>
<dt>-d, --phase1-dh</dt>
<dd>階段 1 Diffie Hellman 群組，選項包含：0、1、2、5。</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>階段 1 金鑰使用期限，範圍為 120-172800。</dd>
<dt>-u, --phase2-auth</dt>
<dd>階段 2 鑑別，選項包含：MD5、SHA1、SHA256。</dd>
<dt>-y, --phase2-crypto</dt>
<dd>階段 2 加密，選項包含：DES、3DES、AES128、AES192、AES256。</dd>
<dt>-e, --phase2-dh</dt>
<dd>階段 2 Diffie Hellman 群組，選項包含：0、1、2、5。</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>階段 2 完全秘密轉遞，範圍為 0-1。</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>階段 2 金鑰使用期限，範圍為 120-172800。</dd>
</dl>
