---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-18"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}

# アカウント、ユーザー、および Cloud Foundry 組織の管理
{: #ibmcloud_commands_account}

以下のコマンドを使用して、パブリック Cloud Foundry 環境のアカウント、アカウントに含まれるユーザー、組織、スペース、および役割を管理します。
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

すべての組織をリストします。
```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>地域名。 指定された地域内の組織をリストします。 未指定の場合、デフォルトは現行地域です。 「all」に設定された場合は、すべての地域の組織をリストします。</dd>
   <dt>--guid</dt>
   <dd>組織の GUID を表示します。 このオプションは、`--output` と同時に指定することはできません。</dd>
   <dt>--output FORMAT</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。 このオプションは、`--guid` と同時に指定することはできません。</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>アカウント ID。 アカウントの下の組織をリストします。 未指定の場合、デフォルトは現行アカウントです。 `all` に設定された場合、すべてのアカウントの下の組織をリストします。 このオプションは、`-u` と同時に指定することはできません。</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>アカウント所有者名。 ユーザーが所有するアカウントの下の組織をリストします。 未指定の場合、デフォルトは現行アカウントです。 「all」に設定された場合、すべてのアカウントの下の組織をリストします。 このオプションは、`-c` と同時に指定することはできません。</dd>
   </dl>

<strong>例</strong>:

地域 `us-south` 内のすべての組織を、GUID の出力と共にリストします。
```
ibmcloud account orgs -r us-south --guid
```

すべての組織を JSON 形式でリストします。
```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

指定された組織の情報を表示します。
```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG_NAME (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>-r REGION</dt>
   <dd>地域名。 指定しない場合、デフォルトは現行地域です。 `all` に設定された場合は、すべての地域の指定された名前の組織がリストされます。</dd>
   <dt>--guid</dt>
   <dd>組織の GUID を取得して表示します。 この組織の他の出力はすべて抑制されます。 このオプションは、`--output` と同時に指定することはできません。</dd>
   <dt>--output REGION</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。 このオプションは、`--guid` と同時に指定することはできません。</dd>
   </dl>

<strong>例</strong>:

組織 `IBM` の情報を、GUID の出力と共に表示します。
```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

組織を作成します。 この操作は、アカウントの所有者のみが実行できます。
```
ibmcloud account org-create ORG_NAME [-r, --region REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG_NAME (必須)</dt>
   <dd>作成される組織の名前。</dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
   </dl>

<strong>例</strong>:

名前が `IBM` という組織を作成します。
```
ibmcloud account org-create IBM 
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

現在の地域から別の地域に組織を複製します。
```
ibmcloud account org-replicate ORG_NAME REGION_NAME [-r, --region SOURCE_REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG_NAME (必須)</dt>
   <dd>複製する既存の組織の名前。</dd>
   <dt>REGION_NAME (必須)</dt>
   <dd>複製された組織をホストする地域の名前。</dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
   </dl>

<strong>例</strong>:

組織 `myorg` を地域 `eu-gb` に複製します。
```
ibmcloud account org-replicate myorg eu-gb
```

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

組織の名前を変更します。 この操作は、組織の管理者のみが実行できます。
```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME [-r, --region REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>OLD_ORG_NAME (必須)</dt>
   <dd>名前を変更する組織の古い名前。</dd>
   <dt>NEW_ORG_NAME (必須)</dt>
   <dd>名前を変更する組織の新しい名前。</dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

すべてのアカウント・スペースをリストします。
```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-o ORG_NAME (オプション)</dt>
   <dd>組織名。 指定された組織の下のスペースをリストします。 未指定の場合、デフォルトは現行組織です。</dd>
   <dt>-r REGION-NAME (オプション)</dt>
   <dd>地域名。 指定した地域の下のスペースをリストします。 未指定の場合、デフォルトは現行地域です。</dd>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
   </dl>

<strong>例</strong>:

すべてのスペースをリストします
```
ibmcloud account spaces
```

組織 `org_example` のすべてのスペースを JSON 形式でリストします。
```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

特定のスペースの情報を表示します。
```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>SPACE_NAME (必須)</dt>
   <dd>表示するスペースの名前。</dd>
   <dt>-o ORG_NAME</dt>
   <dd>組織名。 未指定の場合、デフォルトは現行組織です。</dd>
   <dt>--guid</dt>
   <dd>スペースの GUID を取得して表示します。 このスペースの他の出力はすべて抑制されます。 このオプションは、`--output` と同時に指定することはできません。</dd>
   <dt>--output FORMAT</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。 このスペースの他の出力はすべて抑制されます。 このオプションは、`--guid` と同時に指定することはできません。</dd>
   <dt>--security-group-rules</dt>
   <dd>このスペースに関連付けられているすべてのセキュリティー・グループのルールを取得します。</dd>
   </dl>

<strong>例</strong>:

スペース `space_example` の情報を表示します。
```
ibmcloud account space space_example
```

スペース `space_example` の GUID を表示します。
```
ibmcloud account space space_example --guid
```

スペース `space_example` の情報を JSON 形式で表示します。
```
ibmcloud account space space_example --output JSON
```

スペース `space_example` のセキュリティー・グループ・ルールを表示します。
```
ibmcloud account space space_example --security-group-rules
```

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

このコマンドの機能とオプションは [`cf create-space`](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") コマンドと同じです。

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}

このコマンドの機能とオプションは [`cf rename-space`](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") コマンドと同じです。

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}

このコマンドの機能とオプションは [`cf delete-space`](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") コマンドと同じです。

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

指定された組織内のユーザーを役割別に表示します

```
ibmcloud account org-users ORG_NAME [-r, --region REGION] [-a, --all]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>ORG_NAME (必須)</dt>
<dd>組織の名前。</dd>
<dt>-a, -all (オプション)</dt>
<dd>指定された組織内のすべてのユーザーを、役割別にグループ化せずにリストします。</dd>
<dt>-r, --region REGION (オプション)</dt>
<dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
</dl> 

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

組織にユーザーを追加します (組織管理者が必要)。
```
 ibmcloud account org-user-add USER_NAME ORG [-r, --region REGION]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>USER_NAME (必須)</dt>
<dd>ユーザーの名前。</dd>
<dt>ORG (必須)</dt>
<dd>組織の名前。</dd>
<dt>-r, --region REGION (オプション)</dt>
<dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
</dl>  

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

組織からユーザーを削除します (組織管理者またはユーザーのみ)。
```
ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--force, -f</dt>
<dd>確認なしで削除を強制します。</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

現行ユーザーのすべての組織の役割を取得します。
```
ibmcloud account org-roles [-r, --region REGION] [-u USER_ID] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ユーザー ID。 指定しない場合、現行ユーザーがデフォルトで使用されます。</dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

組織の役割をユーザーに割り当てます。 この操作は、組織の管理者が実行する必要があります。
```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>USER_NAME (必須)</dt>
   <dd>割り当てられるユーザーの名前。</dd>
   <dt>ORG_NAME (必須)</dt>
   <dd>このユーザーの割り当て先の組織の名前。</dd>
   <dt>ORG_ROLE (必須)</dt>
   <dd>このユーザーの割り当て先の組織内での役割の名前。 以下に例を示します。
   <ul>
   <li>OrgManager: この役割は、ユーザーの招待と管理、プランの選択と変更、支払上限の設定を行います。</li>
   <li>BillingManager: この役割は、請求アカウントと支払い情報の作成および管理を行えます。</li>
   <li>OrgAuditor: この役割は、組織の情報とレポートに読み取りアクセスだけが可能です。</li>
   </ul>
   </dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
  </dl>

<strong>例</strong>:

ユーザー `Mary` を組織 `IBM` に役割 `OrgManager` として割り当てるには、次のように指定します。
```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
組織およびスペースの役割は CLI を使用して設定できますが、その他の許可を設定したい場合は UI を使用する必要があります。 詳しくは、[リソースに対するアクセス権限の管理](/docs/iam?topic=iam-iammanidaccser)を参照してください。
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

組織の役割をユーザーから削除します。 この操作は、組織の管理者のみが実行できます。
```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>USER_NAME (必須)</dt>
   <dd>削除するユーザーの名前。</dd>
   <dt>ORG_NAME (必須)</dt>
   <dd>このユーザーの削除元の組織の名前。</dd>
   <dt>ORG_ROLE (必須)</dt>
   <dd>このユーザーの削除元の組織内での役割の名前。 以下に例を示します。
   <ul>
   <li>OrgManager: この役割は、ユーザーの招待と管理、プランの選択と変更、支払上限の設定を行います。</li>
   <li>BillingManager: この役割は、請求アカウントと支払い情報の作成および管理を行えます。</li>
   <li>OrgAuditor: この役割は、組織の情報とレポートに読み取りアクセスだけが可能です。</li>
   </ul>
   </dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
   </dl>

<strong>例</strong>:

ユーザー `Mary` を組織 `IBM` の役割 `OrgManager` から削除するには、次のように指定します。
```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

指定されたスペース内のユーザーを役割別に表示します
```
ibmcloud account space-users ORG_NAME SPACE_NAME [-r, --region REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG_NAME (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>SPACE_NAME (必須)</dt>
   <dd>スペースの名前。</dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
   </dl>

## ibmcloud account space-roles
{: #ibmcloud_account_space_roles}

特定の組織の現行のユーザーの、すべてのスペースの役割を取得します

```
ibmcloud account space-roles ORG [-r, --region REGION] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>-r (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

スペースの役割をユーザーに割り当てます。 この操作は、スペースの管理者のみが実行できます。
```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>USER_NAME (必須)</dt>
   <dd>割り当てられるユーザーの名前。</dd>
   <dt>ORG_NAME (必須)</dt>
   <dd>このユーザーの割り当て先の組織の名前。</dd>
   <dt>SPACE_NAME (必須)</dt>
   <dd>このユーザーの割り当て先のスペースの名前。</dd>
   <dt>SPACE_ROLE (必須)</dt>
   <dd>このユーザーの割り当て先のスペース内での役割の名前。 以下に例を示します。
   <ul>
   <li>SpaceManager: この役割は、ユーザーの招待と管理を行い、フィーチャーを有効にします。</li>
   <li>SpaceDeveloper: この役割は、アプリとサービスを作成して管理し、ログとレポートを表示します。</li>
   <li>SpaceAuditor: この役割は、ログ、レポート、スペースの設定を表示できます。</li>
   </ul>
   </dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
   </dl>

<strong>例</strong>:

ユーザー `Mary` を組織 `IBM` およびスペース `Cloud` に役割 `SpaceManager` として割り当てるには、次のように指定します。
```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

スペースの役割をユーザーから削除します。 この操作は、スペースの管理者のみが実行できます。
```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>USER_NAME (必須)</dt>
   <dd>削除するユーザーの名前。</dd>
   <dt>ORG_NAME (必須)</dt>
   <dd>このユーザーの削除元の組織の名前。</dd>
   <dt>SPACE_NAME (必須)</dt>
   <dd>このユーザーの削除元のスペースの名前。</dd>
   <dt>SPACE_ROLE (必須)</dt>
   <dd>このユーザーの削除元のスペース内での役割の名前。 以下に例を示します。
   <ul>
   <li>SpaceManager: この役割は、ユーザーの招待と管理を行い、フィーチャーを有効にします。</li>
   <li>SpaceDeveloper: この役割は、アプリとサービスを作成して管理し、ログとレポートを表示します。</li>
   <li>SpaceAuditor: この役割は、ログ、レポート、スペースの設定を表示できます。</li>
   </ul></dd>
   <dt>-r, --region REGION (オプション)</dt>
   <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
    </dl>


<strong>例</strong>:

ユーザー `Mary` を組織 `IBM` と、役割 `SpaceManager` としてのスペース `Cloud` から削除するには、次のように指定します。
```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

現行ユーザーのすべてのアカウントをリストします。
```
ibmcloud account list [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

指定された組織のアカウントを表示します (組織のユーザーが必要)。
```
ibmcloud account org-account ORG_NAME [-r, --region REGION] [--guid | --output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-r (オプション)</dt>
  <dd>地域名。 未指定の場合、デフォルトは現行地域です。</dd>
  <dt>--guid (オプション)</dt>
  <dd>アカウント ID のみを表示します</dd>
  <dt>--output FORMAT (オプション)</dt>
  <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

アカウントの詳細を表示します。
```
ibmcloud account show
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

現在のターゲット・アカウントの詳細を表示します
```
ibmcloud account show
```

## ibmcloud account update
{: #ibmcloud_account_update}

特定のアカウントを更新します。
```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>SoftLayer アカウントのサービス・エンドポイント接続を有効または無効にします。</dd>
</dl>

<strong>例</strong>:

現行アカウントのサービス・エンドポイント接続を有効にします。
```
ibmcloud account update --service-endpoint-enable true
```

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

SoftLayer アカウント監査ログをリストします。
```
account audit-logs [-u, --user-name USER_NAME] [-t, --object-type OBJECT_TYPE] [-o, --object OBJECT] [-a, --action ACTION] [-s, --start-date START_DATE] [-e, --end-date END_DATE]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-a, --action <i>ACTION</i></dt>
  <dd>アクション。 アクションの監査ログをリストします。</dd>
  <dt>-e, --end-date <i>END_DATE</i></dt>
  <dd>終了日。 終了日より前の監査ログをリストします。 サポートされる形式は、yyyy-MM-ddTHH:mm:ss です。</dd>
  <dt>-o, --object <i>OBJECT</i></dt>
  <dd>オブジェクト。 オブジェクトの監査ログをリストします。</dd>
  <dt>-t, --object-type <i>OBJECT_TYPE</i></dt>
  <dd>オブジェクト・タイプ。 オブジェクト・タイプの監査ログをリストします。</dd>
  <dt>-s, --start-date <i>START_DATE</i></dt>
  <dd>開始日。 開始日より後の監査ログをリストします。 サポートされる形式は、yyyy-MM-ddTHH:mm:ss です。</dd>
  <dt>-u, --user-name <i>USER_NAME</i></dt>
  <dd>ユーザー名。 ユーザー名の監査ログをリストします。</dd>
</dl>

<strong>例</strong>:

監査ログをリストします。
```
ibmcloud account audit-logs
```

## ibmcloud account users
{: #ibmcloud_account_users}

アカウントに関連付けられているユーザーを表示します。 この操作は、アカウント所有者が実行する必要があります。
```
ibmcloud account users [-c, --account-id ACCOUNT_ID] [--output FORMAT]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>-c (オプション)</dt>
<dd>アカウント ID。 指定しない場合、現行アカウントがデフォルトで使用されます。</dd>
<dt>--output FORMAT (オプション)</dt>
<dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

アカウントからユーザーを削除します (アカウント所有者のみ)。
```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>USER_ID (必須)</dt>
<dd>ユーザー ID</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>アカウント ID。 指定しない場合、現行アカウントがデフォルトで使用されます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで削除を強制します。</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

ユーザーをアカウントに招待します。
```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>USER_EMAIL (必須)</dt>
   <dd>招待するユーザーの E メール。</dd>
   <dt>-o ORG</dt>
   <dd>ユーザーを招待する先の組織</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>組織の役割。 有効な入力は、OrgManager、BillingManager、OrgAuditor、および OrgUser です。 省略された場合、OrgUser 役割が設定されます。</dd>
   <dt>-s SPACE</dt>
   <dd>ユーザーを招待する先のスペース</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>スペースの役割。 有効な入力は、SpaceManager、SpaceDeveloper、および SpaceAuditor です。</dd>
</dl>

アクセス権限を割り当てる準備ができていない場合、または Cloud Foundry アクセス権限の代わりに IAM ポリシーを割り当てる場合は、アクセス権限なしでユーザーを招待し、後でアクセス権限を割り当てることができます。 ユーザーへのアクセス権限の割り当てについて詳しくは、[リソースに対するアクセス権限の管理](/docs/iam?topic=iam-iammanidaccser#assign_new_access)を参照してください。
{: tip}

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

ユーザーに招待を再送信します (アカウント管理者)。
```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>USER_EMAIL (必須)</dt>
   <dd>再度招待するユーザーの E メール。</dd>
</dl>

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

アカウント監査ログをリストします

```
ibmcloud account audit-logs [--user-name USER_NAME] [--object-type OBJECT_TYPE] [--object OBJECT] [--action ACTION] [--start-date START_DATE] [--end-date END_DATE] [--output FORMAT]
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>--user-name <i>USER_NAME</i> (オプション)</dt>
   <dd>ユーザー名の監査ログをリストします。</dd>
   <dt>--object-type <i>OBJECT_TYPE</i> (オプション)</dt>
   <dd>オブジェクト・タイプの監査ログをリストします。</dd>
   <dt>--object <i>OBJECT</i> (オプション)</dt>
   <dd>オブジェクトの監査ログをリストします。</dd>
   <dt>--action <i>ACTION</i> (オプション)</dt>
   <dd>アクションの監査ログをリストします。</dd>
   <dt>--start-date <i>START_DATE</i> (オプション)</dt>
   <dd>開始日より後の監査ログをリストします。 サポートされる形式は、yyyy-MM-ddTHH:mm:ss です。</dd>
   <dt>--end-date <i>END_DATE</i> (オプション)</dt>
   <dd>終了日より前の監査ログをリストします。 サポートされる形式は、yyyy-MM-ddTHH:mm:ss です。</dd>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud account user-preference
{: #ibmcloud_account_user_preference}

ユーザー設定の詳細を表示します

```
ibmcloud account user-preference [--output FORMAT]
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud account user-preference-update
{: #ibmcloud_account_user_preference_update}

ユーザー設定を更新します

```
ibmcloud account user-preference-update (--position NEW_POSITION) [--output FORMAT]
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>--position <i>NEW_POSITION</i> (オプション)</dt>
   <dd>ユーザーのポジションを設定します ('manager' や 'student'など)。</dd>
   <dt>--output FORMAT (オプション)</dt>
   <dd>出力形式を指定します。現在、JSON のみがサポートされています。</dd>
</dl>

## ibmcloud account platform-notification-subscribe
{: #ibmcloud_account_platform_notification_subscribe}

プラットフォーム通知をサブスクライブします。
```
ibmcloud account platform-notification-subscribe (--type TYPE)
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>--type <i>TYPE</i> (オプション)</dt>
   <dd>通知タイプ ('unplanned_events' と 'planned_maintenance' のいずれか)。</dd>
</dl>

## ibmcloud account platform-notification-unsubscribe
{: #ibmcloud_account_platform_notification_unsubscribe}

プラットフォーム通知をアンサブスクライブします。
```
ibmcloud account platform-notification-unsubscribe (--type TYPE)
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>--type <i>TYPE</i> (オプション)</dt>
   <dd>通知タイプ ('unplanned_events' と 'planned_maintenance' のいずれか)。</dd>
</dl>

## ibmcloud account domain-cert
{: #ibmcloud_account_domain_cert}

ドメインの証明書情報をリストします。
```
ibmcloud account domain-cert DOMAIN_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>DOMAIN_NAME (必須)</dt>
<dd>証明書をホストするドメイン。</dd>
</dl>


<strong>例</strong>:

ドメイン `ibmcxo-eventconnect.com` の証明書情報を表示するには、次のように指定します。
```
ibmcloud account domain-cert ibmcxo-eventconnect.com
```

## ibmcloud account domain-cert-add
{: #ibmcloud_account_domain_cert_add}

現在の組織内の、指定したドメインに証明書を追加します。
```
ibmcloud account domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>DOMAIN (必須)</dt>
   <dd>証明書を追加するドメイン。</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (必須)</dt>
   <dd>秘密鍵ファイル・パス。</dd>
   <dt>-c <i>CERT_FILE</i> (必須)</dt>
   <dd>証明書ファイル・パス。</dd>
   <dt>-p <i>PASSWORD</i> (オプション)</dt>
   <dd>証明書のパスワード。</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (オプション)</dt>
   <dd>中間証明書ファイル・パス。</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (オプション)</dt>
   <dd>トラストストア・ファイル。</dd>
   </dl>


<strong>例</strong>:

ドメイン `ibmcxo-eventconnect.com` に証明書を追加するには、以下のように指定します。
```
ibmcloud account domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud account domain-cert-remove
{: #ibmcloud_account_domain_cert_remove}

現在の組織内の、指定したドメインから証明書を削除します。
```
ibmcloud account domain-cert-remove DOMAIN [-f]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>DOMAIN (必須)</dt>
   <dd>証明書を削除するドメイン。</dd>
   <dt>-f (オプション)</dt>
   <dd>確認なしで削除を強制します。</dd>
   </dl>
