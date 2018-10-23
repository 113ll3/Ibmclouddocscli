---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 仮想サーバー

{{site.data.keyword.BluVirtServers}} は、専用のコアおよびメモリー割り振りと共に購入される拡張が容易な仮想サーバーです。 数分で追加が可能で、イメージ・テンプレートのような機能も利用できる計算リソースをお探しであれば、これは優れた選択肢です。  

以下のコマンドを使用して、{{site.data.keyword.Bluemix}} インフラストラクチャー仮想サーバーを管理します。
{: shortdesc}

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の {{site.data.keyword.Bluemix_notm}} インフラストラクチャー仮想サーバー・コマンド">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vs cancel](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_cancel)</td>
 <td>[ibmcloud sl vs capture](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_capture)</td>
 <td>[ibmcloud sl vs create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_create)</td>
 <td>[ibmcloud sl vs options](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_options)</td>
 <td>[ibmcloud sl vs credentials](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_credentials)</td>
 <td>[ibmcloud sl vs detail](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_detail)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs dns-sync](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_dns_sync)</td>
 <td>[ibmcloud sl vs edit](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_edit)</td>
 <td>[ibmcloud sl vs host-create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_create)</td>
 <td>[ibmcloud sl vs host-list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_list)</td>
 <td>[ibmcloud sl vs list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_list)</td>
 <td>[ibmcloud sl vs pause](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_pause)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs power-off](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_off)</td>
 <td>[ibmcloud sl vs power-on](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_on)
 <td>[ibmcloud sl vs ready](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_ready)</td>
 <td>[ibmcloud sl vs reboot](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reboot)</td>
 <td>[ibmcloud sl vs reload](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reload)</td>
 <td>[ibmcloud sl vs rescue](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_rescue)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs resume](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_resume)</td>
 <td>[ibmcloud sl vs upgrade](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_upgrade)</td>
