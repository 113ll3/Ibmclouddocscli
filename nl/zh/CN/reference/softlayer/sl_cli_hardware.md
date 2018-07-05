---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 硬件 CLI 命令

<table summary="按字母顺序排序的常规 {{site.data.keyword.BluSoftlayer_notm}} 基础架构命令（命令带有可获取命令更多信息的链接）">
<caption>表 1. {{site.data.keyword.BluSoftlayer_notm}} 基础架构硬件命令</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} 基础架构硬件命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl hardware cancel](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_cancel)</td>
 <td>[ibmcloud sl hardware cancel-reasons](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_cancel_reasons)</td>
 <td>[ibmcloud sl hardware create](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_create)</td>
 <td>[ibmcloud sl hardware create-options](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_create_options)</td>
 <td>[ibmcloud sl hardware credentials](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_credentials)</td>
 <td>[ibmcloud sl hardware detail](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_detail)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware edit](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_edit)</td>
 <td>[ibmcloud sl hardware list](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_list)</td>
 <td>[ibmcloud sl hardware power-cycle](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_cycle)</td>
 <td>[ibmcloud sl hardware power-off](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_off)</td>
 <td>[ibmcloud sl hardware power-on](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_on)</td>
 <td>[ibmcloud sl hardware reboot](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_reboot)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware reload](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_reload)</td>
 <td>[ibmcloud sl hardware rescue](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_rescue)</td>
 <td>[ibmcloud sl hardware update-firmware](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_update_firmware)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

取消硬件服务器。
```
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-i, --immediate</dt>
<dd>立即取消服务器（而不是在计费周年取消）。</dd>
<dt>-r, --reason</dt>
<dd>（可选）取消原因。请参阅“ibmcloud sl hardware cancel-recons”以获取可用选项的列表。</dd>
<dt>-c, --comment</dt>
<dd>（可选）要添加到取消凭单的注释。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

显示取消原因的列表。
```
ibmcloud sl hardware cancel-reasons
```

### ibmcloud sl hardware create
{: #sl_hardware_create}

订购/创建硬件服务器。
```
ibmcloud sl hardware create [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-H, --hostname</dt>
<dd>FQDN 的主机部分（必需）。</dd>
<dt>-D, --domain</dt>
<dd>FQDN 的域部分（必需）。</dd>
<dt>-s, --size</dt>
<dd>硬件大小（必需）。</dd>
<dt>-o, --os</dt>
<dd>操作系统安装代码（必需）。</dd>
<dt>-d, --datacenter</dt>
<dd>数据中心短名称（必需）。</dd>
<dt>-p, --port-speed</dt>
<dd>端口速度（必需）。</dd>
<dt>-b, --billing</dt>
<dd>计费费率，为 hourly 或 monthly，如果未指定，缺省值为 hourly。</dd>
<dt>-i, --post-install</dt>
<dd>要下载的安装后脚本。</dd>
<dt>-k, --key</dt>
<dd>要添加到 root 用户的 SSH 密钥（允许多次出现）。</dd>
<dt>-n, --no-public</dt>
<dd>仅专用网络。</dd>
<dt>-e, --extra</dt>
<dd>额外选项（允许多次出现）。</dd>
<dt>-t, --test</dt>
<dd>实际不创建虚拟服务器。</dd>
<dt>-m, --template</dt>
<dd>对命令行选项使用缺省值的模板文件。</dd>
<dt>-x, --export</dt>
<dd>将选项导出到模板文件。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

给定机箱的服务器订购选项。
```
ibmcloud sl hardware create-options
```

### ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

列出硬件服务器凭证。
```
ibmcloud sl hardware credentials IDENTIFIER
```

### ibmcloud sl hardware detail
{: #sl_hardware_detail}

获取硬件服务器的详细信息。
```
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-p, --passwords</dt>
<dd>显示密码（小心有人在你背后偷看！）.</dd>
<dt>-c, --price</dt>
<dd>显示关联的价格。</dd>
</dl>

### ibmcloud sl hardware edit
{: #sl_hardware_edit}

编辑硬件服务器详细信息。
```
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-H, --hostname</dt>
<dd>FQDN 的主机部分。</dd>
<dt>-D, --domain</dt>
<dd>FQDN 的域部分。</dd>
<dt>-g, --tag</dt>
<dd>要设置的标记，或使用空字符串表示全部除去。</dd>
<dt>-F, --userfile</dt>
<dd>从文件中读取用户数据。</dd>
<dt>-u, --userdata</dt>
<dd>用户定义的元数据字符串。</dd>
<dt>-p, --public-speed</dt>
<dd>公共端口速度，选项为：0、10、100、1000 或 10000。</dd>
<dt>-v, --private-speed</dt>
<dd>专用端口速度，选项为：0、10、100、1000 或 10000。</dd>
</dl>

### ibmcloud sl hardware list
{: #sl_hardware_list}

列出硬件服务器。
```
ibmcloud sl hardware list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-c, --cpu</dt>
<dd>按 CPU 核心数过滤。</dd>
<dt>-D, --domain</dt>
<dd>按域过滤。</dd>
<dt>-H, --hostname</dt>
<dd>按主机名过滤。</dd>
<dt>-d, --datacenter</dt>
<dd>按数据中心过滤。</dd>
<dt>-m, --memory</dt>
<dd>按内存（以千兆字节为单位）过滤。</dd>
<dt>-n, --network</dt>
<dd>按网络端口速度 (Mbps) 过滤。</dd>
<dt>-g, --tag</dt>
<dd>按标记过滤（允许多次出现）。</dd>
<dt>-p, --public-ip</dt>
<dd>按公共 IP 地址过滤。</dd>
<dt>-v, --private-ip</dt>
<dd>按专用 IP 地址过滤。</dd>
<dt>-o, --order</dt>
<dd>按购买了硬件服务器的订单的标识过滤。</dd>
<dt>--owner</dt>
<dd>按所有者标识过滤。</dd>
<dt>--sortby</dt>
<dd>要作为排序依据的列，缺省值：hostname，选项：id、guid、hostname、domain、public_ip、private_ip、datacenter、status、ipmi_ip、created 或 created_by。</dd>
<dt>--columns</dt>
<dd>要显示的列，缺省值：id、hostname、domain、public_ip、private_ip、datacenter 和 status，选项：guid、cpu、memory、os、ipmi_ip、created、created_by 或 tags。</dd>
</dl>

### ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

重启服务器的电源。
```
ibmcloud sl hardware power-cycle IDENTIFIER
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

关闭活动服务器的电源。
```
ibmcloud sl hardware power-off IDENTIFIER
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

打开服务器的电源。
```
ibmcloud sl hardware power-on IDENTIFIER
```

### ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

重新引导活动服务器。
```
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
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

### ibmcloud sl hardware reload
{: #sl_hardware_reload}

在服务器上重装操作系统。
```
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-i, --postinstall</dt>
<dd>要下载的安装后脚本，仅限 HTTPS 执行，HTTP 会使文件留在 /root 下。</dd>
<dt>-k, --key</dt>
<dd>要添加到 root 用户的 SSH 密钥的标识（允许多次出现）。</dd>
<dt>-b, --upgrade-bios</dt>
<dd>升级 BIOS。</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>升级所有硬盘驱动器的固件。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

将服务器重新引导至拯救映像。
```
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

更新服务器固件。
```
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>
