---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: domain management, dns service, ibmcloud sl dns, classic infrastructure, management interface, dns, dns cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 使用 DNS 服務來管理網域
{: #sl-manage-domains}

{{site.data.keyword.cloud}} 網域名稱服務 (DNS) 提供客戶一個集中位置，可以透過基本 DNS 管理介面檢視和管理他們的網域，另外也讓使用者能選擇在相同的位置免費管理反向和次要 DNS。

請使用下列指令來管理 {{site.data.keyword.cloud_notm}} 標準基礎架構 DNS 服務。
{: shortdesc}

## ibmcloud sl dns import
{: #sl_dns_import}

以 BIND 區域檔案為基礎匯入區域。
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--dry-run</dt>
<dd>不要實際建立記錄。</dd>
</dl>

**範例**：
```
ibmcloud sl dns import ~/ibm.com.txt
```
這個指令會從 ~/ibm.com.txt 檔案匯入區域及其資源記錄。


## ibmcloud sl dns record-add
{: #sl_dns_record_add}

在區域中新增資源記錄。
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--ttl</dt>
<dd>TTL（存活時間）（以秒為單位），例如：86400，預設值為：7200。</dd>
</dl>

**範例**：
```
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
這個指令會將 A 記錄新增至 ibm.com 區域，其主機為 "ftp"、資料為 "127.0.0.1"，而 ttl 為 86400 秒。


## ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

更新區域中的資源記錄。
```
ibmcloud sl dns record-edit ZONE [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--by-record</dt>
<dd>依主機記錄編輯，例如 www。</dd>
<dt>--by-id</dt>
<dd>依 ID 編輯單一記錄。</dd>
<dt>--data</dt>
<dd>記錄資料，例如 IP 位址。</dd>
<dt>--ttl</dt>
<dd>TTL 值（以秒為單位），例如：86400。</dd>
</dl>

**範例**：
```
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
這個指令會編輯 ibm.com 區域下 ID 為 12345678 的記錄、將其資料設為 "127.0.0.2"，並將 ttl 設為 3600。


## ibmcloud sl dns record-list
{: #sl_dns_record_list}

列出區域中的所有資源記錄。
```
ibmcloud sl dns record-list ZONE [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--data</dt>
<dd>依記錄資料進行過濾，例如 IP 位址。</dd>
<dt>--record</dt>
<dd>依主機記錄進行過濾，例如 www。</dd>
<dt>--ttl</dt>
<dd>依 TTL 值（以秒為單位）進行過濾，例如 86400。</dd>
<dt>--type</dt>
<dd>依記錄類型進行過濾，例如 A 或 CNAME。</dd>
</dl>

**範例**：
```
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
這個指令會列出 ibm.com 區域下的所有 A 記錄、用來過濾的主機為 elasticsearch，而 ttl 為 900 秒。


## ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

移除區域中的資源記錄。
```
ibmcloud sl dns record-remove RECORD_ID
```

**範例**：
```
ibmcloud sl dns record-remove 12345678
```
這個指令會移除 ID 為 12345678 的資源記錄。


## ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

建立區域。
```
ibmcloud sl dns zone-create ZONE
```

**範例**：
```
ibmcloud sl dns zone-create ibm.com
```
這個指令會建立名為 ibm.com 的區域。


## ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

刪除區域。
```
ibmcloud sl dns zone-delete ZONE
```

**範例**：
```
ibmcloud sl dns zone-delete ibm.com
```
這個指令會刪除名為 ibm.com 的區域。


## ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

列出您帳戶上的所有區域。
```
ibmcloud sl dns zone-list
```

**範例**：
```
ibmcloud sl dns zone-list
```
這個指令會列出現行帳戶下的所有區域。


## ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

以 BIND 格式列印區域及資源記錄。
```
ibmcloud sl dns zone-print ZONE
```

**範例**：
```
ibmcloud sl dns zone-print ibm.com
```
這個指令會以 BIND 格式列印名為 ibm.com 的區域。