</tr>
   </tbody>
 </table>

 ## ibmcloud sl vs cancel
{: #sl_vs_cancel}

仮想サーバー・インスタンスを取り消します。
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs cancel 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを取り消します。

## ibmcloud sl vs capture
{: #sl_vs_capture}

仮想サーバー・インスタンスをイメージに取り込みます。
```
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --name</dt>
<dd>必須。 イメージの名前。</dd>
<dt>--all</dt>
<dd>この VS に属しているすべてのディスクを取り込みます。</dd>
<dt>--note</dt>
<dd>このイメージに関連付けるメモを追加します。</dd>
</dl>

**例**:
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスをすべてのディスクと共に、「mycloud」という名前のイメージに、「testing」というメモを付けて取り込みます。

## ibmcloud sl vs create
{: #sl_vs_create}

仮想サーバー・インスタンスを作成します。
```
ibmcloud sl vs create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>必須。 FQDN のホスト部分。</dd>
<dt>-D, --domain</dt>
<dd>必須。 FQDN のドメイン部分。</dd>
<dt>-c, --cpu</dt>
<dd>必須。 CPU コアの数。</dd>
<dt>-m, --memory</dt>
<dd>必須。 メモリー (M バイト)。</dd>
<dt>--flavor</dt>
<dd>パブリック仮想サーバー・フレーバー・キー名。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 データ・センターの短縮名。</dd>
<dt>-o, --os</dt>
<dd>OS インストール・コード。 ヒント: <OS>_LATEST を指定できます。</dd>
<dt>--image</dt>
<dd>イメージ ID。 「ibmcloud sl image list」を参照してください。</dd>
<dt>--billing</dt>
<dd>請求レート。 デフォルトは hourly です。 オプション: hourly、monthly。</dd>
<dt>--dedicated</dt>
<dd>専用仮想サーバー (プライベート・ノード) を作成します。</dd>
<dt>--host-id</dt>
<dd>専用仮想サーバーをプロビジョンするホスト ID。</dd>
<dt>--san</dt>
<dd>ローカル・ディスクの代わりに SAN ストレージを使用します。</dd>
<dt>--test</dt>
<dd>実際には仮想サーバーを作成しません。</dd>
<dt>--export</dt>
<dd>オプションをテンプレート・ファイルにエクスポートします。</dd>
<dt>-i, --postinstall</dt>
<dd>ダウンロードするインストール後スクリプト。</dd>
<dt>-k, --key</dt>
<dd>root ユーザーに追加する SSH 鍵の ID (複数のオカレンスが許可されます)。</dd>
<dt>--disk</dt>
<dd>ディスク・サイズ (複数のオカレンスが許可されます)。</dd>
<dt>--private</dt>
<dd>仮想サーバーがプライベート・ネットワークのみにアクセスすることを強制します。</dd>
<dt>--like</dt>
<dd>既存の仮想サーバーからの構成を使用します。</dd>
<dt>-n, --network</dt>
<dd>ネットワーク・ポート速度 (Mbps)。</dd>
<dt>-g, --tag</dt>
<dd>インスタンスに追加するタグ (複数のオカレンスが許可されます)。</dd>
<dt>-t, --template</dt>
<dd>コマンド・ライン・オプションをデフォルト設定するテンプレート・ファイル。</dd>
<dt>-u, --userdata</dt>
<dd>ユーザー定義のメタデータ・ストリング。</dd>
<dt>-F, --userfile</dt>
<dd>ユーザー・データをファイルから読み取ります。</dd>
<dt>--vlan-public</dt>
<dd>仮想サーバーを配置するパブリック VLAN の ID。</dd>
<dt>--vlan-private</dt>
<dd>仮想サーバーを配置するプライベート VLAN の ID。</dd>
<dt>-S, --public-security-group</dt>
<dd>パブリック・インターフェースに関連付けるセキュリティー・グループ ID (複数のオカレンスが許可されます)。</dd>
<dt>-s, --private-security-group</dt>
<dd>プライベート・インターフェースに関連付けるセキュリティー・グループ ID (複数のオカレンスが許可されます)。</dd>
<dt>--wait</dt>
<dd>仮想サーバーでのプロビジョニング終了を最大 X 秒待ってから戻ります。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
このコマンドは、ホスト名 myvsi、ドメイン ibm.com、cpu コア x 4、4096M メモリー、データ・センター dal10 で仮想サーバー・インスタンスを注文します。

## ibmcloud sl vs options
{: #sl_vs_options}

仮想サーバー・インスタンスの作成に関するオプションをリストします。
```
ibmcloud sl vs options [OPTIONS]
```


**例**:
```
ibmcloud sl vs options
```
このコマンドは、仮想サーバー・インスタンス (例えば、データ・センター、CPU、メモリー、OS、ディスク、ネットワーク速度など) を作成するためのすべてのオプションをリストします。

## ibmcloud sl vs credentials
{: #sl_vs_credentials}

仮想サーバー・インスタンスの資格情報をリストします。
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONS]
```


**例**:
```
ibmcloud sl vs credentials 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのユーザー名とパスワードのすべてのペアをリストします。

## ibmcloud sl vs detail
{: #sl_vs_detail}

仮想サーバー・インスタンスの詳細を取得します。
```
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--passwords</dt>
<dd>パスワードを表示します (他人に見られないように注意してください)。</dd>
<dt>--price</dt>
<dd>関連付けられた価格を表示します。</dd>
</dl>

**例**:
```
ibmcloud sl vs details 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスに関する詳細情報をリストします。

## ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

仮想サーバー・インスタンスの DNS レコードを同期します。
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>ホストの A レコードを同期します。</dd>
<dt>--aaaa-record</dt>
<dd>ホストの AAAA レコードを同期します。</dd>
<dt>--ptr</dt>
<dd>ホストの PTR レコードを同期します。</dd>
<dt>--ttl</dt>
<dd>A レコードまたは PTR レコード、あるいは両方の TTL を設定します。デフォルトは 7200 です。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスの A レコード (IP V4 アドレス) を DNS サーバーに同期し、この A レコードの TTL を 3600 に設定します。

## ibmcloud sl vs edit
{: #sl_vs_edit}

仮想サーバー・インスタンスの詳細を編集します。
```
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>FQDN のドメイン部分。</dd>
<dt>-H, --hostname</dt>
<dd>FQDN のホスト部分。 例: server。</dd>
<dt>-g, --tag</dt>
<dd>設定するタグ、または、すべて削除する場合は空ストリング。</dd>
<dt>-u, --userdata</dt>
<dd>ユーザー定義のメタデータ・ストリング。</dd>
<dt>-F, --userfile</dt>
<dd>ユーザー・データをファイルから読み取ります。</dd>
<dt>--public-speed</dt>
<dd>パブリック・ポート速度。オプション: 0、10、100、1000、10000。</dd>
<dt>--private-speed</dt>
<dd>プライベート・ポート速度。オプション: 0、10、100、1000、10000。</dd>
</dl>

**例**:
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを更新し、ドメインを「ibm.com」、ホスト名を「myapp」、タグを「testcli」に設定します。

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

専用仮想サーバーのホストを作成します。
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>必須。 FQDN のホスト部分。</dd>
<dt>-D, --domain</dt>
<dd>必須。 FQDN のドメイン部分。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 データ・センターの短縮名。</dd>
<dt>-s, --size</dt>
<dd>専用ホストのサイズ。現在使用可能なサイズは 56_CORES_X_242_RAM_X_1_4_TB の 1 つのみです。</dd>
<dt>-b, --billing</dt>
<dd>請求レート。 デフォルトは hourly です。 オプション: hourly、monthly。</dd>
<dt>-v, --vlan-private</dt>
<dd>専用ホストを配置するプライベート VLAN の ID。 「ibmcloud sl vlan list」を参照してください。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

ご使用のアカウントの専用ホストをリストします。
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --name</dt>
<dd>専用ホストの名前を基準にフィルター操作します。</dd>
<dt>-d, --datacenter</dt>
<dd>専用ホストのデータ・センターを基準にフィルター操作します。</dd>
<dt>--owner</dt>
<dd>専用ホストの所有者を基準にフィルター操作します。</dd>
<dt>--order</dt>
<dd>この専用ホストを購入した注文の ID を基準にフィルター操作します。</dd>
</dl>

## ibmcloud sl vs list
{: #sl_vs_list}

ご使用のアカウントの仮想サーバー・インスタンスをリストします。
```
ibmcloud sl vs list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>CPU コアの数を基準にフィルター操作します。</dd>
<dt>-D, --domain</dt>
<dd>FQDN のドメイン部分を基準にフィルター操作します。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>-H, --hostname</dt>
<dd>FQDN のホスト部分を基準にフィルター操作します。</dd>
<dt>-m, --memory</dt>
<dd>メガバイト単位のメモリーを基準にフィルター操作します。</dd>
<dt>-n, --network</dt>
<dd>Mbps 単位のネットワーク・ポート速度を基準にフィルター操作します。</dd>
<dt>-P, --public-ip</dt>
<dd>パブリック IP アドレスを基準にしてフィルター操作します。</dd>
<dt>-p, --private-ip</dt>
<dd>プライベート IP アドレスを基準にフィルター操作します。</dd>
<dt>--hourly</dt>
<dd>時間単位のインスタンスのみを表示します。</dd>
<dt>--monthly</dt>
<dd>月単位のインスタンスのみを表示します。</dd>
<dt>-g, --tag</dt>
<dd>タグを基準にフィルター操作します (複数のオカレンスが許可されます)。</dd>
<dt>-o, --order</dt>
<dd>このインスタンスを購入した注文の ID を基準にフィルター操作します。</dd>
<dt>--owner</dt>
<dd>インスタンスを所有するユーザーの ID を基準にフィルター操作します。</dd>
<dt>--sortby</dt>
<dd>ソートの基準にする列。デフォルト: hostname、オプション: id、hostname、domain、datacenter、cpu、memory、public_ip、private_ip。</dd>
<dt>--columns</dt>
<dd>表示する列。デフォルト: id、hostname、public_ip、private_ip、datacenter、action、オプション: guid、power_state、created_by、tags。</dd>
</dl>

**例**:
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
このコマンドは、現行アカウントの、時間ごとに請求されるすべての仮想サーバー・インスタンスをリストします。フィルター基準のドメインは「ibm.com」で、それらをメモリーによってソートします。

## ibmcloud sl vs pause
{: #sl_vs_pause}

アクティブな仮想サーバー・インスタンスを一時停止します。
```
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs pause 12345678 -f
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを、確認を求めずに一時停止します。

## ibmcloud sl vs power-off
{: #sl_vs_power_off}

アクティブな仮想サーバー・インスタンスをパワーオフします。
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--hard</dt>
<dd>ハード・シャットダウンを実行します。</dd>
<dt>--soft</dt>
<dd>ソフト・シャットダウンを実行します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs power-off 12345678 --soft
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのソフト・パワーオフを実行します。

## ibmcloud sl vs power-on
{: #sl_vs_power_on}

仮想サーバー・インスタンスをパワーオンします。
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs power-on 12345678
```
このコマンドは、ID 12345678 の仮想サーバーのパワーオンを実行します。

## ibmcloud sl vs ready
{: #sl_vs_ready}

仮想サーバー・インスタンスの使用準備ができているかどうかをチェックします。
```
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--wait</dt>
<dd>仮想サーバーでのプロビジョニング終了を最大 X 秒待ってから戻ります。</dd>
</dl>

**例**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
このコマンドは、ID 12345678 の仮想サーバーの状況をチェックして、そのインスタンスが、連続して使用する準備ができているかどうか確認し、最大 30 秒待機します。

## ibmcloud sl vs reboot
{: #sl_vs_reboot}

アクティブな仮想サーバー・インスタンスをリブートします。
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--hard</dt>
<dd>ハード・リブートを実行します。</dd>
<dt>--soft</dt>
<dd>ソフト・リブートを実行します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs reboot 12345678 --hard
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのハード・リブートを実行します。

## ibmcloud sl vs reload
{: #sl_vs_reload}

仮想サーバー・インスタンス上でオペレーティング・システムを再ロードします。
```
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>ダウンロードするインストール後スクリプト。</dd>
<dt>--image</dt>
<dd>イメージ ID。 デフォルトは、現行オペレーティング・システムを使用することです。</dd>
<dt>以下を参照してください。</dt>
<dd>「ibmcloud sl image list」。</dd>
<dt>-k, --key</dt>
<dd>root ユーザーに追加する SSH 鍵の ID (複数のオカレンスが許可されます)。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs reload 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスの現行オペレーティング・システムを再ロードします。

## ibmcloud sl vs rescue
{: #sl_vs_rescue}

仮想サーバー・インスタンスをレスキュー・イメージでリブートします。
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs rescue 12345678
```
このコマンドは、ID 12345678 の仮想サーバーをレスキュー・イメージでリブートします。

## ibmcloud sl vs resume
{: #sl_vs_resume}

一時停止された仮想サーバー・インスタンスを再開します。
```
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs resume 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを再開します。

## ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

仮想サーバー・インスタンスを更新します。
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>CPU コアの数。</dd>
<dt>--private</dt>
<dd>CPU コアは、専用ホスト・サーバーに置かれます。</dd>
<dt>-m, --memory</dt>
<dd>メモリー (M バイト)。</dd>
<dt>--network</dt>
<dd>ネットワーク・ポート速度 (Mbps)。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスをアップグレードし、CPU コア数を 8、メモリーを 8192 M、ネットワーク・ポート速度を 1000 Mbps に設定します。
