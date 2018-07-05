---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 虚拟服务器 CLI 命令

<table summary="按字母顺序排序的常规 {{site.data.keyword.BluSoftlayer_notm}} 基础架构命令（命令带有可获取命令更多信息的链接）">
<caption>表 1. {{site.data.keyword.BluSoftlayer_notm}} 基础架构虚拟服务器命令</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} 基础架构虚拟服务器命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vs cancel](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_cancel)</td>
 <td>[ibmcloud sl vs capture](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_capture)</td>
 <td>[ibmcloud sl vs create](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_create)</td>
 <td>[ibmcloud sl vs options](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_options)</td>
 <td>[ibmcloud sl vs credentials](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_credentials)</td>
 <td>[ibmcloud sl vs detail](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_detail)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs dns-sync](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_dns_sync)</td>
 <td>[ibmcloud sl vs edit](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_edit)</td>
 <td>[ibmcloud sl vs host-create](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_host_create)</td>
 <td>[ibmcloud sl vs host-list](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_host_list)</td>
 <td>[ibmcloud sl vs list](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_list)</td>
 <td>[ibmcloud sl vs pause](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_pause)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs power-off](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_power_off)</td>
 <td>[ibmcloud sl vs power-on](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_power_on)
 <td>[ibmcloud sl vs ready](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_ready)</td>
 <td>[ibmcloud sl vs reboot](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_reboot)</td>
 <td>[ibmcloud sl vs reload](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_reload)</td>
 <td>[ibmcloud sl vs rescue](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_rescue)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs resume](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_resume)</td>
 <td>[ibmcloud sl vs upgrade](/docs/cli/reference/softlayer/sl_cli_virtual_server.html#sl_vs_upgrade)</td>
</tr>
   </tbody>
 </table>
 
 ### ibmcloud sl vs cancel
{: #sl_vs_cancel}

取消虚拟服务器实例。
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs cancel 12345678
```
此命令取消标识为 12345678 的虚拟服务器实例。




### ibmcloud sl vs capture
{: #sl_vs_capture}

将虚拟服务器实例捕获到映像中。
```
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-n, --name</dt>
<dd>必需。映像的名称。</dd>
<dt>--all</dt>
<dd>捕获属于 VS 的所有磁盘。</dd>
<dt>--note</dt>
<dd>添加要与映像关联的注释。</dd>
</dl>

**示例**：
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
此命令将标识为 12345678 的虚拟服务器实例中的所有磁盘捕获到名为“mycloud”的映像中，注释为“testing”。

### ibmcloud sl vs create
{: #sl_vs_create}

创建虚拟服务器实例。
```
ibmcloud sl vs create [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-H, --hostname</dt>
<dd>必需。FQDN 的主机部分。</dd>
<dt>-D, --domain</dt>
<dd>必需。FQDN 的域部分。</dd>
<dt>-c, --cpu</dt>
<dd>必需。CPU 核心数。</dd>
<dt>-m, --memory</dt>
<dd>必需。内存（以兆字节为单位）。</dd>
<dt>--flavor</dt>
<dd>公共虚拟服务器类型模板键名。</dd>
<dt>-d, --datacenter</dt>
<dd>必需。数据中心短名称。</dd>
<dt>-o, --os</dt>
<dd>操作系统安装代码。提示：可以指定 <OS>_LATEST。</dd>
<dt>--image</dt>
<dd>映像标识。请参阅“ibmcloud sl image list”以获取参考信息。</dd>
<dt>--billing</dt>
<dd>计费费率。缺省值为：hourly。选项为：hourly 或 monthly。</dd>
<dt>--dedicated</dt>
<dd>创建专用虚拟服务器（专用节点）。</dd>
<dt>--host-id</dt>
<dd>要将专用虚拟服务器供应到的主机标识。</dd>
<dt>--san</dt>
<dd>使用 SAN 存储器（而非本地磁盘）。</dd>
<dt>--test</dt>
<dd>实际不创建虚拟服务器。</dd>
<dt>--export</dt>
<dd>将选项导出到模板文件。</dd>
<dt>-i, --postinstall</dt>
<dd>要下载的安装后脚本。</dd>
<dt>-k, --key</dt>
<dd>要添加到 root 用户的 SSH 密钥的标识（允许多次出现）。</dd>
<dt>--disk</dt>
<dd>磁盘大小（允许多次出现）。</dd>
<dt>--private</dt>
<dd>强制虚拟服务器只有权访问专用网络。</dd>
<dt>--like</dt>
<dd>使用现有虚拟服务器中的配置。</dd>
<dt>-n, --network</dt>
<dd>网络端口速度（以 Mbps 为单位）。</dd>
<dt>-g, --tag</dt>
<dd>要添加到实例的标记（允许多次出现）。</dd>
<dt>-t, --template</dt>
<dd>对命令行选项使用缺省值的模板文件。</dd>
<dt>-u, --userdata</dt>
<dd>用户定义的元数据字符串。</dd>
<dt>-F, --userfile</dt>
<dd>从文件中读取用户数据。</dd>
<dt>--vlan-public</dt>
<dd>要将虚拟服务器放到其中的公共 VLAN 的标识。</dd>
<dt>--vlan-private</dt>
<dd>要将虚拟服务器放到其中的专用 VLAN 的标识。</dd>
<dt>-S, --public-security-group</dt>
<dd>要与公共接口关联的安全组标识（允许多次出现）。</dd>
<dt>-s, --private-security-group</dt>
<dd>要与专用接口关联的安全组标识（允许多次出现）。</dd>
<dt>--wait</dt>
<dd>等待虚拟服务器完成供应（最长 X 秒）后再返回。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
此命令订购虚拟服务器实例，其主机名为 myvsi，域为 ibm.com，4 个 CPU 核心，4096M 内存，位于数据中心 dal10。

### ibmcloud sl vs options
{: #sl_vs_options}

列出用于创建虚拟服务器实例的选项。
```
ibmcloud sl vs options [OPTIONS]
```


**示例**：
```
ibmcloud sl vs options
```
此命令列出用于创建虚拟服务器实例的所有选项，例如，数据中心、CPU、内存、操作系统、磁盘、网络速度等。





### ibmcloud sl vs credentials
{: #sl_vs_credentials}

列出虚拟服务器实例凭证。
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONS]
```


**示例**：
```
ibmcloud sl vs credentials 12345678
```
此命令列出标识为 12345678 的虚拟服务器实例的所有用户名和密码对。



### ibmcloud sl vs detail
{: #sl_vs_detail}

获取虚拟服务器实例的详细信息。
```
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--passwords</dt>
<dd>显示密码（小心有人在你背后偷看！）.</dd>
<dt>--price</dt>
<dd>显示关联的价格。</dd>
</dl>

**示例**：
```
ibmcloud sl vs details 12345678
```
此命令列出有关标识为 12345678 的虚拟服务器实例的详细信息。




### ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

同步虚拟服务器实例的 DNS 记录。
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-a, --a-record</dt>
<dd>同步主机的 A 记录。</dd>
<dt>--aaaa-record</dt>
<dd>同步主机的 AAAA 记录。</dd>
<dt>--ptr</dt>
<dd>同步主机的 PTR 记录。</dd>
<dt>--ttl</dt>
<dd>为 A 和/或 PTR 记录设置 TTL，缺省值为：7200。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
此命令将标识为 12345678 的虚拟服务器实例的 A 记录（IP V4 地址）与 DNS 服务器同步，并将此 A 记录的 ttl 设置为 3600。


### ibmcloud sl vs edit
{: #sl_vs_edit}

编辑虚拟服务器实例的详细信息。
```
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-D, --domain</dt>
<dd>FQDN 的域部分。</dd>
<dt>-H, --hostname</dt>
<dd>FQDN 的主机部分。示例：server。</dd>
<dt>-g, --tag</dt>
<dd>要设置的标记，或使用空字符串表示全部除去。</dd>
<dt>-u, --userdata</dt>
<dd>用户定义的元数据字符串。</dd>
<dt>-F, --userfile</dt>
<dd>从文件中读取用户数据。</dd>
<dt>--public-speed</dt>
<dd>公共端口速度，选项为：0、10、100、1000 或 10000。</dd>
<dt>--private-speed</dt>
<dd>专用端口速度，选项为：0、10、100、1000 或 10000。</dd>
</dl>

**示例**：
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
此命令更新标识为 12345678 的虚拟服务器实例，并将其域设置为“ibm.com”，主机名设置为“myapp”，标记设置为“testcli”。

### ibmcloud sl vs host-create
{: #sl_vs_host_create}

为专用虚拟服务器创建主机。
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-H, --hostname</dt>
<dd>必需。FQDN 的主机部分。</dd>
<dt>-D, --domain</dt>
<dd>必需。FQDN 的域部分。</dd>
<dt>-d, --datacenter</dt>
<dd>必需。数据中心短名称。</dd>
<dt>-s, --size</dt>
<dd>专用主机的大小，目前只有一种大小可用：56_CORES_X_242_RAM_X_1_4_TB。</dd>
<dt>-b, --billing</dt>
<dd>计费费率。缺省值为：hourly。选项为：hourly 或 monthly。</dd>
<dt>-v, --vlan-private</dt>
<dd>要将专用主机放到其中的专用 VLAN 的标识。请参阅“ibmcloud sl vlan list”以获取参考信息。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl vs host-list
{: #sl_vs_host_list}

列出帐户上的专用主机。
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>命令选项</strong>：
<dl>
<dt>-n, --name</dt>
<dd>按专用主机的名称过滤。</dd>
<dt>-d, --datacenter</dt>
<dd>按专用主机的数据中心过滤。</dd>
<dt>--owner</dt>
<dd>按专用主机的所有者过滤。</dd>
<dt>--order</dt>
<dd>按购买了此专用主机的订单的标识过滤。</dd>
</dl>

### ibmcloud sl vs list
{: #sl_vs_list}

列出帐户的虚拟服务器实例。
```
ibmcloud sl vs list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-c, --cpu</dt>
<dd>按 CPU 核心数过滤。</dd>
<dt>-D, --domain</dt>
<dd>按 FQDN 的域部分过滤。</dd>
<dt>-d, --datacenter</dt>
<dd>按数据中心短名称过滤。</dd>
<dt>-H, --hostname</dt>
<dd>按 FQDN 的主机部分过滤。</dd>
<dt>-m, --memory</dt>
<dd>按内存（以兆字节为单位）过滤。</dd>
<dt>-n, --network</dt>
<dd>按网络端口速度 (Mbps) 过滤。</dd>
<dt>-P, --public-ip</dt>
<dd>按公共 IP 地址过滤。</dd>
<dt>-p, --private-ip</dt>
<dd>按专用 IP 地址过滤。</dd>
<dt>--hourly</dt>
<dd>仅显示每小时实例。</dd>
<dt>--monthly</dt>
<dd>仅显示每月实例。</dd>
<dt>-g, --tag</dt>
<dd>按标记过滤（允许多次出现）。</dd>
<dt>-o, --order</dt>
<dd>按购买了此实例的订单的标识过滤。</dd>
<dt>--owner</dt>
<dd>按拥有实例的用户的标识过滤。</dd>
<dt>--sortby</dt>
<dd>要作为排序依据的列，缺省值为：hostname，选项为：id、hostname、domain、datacenter、cpu、memory、public_ip 或 private_ip。</dd>
<dt>--columns</dt>
<dd>要显示的列，缺省值为：id、hostname、public_ip、private_ip、datacenter 和 action，选项为：guid、power_state、created_by 或 tags。</dd>
</dl>

**示例**：
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
此命令列出当前帐户的所有每小时计费的虚拟服务器实例，过滤域为“ibm.com”域，并按内存对其排序。

### ibmcloud sl vs pause
{: #sl_vs_pause}

暂停活动的虚拟服务器实例。
```
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs pause 12345678 -f
```
此命令暂停标识为 12345678 的虚拟服务器实例，而不要求确认。





### ibmcloud sl vs power-off
{: #sl_vs_power_off}

关闭活动虚拟服务器实例的电源。
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--hard</dt>
<dd>执行硬关闭。</dd>
<dt>--soft</dt>
<dd>执行软关闭。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs power-off 12345678 --soft
```
此命令对标识为 12345678 的虚拟服务器实例执行软电源关闭操作。



### ibmcloud sl vs power-on
{: #sl_vs_power_on}

打开虚拟服务器实例的电源。
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs power-on 12345678
```
此命令对标识为 12345678 的虚拟服务器实例执行打开电源操作。




### ibmcloud sl vs ready
{: #sl_vs_ready}

检查虚拟服务器实例是否准备就绪可供使用。
```
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--wait</dt>
<dd>等待虚拟服务器完成供应（最长 X 秒）后再返回。</dd>
</dl>

**示例**：
```
ibmcloud sl vs ready 12345678 --wait 30
```
此命令检查标识为 12345678 的虚拟服务器实例的状态以确定其是否准备就绪可持续使用，并且最长等待 30 秒。



### ibmcloud sl vs reboot
{: #sl_vs_reboot}

重新引导活动的虚拟服务器实例。
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--hard</dt>
<dd>执行硬重新引导。</dd>
<dt>--soft</dt>
<dd>执行软重新引导。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs reboot 12345678 --hard
```
此命令对标识为 12345678 的虚拟服务器实例执行硬重新引导。





### ibmcloud sl vs reload
{: #sl_vs_reload}

在虚拟服务器实例上重装操作系统。
```
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-i, --postinstall</dt>
<dd>要下载的安装后脚本。</dd>
<dt>--image</dt>
<dd>映像标识。缺省值为使用当前操作系统。</dd>
<dt>请参阅</dt>
<dd>“ibmcloud sl image list”以获取参考信息。</dd>
<dt>-k, --key</dt>
<dd>要添加到 root 用户的 SSH 密钥的标识（允许多次出现）。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs reload 12345678
```
此命令为标识为 12345678 的虚拟服务器实例重新装入当前操作系统。


### ibmcloud sl vs rescue
{: #sl_vs_rescue}

将虚拟服务器实例重新引导至拯救映像。
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs rescue 12345678
```
此命令将标识为 12345678 的虚拟服务器实例重新引导到拯救映像。




### ibmcloud sl vs resume
{: #sl_vs_resume}

恢复暂停的虚拟服务器实例。
```
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs resume 12345678
```
此命令恢复标识为 12345678 的虚拟服务器实例。




### ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

升级虚拟服务器实例。
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-c, --cpu</dt>
<dd>CPU 核心数。</dd>
<dt>--private</dt>
<dd>CPU 核心将位于专用主机服务器上。</dd>
<dt>-m, --memory</dt>
<dd>内存（以兆字节为单位）。</dd>
<dt>--network</dt>
<dd>网络端口速度（以 Mbps 为单位）。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
此命令升级标识为 12345678 的虚拟服务器实例，并将 CPU 核心数设置为 8，内存设置为 8192M，网络端口速度设置为 1000 Mbps。
