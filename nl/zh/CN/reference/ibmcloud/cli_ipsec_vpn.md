---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} 基础架构 IPSec VPN

使用以下命令可管理 {{site.data.keyword.Bluemix_notm}} 基础架构 IPSec VPN 服务中的 IPSec VPN 隧道。
{: shortdesc}

<table summary="按字母顺序排序的 {{site.data.keyword.Bluemix_notm}} IPSec VPN 命令（命令带有可获取命令更多信息的链接）">
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

取消 IPSec VPN 隧道上下文。
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--immediate</dt>
<dd>立即取消 IPSec，而不是在计费周年取消。</dd>
<dt>--reason</dt>
<dd>可选的取消原因。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

## ibmcloud sl ipsec config
{: #sl_ipsec_config}

请求隧道上下文的配置。
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

列出 IPSec VPN 隧道上下文详细信息。
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-i, --include</dt>
<dd>包含其他资源，选项为：at、is、rs、sr 或 ss。</dd>
</dl>

## ibmcloud sl ipsec list
{: #sl_ipsec_list}

列出 IPSec VPN 隧道上下文。
```
ibmcloud sl ipsec list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--order</dt>
<dd>按购买了 IPSec 的订单的标识过滤。</dd>
</dl>

## ibmcloud sl ipsec order
{: #sl_ipsec_order}

订购 IPSec VPN 隧道。
```
ibmcloud sl ipsec order [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-d, --datacenter</dt>
<dd>必需。IPSec 的数据中心的短名称，例如 dal09。</dd>
</dl>

## ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

向 IPSec 隧道上下文添加子网。
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-s, --subnet-id</dt>
<dd>要添加的子网标识（必需）。</dd>
<dt>-t, --subnet-type</dt>
<dd>要添加的子网类型（必需），选项为：internal、remote 或 service。</dd>
<dt>-n, --network</dt>
<dd>要创建的子网标识。</dd>
</dl>

## ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

从 IPSec 隧道上下文中除去子网。
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

## ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

向 IPSec 隧道添加地址转换。
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-s, --static-ip</dt>
<dd>静态 IP 地址（必需）。</dd>
<dt>-r, --remote-ip</dt>
<dd>远程 IP 地址（必需）。</dd>
<dt>-n, --note</dt>
<dd>注释。</dd>
</dl>

## ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

从 IPSec 中除去转换条目。
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

## ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

更新 IPSec 的地址转换。
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-s, --static-ip</dt>
<dd>静态 IP 地址（必需）。</dd>
<dt>-r, --remote-ip</dt>
<dd>远程 IP 地址（必需）。</dd>
<dt>-n, --note</dt>
<dd>注释。</dd>
</dl>

## ibmcloud sl ipsec update
{: #sl_ipsec_update}

更新隧道上下文属性。
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-n, --name</dt>
<dd>友好名称。</dd>
<dt>-r, --remote-peer</dt>
<dd>远程同级 IP 地址。</dd>
<dt>-k, --preshared-key</dt>
<dd>预共享密钥。</dd>
<dt>-a, --phase1-auth</dt>
<dd>第 1 阶段认证，选项为：MD5、SHA1 或 SHA256。</dd>
<dt>-c, --phase1-crypto</dt>
<dd>第 1 阶段加密，选项为：DES、3DES、AES128、AES192 或 AES256。</dd>
<dt>-d, --phase1-dh</dt>
<dd>第 1 阶段 Diffie-Hellman 组，选项为：0、1、2 或 5。</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>第 1 阶段密钥生存期，范围为 120-172800。</dd>
<dt>-u, --phase2-auth</dt>
<dd>第 2 阶段认证，选项为：MD5、SHA1 或 SHA256。</dd>
<dt>-y, --phase2-crypto</dt>
<dd>第 2 阶段加密，选项为：DES、3DES、AES128、AES192 或 AES256。</dd>
<dt>-e, --phase2-dh</dt>
<dd>第 2 阶段 Diffie-Hellman 组，选项为：0、1、2 或 5。</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>第 2 阶段完美前向加密，范围为 0-1。</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>第 2 阶段密钥生存期，范围为 120-172800。</dd>
</dl>
