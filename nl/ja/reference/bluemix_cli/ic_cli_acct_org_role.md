---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# アカウント、組織、および役割を管理するための CLI コマンド
 {: #ibmcloud_commands_account}

<table summary="アカウント、組織、スペース、および役割を管理するために使用できる ibmcloud コマンド。">
<caption>表 1. アカウント、組織、スペース、および役割を管理するためのコマンド</caption>
 <thead>
 <th colspan="5">アカウント、組織、スペース、および役割を管理するためのコマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](ic_cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](ic_cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](ic_cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](ic_cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](ic_cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](ic_cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](ic_cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](ic_cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](ic_cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](ic_cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](ic_cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](ic_cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](ic_cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](ic_cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](ic_cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](ic_cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](ic_cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](ic_cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list](ic_cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](ic_cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users](ic_cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](ic_cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](ic_cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](ic_cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](ic_cli_acct_org_role.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](ic_cli_acct_org_role.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-policy](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policy)</td>
  <td>[ibmcloud iam access-group-policy-create](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[ibmcloud iam access-group-policy-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_delete)</td>
 </tr>
 </tbody>
 </table>
 
 ### ibmcloud account orgs
{: #ibmcloud_account_orgs}

すべての組織をリストします。

```
ibmcloud account orgs [-r REGION] [--guid]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-r <i>REGION</i> (オプション)</dt>
   <dd>どの地域の組織情報を表示するかを指定します。 'all' に設定された場合は、すべての地域のすべての組織がリストされます。</dd>
   <dt>--guid (オプション)</dt>
   <dd>組織の GUID を表示します。</dd>
   </dl>

<strong>例</strong>:

地域 `us-south` 内のすべての組織を、GUID の
出力と共にリストします。

```
ibmcloud account orgs -r us-south --guid
```

### ibmcloud account org
{: #ibmcloud_account_org}

指定された組織の情報を表示します。

```
ibmcloud account org ORG_NAME [--guid]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG_NAME (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>--guid (オプション)</dt>
   <dd>組織の GUID を表示します。</dd>
   </dl>

<strong>例</strong>:

組織 `IBM`
の情報を、GUID の出力と共に表示します

```
ibmcloud account org IBM --guid
```

### ibmcloud account org-create
{: #ibmcloud_account_org_create}

新しい組織を作成します。 この操作は、アカウントの所有者のみが実行できます。

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG_NAME (必須)</dt>
   <dd>作成される組織の名前。</dd>
   <dt>-f</dt>
   <dd>確認を求めずに作成を強制します。</dd>
   </dl>

<strong>例</strong>:

名前が `IBM` という組織を作成します。

```
ibmcloud account org-create IBM
```

### ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

現在の地域から別の地域に組織を複製します。

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG_NAME (必須)</dt>
   <dd>複製する既存の組織の名前。</dd>
   <dt>REGION_NAME (必須)</dt>
   <dd>複製された組織をホストする地域の名前。</dd>
   </dl>

<strong>例</strong>:

組織 `myorg` を地域 `eu-gb` に複製します。

```
ibmcloud account org-replicate myorg eu-gb
```

### ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

組織の名前を変更します。 この操作は、組織の管理者のみが実行できます。

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>OLD_ORG_NAME (必須)</dt>
   <dd>名前を変更する組織の古い名前。</dd>
   <dt>NEW_ORG_NAME (必須)</dt>
   <dd>名前を変更する組織の新しい名前。</dd>
   </dl>

### ibmcloud account spaces
{: #ibmcloud_account_spaces}

すべてのスペースをリストします

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-o</dt>
   <dd>組織名。 指定された組織の下のスペースをリストします。 未指定の場合、デフォルトは現行組織です。</dd>
   <dt>-r</dt>
   <dd>地域名。 指定した地域の下のスペースをリストします。 未指定の場合、デフォルトは現行地域です。</dd>
   </dl>

### ibmcloud account space
{: #ibmcloud_account_space}

このコマンドの機能とオプションは [cf space ![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window} コマンドと同じです。

### ibmcloud account space-create
{: #ibmcloud_account_space_create}

このコマンドの機能とオプションは [cf create-space![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} コマンドと同じです。

### ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


このコマンドの機能とオプションは [cf rename-space![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} コマンドと同じです。

### ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


このコマンドの機能とオプションは [cf delete-space![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} コマンドと同じです。

### ibmcloud account org-users
{: #ibmcloud_account_org_users}

指定された組織内のユーザーを役割別に表示します

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>ORG_NAME (必須)</dt>
<dd>組織の名前。</dd>
<dt>-a (オプション)</dt>
<dd>指定された組織内のすべてのユーザーを、役割別にグループ化せずにリストします。</dd>
</dl>

### ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

組織にユーザーを追加します (組織管理者が必要)。

```
 ibmcloud account org-user-add USER_NAME ORG
```

### ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

組織からユーザーを削除します (組織管理者またはユーザー本人のみ)

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--force, -f</dt>
<dd>確認なしで削除を強制します。</dd>
</dl>

### ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

現行ユーザーのすべての組織の役割を取得します

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ユーザー ID。 指定しない場合、現行ユーザーがデフォルトで使用されます。</dd>
  </dl>

### ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

組織の役割をユーザーに割り当てます。 この操作は、組織の管理者のみが実行できます。

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
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
  </dl>

<strong>例</strong>:

ユーザー `Mary` を組織 `IBM` に役割 `OrgManager` として割り当てるには、次のように指定します。

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**注**: 組織/スペースの役割は CLI を使用して設定できますが、その他の許可を設定したい場合は、UI を使用する必要があります。 詳細については、[ユーザー・アクセスの割り当て](/docs/iam/assignaccess.html#assignaccess)を参照してください。
<!-- Begin Staging URL vs Prod URL -->

### ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

組織の役割をユーザーから削除します。 この操作は、組織の管理者のみが実行できます。

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>USER_NAME (必須)</dt>
   <dd>削除されるユーザーの名前。</dd>
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
    </dl>

<strong>例</strong>:

ユーザー `Mary` を組織 `IBM` の役割 `OrgManager` から削除するには、次のように指定します。

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

### ibmcloud account space-users
{: #ibmcloud_account_space_users}

指定されたスペース内のユーザーを役割別に表示します

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>ORG_NAME (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>SPACE_NAME (必須)</dt>
   <dd>スペースの名前。</dd>
   </dl>

### ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

スペースの役割をユーザーに割り当てます。 この操作は、スペースの管理者のみが実行できます。

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
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
   <li>SpaceManager: この役割は、ユーザーの招待と管理を行い、特定のスペースに対してフィーチャーを有効にします。</li>
   <li>SpaceDeveloper: この役割は、アプリとサービスを作成して管理し、ログとレポートを表示します。</li>
   <li>SpaceAuditor: この役割は、ログ、レポート、スペースの設定を表示できます。</li>
   </ul></dd>
    </dl>

<strong>例</strong>:

ユーザー `Mary` を組織 `IBM` およびスペース `Cloud` に役割 `SpaceManager` として割り当てるには、次のように指定します。

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

### ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

スペースの役割をユーザーから削除します。 この操作は、スペースの管理者のみが実行できます。

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>USER_NAME (必須)</dt>
   <dd>削除されるユーザーの名前。</dd>
   <dt>ORG_NAME (必須)</dt>
   <dd>このユーザーの削除元の組織の名前。</dd>
   <dt>SPACE_NAME (必須)</dt>
   <dd>このユーザーの削除元のスペースの名前。</dd>
   <dt>SPACE_ROLE (必須)</dt>
   <dd>このユーザーの削除元のスペース内での役割の名前。 以下に例を示します。
   <ul>
   <li>SpaceManager: この役割は、ユーザーの招待と管理を行い、特定のスペースに対してフィーチャーを有効にします。</li>
   <li>SpaceDeveloper: この役割は、アプリとサービスを作成して管理し、ログとレポートを表示します。</li>
   <li>SpaceAuditor: この役割は、ログ、レポート、スペースの設定を表示できます。</li>
   </ul></dd>
    </dl>


<strong>例</strong>:

ユーザー `Mary` を組織 `IBM` と、役割 `SpaceManager` としてのスペース `Cloud` から削除するには、次のように指定します。

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

### ibmcloud account list
{: #ibmcloud_account_list}

現行ユーザーのすべてのアカウントをリストします

```
ibmcloud account list
```

<strong>前提条件</strong>: エンドポイント、ログイン

### ibmcloud account org-account
{: #ibmcloud_account_org_account}

指定された組織のアカウントを表示します (組織のユーザーが必要)。

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--guid (オプション)</dt>
  <dd>アカウント ID のみを表示します</dd>
</dl>

### ibmcloud account users
{: #ibmcloud_account_users}

アカウントに関連付けられているユーザーを表示します。 この操作は、アカウントの所有者のみが実行できます。

```
ibmcloud account users
```

### ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

アカウントからユーザーを削除します (アカウント所有者のみ)

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

### ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

ユーザーをアカウントに招待します

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>USER_EMAIL (必須)</dt>
   <dd>招待されるユーザーの E メール。</dd>
   <dt>-o ORG</dt>
   <dd>ユーザーを招待する先の組織</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>組織の役割。 有効な入力は、OrgManager、BillingManager、OrgAuditor、および OrgUser です。 省略された場合、OrgUser 役割が設定されます。</dd>
   <dt>-s SPACE</dt>
   <dd>ユーザーを招待する先のスペース</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>スペースの役割。 有効な入力は、SpaceManager、SpaceDeveloper、および SpaceAuditor です。</dd>
</dl>

### ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

ユーザーに招待を再送信します (アカウント管理者)

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
   <dt>USER_EMAIL (必須)</dt>
   <dd>再度招待されるユーザーの E メール。</dd>
</dl>

### ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

現行アカウントのアクセス・グループをリストします

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-u</dt>
  <dd>ユーザーが所属するアクセス・グループをリストします。 このフラグと '-s' を同時に指定することはできません。</dd>
  <dt>-s</dt>
  <dd>サービス ID が所属するアクセス・グループをリストします。 このフラグと '-u' を同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

すべてのアクセス・グループをリストします

```
ibmcloud iam access-groups
```

### ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

アクセス・グループの詳細を表示します

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-id</dt>
  <dd>ID のみを表示します</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` の詳細を表示します。

```
ibmcloud iam access-group example_group
```

### ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

アクセス・グループを作成します

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>アクセス・グループの説明</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` を作成します。

```
ibmcloud iam access-group-create example_group -d "example access group"
```

### ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

アクセス・グループを更新します

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>新規アクセス・グループ名</dd>
  <dt>-d, --description</dt>
  <dd>新規説明</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずに更新を強制します</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` を `hello_world_group` に名前変更します。

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

### ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

アクセス・グループを削除します

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します</dd>
  <dt>-r, --recursive</dt>
  <dd>アクセス・グループとそのメンバーを削除します</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` を削除します。

```
ibmcloud iam access-group-delete example_group --force
```

### ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

アクセス・グループ内のユーザーをリストします

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` 内のすべてのユーザーをリストします。

```
ibmcloud iam access-group-users example_group
```

### ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

アクセス・グループにユーザーを追加します

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

ユーザー `name@example.com` をアクセス・グループ `example_group` に追加します。

```
ibmcloud iam access group-user-add example_group name@example.com
```

### ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

アクセス・グループからユーザーを削除します

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

ユーザー `name@example.com` をアクセス・グループ `example_group` から削除します。

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

### ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

すべてのアクセス・グループからユーザーを削除します

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認を求めずに削除します</dd>
</dl>

<strong>例</strong>:

ユーザー `name@example.com` をすべてのアクセス・グループから削除します。

```
ibmcloud iam access-group-user-purge name@example.com -f
```

### ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

アクセス・グループ内のサービス ID をリストします

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` 内のすべてのサービス ID をリストします。

```
ibmcloud iam access-group-service-ids example_group
```

### ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

サービス ID をアクセス・グループに追加します

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

サービス ID `example-service` をアクセス・グループ `example_group` に追加します。

```
ibmcloud iam access-group-service-id-add example_group example-service
```

### ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

アクセス・グループからサービス ID を削除します

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

サービス ID `example-service` をアクセス・グループ `example_group` から削除します。

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

### ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

サービス ID をすべてのアクセス・グループから削除します

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認を求めずに削除します</dd>
</dl>

<strong>例</strong>:

サービス ID `example-service` をすべてのアクセス・グループからから削除します。

```
ibmcloud iam access-group-service-id-purge example --force
```

### ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

アクセス・グループのポリシーをリストします

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` のすべてのポリシーをリストします。

```
ibmcloud iam access-group-policies example_group
```

### ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

アクセス・グループ・ポリシーの詳細を表示します

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` のポリシー `51b9717e-76b0-4f6a-bda7-b8132431f926` の詳細を表示します

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

### ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

アクセス・グループ・ポリシーを作成します

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--file</dt>
  <dd>ポリシー定義の JSON ファイル</dd>
  <dt>-roles</dt>
  <dd>ポリシー定義の役割名。 特定のサービスの、サポートされる役割については、「ibmcloud iam roles --service SERVICE_NAME」を実行してください。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-service-name</dt>
  <dd>ポリシー定義のサービス名。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>ポリシー定義のサービス・インスタンスの GUID。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-region</dt>
  <dd>ポリシー定義の地域。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-resource-type</dt>
  <dd>ポリシー定義のリソース・タイプ。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-resource</dt>
  <dd>ポリシー定義のリソース。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-resource-group-name</dt>
  <dd>リソース・グループの名前。 このオプションは、「--file」および「--resource-group-id」と同時に指定することはできません。</dd>
  <dt>-resource-group-id</dt>
  <dd>リソース・グループの ID。 このオプションは、「--file」および「--resource-group-name」と同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

JSON ファイルからアクセス・グループ・ポリシーを作成します。

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

`example_group` に、すべての `sample-service` リソースの `Administrator` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

`example_group` に、`us-south` 地域の GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` の `sample-service` インスタンスのリソース `key123` の `Editor` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

`example_group` に、リソース・グループ ID `dda27e49d2a1efca58083a01dfde18f6` の `Operator` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`example_group` に、 リソース・グループ `sample-resource-group` のメンバーの `Viewer` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

`example_group` に、ID `dda27e49d2a1efca58083a01dfde18f6` を持つリソース・グループのメンバーの `Viewer` 役割を与えます。
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

アクセス・グループ・ポリシーを更新します

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>--file</dt>
  <dd>ポリシー定義の JSON ファイル</dd>
  <dt>--roles</dt>
  <dd>ポリシー定義の役割名。 特定のサービスの、サポートされる役割については、「ibmcloud iam roles --service SERVICE_NAME」を実行してください。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-service-name</dt>
  <dd>ポリシー定義のサービス名。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>ポリシー定義のサービス・インスタンスの GUID。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-region</dt>
  <dd>ポリシー定義の地域。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-resource-type</dt>
  <dd>ポリシー定義のリソース・タイプ。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-resource</dt>
  <dd>ポリシー定義のリソース。 このオプションは、「--file」と同時に指定することはできません。</dd>
  <dt>-resource-group-name</dt>
  <dd>リソース・グループの名前。 このオプションは、「--file」および「--resource-group-id」と同時に指定することはできません。</dd>
  <dt>-resource-group-id</dt>
  <dd>リソース・グループの ID。 このオプションは、「--file」および「--resource-group-name」と同時に指定することはできません。</dd>
</dl>

<strong>例</strong>:

ポリシー JSON ファイル内のもので、アクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

`example_group` に、すべての `sample-service` リソースの `Administrator` 役割を与えるようにアクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

`example_group` に、`us-south` 地域の GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` の `sample-service` インスタンスのリソース `key123` の `Editor` 役割を与えるように、アクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

`example_group` に、リソース・グループ ID `dda27e49d2a1efca58083a01dfde18f6` の `Operator` 役割を与えるようにアクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

`example_group` に、リソース・グループ `sample-resource-group` のメンバーの `Viewer` 役割を与えるようにアクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

`example_group` に、ID `dda27e49d2a1efca58083a01dfde18f6` を持つリソース・グループのメンバーの `Viewer` 役割を与えるようにアクセス・グループ・ポリシーを更新します。
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

アクセス・グループ・ポリシーを削除します

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>確認なしで削除を強制します</dd>
</dl>

<strong>例</strong>:

アクセス・グループ `example_group` のポリシー `51b9717e-76b0-4f6a-bda7-b8132431f926` を削除します。
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
