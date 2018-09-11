---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cloud Foundry エンタープライズ環境 (CFEE) (ベータ)
{: #ibmcloud_commands_cfee}

以下のコマンドを使用して、CFEE 組織、スペース、ユーザー、および役割を管理します。
{: shortdesc}

<table summary="Cloud Foundry エンタープライズ環境の管理 (試験的)">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 <td>[ibmcloud cfee orgs
](cli_cfee.html#ibmcloud_cfee_orgs)</td>
 <td>[ibmcloud cfee org](cli_cfee.html#ibmcloud_cfee_org)</td>
 <td>[ibmcloud cfee org-create](cli_cfee.html#ibmcloud_cfee_org_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee org-delete](cli_cfee.html#ibmcloud_cfee_org_delete)</td>
 <td>[ibmcloud cfee org-users](cli_cfee.html#ibmcloud_cfee_org_users)</td>
 <td>[ibmcloud cfee org-role-set](cli_cfee.html#ibmcloud_cfee_org_role_set)</td>
 <td>[ibmcloud cfee org-role-unset](cli_cfee.html#ibmcloud_cfee_org_role_unset)</td>
 <td>[ibmcloud cfee spaces](cli_cfee.html#ibmcloud_cfee_spaces)</td>
 </tr>
<tr>
 <td>[ibmcloud cfee space](cli_cfee.html#ibmcloud_cfee_space)</td>
 <td>[ibmcloud cfee space-create](cli_cfee.html#ibmcloud_cfee_space_create)</td>
 <td>[ibmcloud cfee space-rename](cli_cfee.html#ibmcloud_cfee_space_rename)</td>
 <td>[ibmcloud cfee space-delete](cli_cfee.html#ibmcloud_cfee_space_delete)</td>
 <td>[ibmcloud cfee space-role-set](cli_cfee.html#ibmcloud_cfee_space_role_set)</td>
 </tr>
 <tr>

 <td>[ibmcloud cfee space-role-unset](cli_cfee.html#ibmcloud_cfee_space_role_unset)</td>
 <td>[ibmcloud cfee space-roles](cli_cfee.html#ibmcloud_cfee_space_roles)</td>
 <td>[ibmcloud cfee space-users](cli_cfee.html#ibmcloud_cfee_space_users)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

CFEE 環境をリストします。

```
ibmcloud cfee environments
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

CFEE 環境の詳細を表示します

```
ibmcloud cfee environment NAME [--id]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>NAME (必須)</dt>
   <dd>表示する環境の名前。</dd>
   <dt>--id</dt>
   <dd>ID のみを表示します</dd>
  </dl>

<strong>例</strong>:

CFEE 環境 `env_example` の詳細を表示します。

```
ibmcloud cfee environment env_example
```

CFEE 環境 `env_example` の ID を表示します。

```
ibmcloud cfee environment env_example --id
```

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

すべての組織をリストします

```
ibmcloud cfee orgs [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

すべての組織をリストします。

```
ibmcloud cfee orgs
```

CFEE 環境 `env_example` のすべての組織をリストします。

```
ibmcloud cfee orgs --env env_example
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

組織の詳細を表示します

```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>ORG (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
   <dt>--guid</dt>
   <dd>組織 GUID のみを表示します。組織の他の出力はすべて抑制されます。</dd>
  </dl>

<strong>例</strong>:

CFEE 組織 `org_example` の詳細を表示します。

```
ibmcloud cfee org org_example
```

CFEE 環境 `env_example` の CFEE 組織 `org_example` の詳細を表示します。

```
ibmcloud cfee org org_example --env env_example
```

CFEE 組織 `org_example` の GUID を表示します。

```
ibmcloud cfee org org_example --guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

組織を作成します

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>ORG (必須)</dt>
   <dd>作成される組織の名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>新しく作成された組織に割り当てる割り当て量 (指定されなければ、デフォルトの割り当て量を使用)</dd>
  </dl>

<strong>例</strong>:

CFEE 組織 `org_example` を作成します。

```
ibmcloud cfee org-create org_example
```

CFEE 環境 `env_example` の CFEE 組織 `org_example` を作成します。

```
ibmcloud cfee org-create org_example --env env_example
```

CFEE 組織 `org_example` を割り当て量 `quote_example` で作成します。

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

組織を削除します

```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>ORG (必須)</dt>
   <dd>削除される組織の名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで削除を強制します</dd>
  </dl>

<strong>例</strong>:

CFEE 組織 `org_example` を削除します。

```
ibmcloud cfee org-delete org_example
```

CFEE 環境 `env_example` の CFEE 組織 `org_example` を削除します。

```
ibmcloud cfee org-delete org_example --env env_example
```

確認なしで CFEE 組織 `org_example` を削除します。

```
ibmcloud cfee org org-delete org_example -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

指定された組織内のユーザーを役割別に表示します

```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>ORG (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>-a, --all</dt>
   <dd>指定された組織内のすべてのユーザーをリストします</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

CFEE 組織 `org_example` 内のユーザーを表示します。

```
ibmcloud cfee org-users org_example
```

CFEE 環境 `env_example` の CFEE 組織 `org_example` 内のユーザーを表示します。

```
ibmcloud cfee org-users org_example --env env_example
```

CFEE 組織 `org_example` 内のすべてのユーザーをリストします。

```
ibmcloud cfee org-users org_example -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

ユーザーに組織の役割を割り当てます (組織管理者が必要)

```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>USER_EMAIL (必須)</dt>
   <dd>割り当てられるユーザーの E メール。</dd>
   <dt>ORG (必須)</dt>
   <dd>このユーザーの割り当て先の組織の名前。</dd>
   <dt>ROLE (必須)</dt>
   <dd>このユーザーの割り当て先の組織内での役割の名前。 以下に例を示します。
   <ul>
   <li>OrgManager: この役割は、ユーザーの招待と管理、プランの選択と変更、支払上限の設定を行います。</li>
   <li>BillingManager: この役割は、請求アカウントと支払い情報の作成および管理を行えます。</li>
   <li>OrgAuditor: この役割は、組織の情報とレポートに読み取りアクセスだけが可能です。</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

組織 `org_example` 内のユーザー `test@exmaple.com` に役割 `BillingManager` を割り当てます。

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```

CFEE 環境 `env_example` の組織 `org_example` 内のユーザー `test@exmaple.com` に役割 `BillingManager` を割り当てます。

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

ユーザーから組織の役割を削除します (組織管理者またはユーザー本人のみ)

```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>USER_EMAIL (必須)</dt>
   <dd>削除されるユーザーの E メール。</dd>
   <dt>ORG (必須)</dt>
   <dd>このユーザーの削除元の組織の名前。</dd>
   <dt>ROLE (必須)</dt>
   <dd>このユーザーの削除元の組織内での役割の名前。 以下に例を示します。
   <ul>
   <li>OrgManager: この役割は、ユーザーの招待と管理、プランの選択と変更、支払上限の設定を行います。</li>
   <li>BillingManager: この役割は、請求アカウントと支払い情報の作成および管理を行えます。</li>
   <li>OrgAuditor: この役割は、組織の情報とレポートに読み取りアクセスだけが可能です。</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

組織 `org_example` からユーザー `test@exmaple.com` の役割 `BillingManager` を削除します。

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```

CFEE 環境 `env_example` の組織 `org_example` から、ユーザー `test@exmaple.com` の役割 `BillingManager` を削除します。

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

すべてのスペースをリストします

```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>組織名。 未指定の場合、デフォルトは現行組織です。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

すべてのスペースをリストします

```
ibmcloud cfee spaces
```

組織 `org_example` および CFEE 環境 `env_example` のすべてのスペースをリストします

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

指定されたスペースの情報を表示します

```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>SPACE (必須)</dt>
   <dd>表示するスペースの名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
   <dt>--guid</dt>
   <dd>指定されたスペースの GUID を取得して表示します。 このスペースの他の出力はすべて抑制されます。</dd>
   <dt>-o, --org ORG</dt>
   <dd>組織名。 未指定の場合、デフォルトは現行組織です。</dd>
   <dt>--security-group-rules</dt>
   <dd>このスペースに関連付けられているすべてのセキュリティー・グループのルールを取得します。</dd>
  </dl>

<strong>例</strong>:

スペース `space_example` の情報を表示します。

```
ibmcloud cfee space space_example
```

スペース `space_example` の guid を取得して表示します。

```
ibmcloud cfee space space_example --guid
```

スペース `space_example` と関連付けられたすべてのセキュリティー・グループのルールを表示します。

```
ibmcloud cfee space space_example --security-group-rules
```

組織 `org_example` および CFEE 環境 `env_example` のスペース `space_example` の情報を表示します。

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

新規スペースを作成します

```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>SPACE (必須)</dt>
   <dd>作成するスペースの名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
   <dt>-o, --org ORG</dt>
   <dd>組織名。 未指定の場合、デフォルトは現行組織です。</dd>
  </dl>

<strong>例</strong>:

新規スペース `space_example` を作成します。

```
ibmcloud cfee space-create space_example
```

組織 `org_example` および CFEE 環境 `env_example` の下に新規スペース `space_example` を作成します。

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

スペースを名前変更します

```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>OLD_NAME (必須)</dt>
   <dd>名前を変更するスペースの古い名前。</dd>
   <dt>NEW_NAME (必須)</dt>
   <dd>名前を変更するスペースの新しい名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
   <dt>-o, --org ORG</dt>
   <dd>組織名。 未指定の場合、デフォルトは現行組織です。</dd>
  </dl>

<strong>例</strong>:

スペース `space_example` を `new_pace_example` に名前変更します。

```
ibmcloud cfee space-rename space_example new_pace_example
```

組織 `org_example` および CFEE 環境 `env_example` の下でスペース `space_example` を `new_pace_example` に名前変更します。

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

スペースを削除します

```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>SPACE (必須)</dt>
   <dd>削除するスペースの名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで削除を強制します。</dd>
   <dt>-o, --org ORG</dt>
   <dd>組織名。 未指定の場合、デフォルトは現行組織です。</dd>
  </dl>

<strong>例</strong>:

スペース `space_example` を削除します。

```
ibmcloud cfee space-delete space_example
```

組織 `org_example` および CFEE 環境 `env_example` の下のスペース `space_example` を確認なしで削除します。

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

スペースの役割をユーザーに割り当てます

```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>USER_EMAIL (必須)</dt>
   <dd>割り当てられるユーザーの E メール。</dd>
   <dt>ORG (必須)</dt>
   <dd>このユーザーの割り当て先の組織の名前。</dd>
   <dt>SPACE (必須)</dt>
   <dd>このユーザーの割り当て先のスペースの名前。</dd>
   <dt>ROLE (必須)</dt>
   <dd>このユーザーの割り当て先のスペース内での役割の名前。 以下に例を示します。
   <ul>
   <li>SpaceManager: この役割は、ユーザーの招待と管理を行い、特定のスペースに対してフィーチャーを有効にします。</li>
   <li>SpaceDeveloper: この役割は、アプリとサービスを作成して管理し、ログとレポートを表示します。</li>
   <li>SpaceAuditor: この役割は、ログ、レポート、スペースの設定を表示できます。</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

ユーザー `test@exmaple.com` を、`SpaceManager` 役割として組織 `org_example` およびスペース `space_example` に割り当てます。

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

ユーザー `test@exmaple.com` を、環境 `env_example` の下で、`SpaceManager` 役割として組織 `org_example` およびスペース `space_example` に割り当てます。

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

スペースの役割をユーザーから削除します

```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>USER_EMAIL (必須)</dt>
   <dd>削除されるユーザーの E メール。</dd>
   <dt>ORG (必須)</dt>
   <dd>このユーザーの削除元の組織の名前。</dd>
   <dt>SPACE (必須)</dt>
   <dd>このユーザーの削除元のスペースの名前。</dd>
   <dt>ROLE (必須)</dt>
   <dd>このユーザーの削除元のスペース内での役割の名前。 以下に例を示します。
   <ul>
   <li>SpaceManager: この役割は、ユーザーの招待と管理を行い、特定のスペースに対してフィーチャーを有効にします。</li>
   <li>SpaceDeveloper: この役割は、アプリとサービスを作成して管理し、ログとレポートを表示します。</li>
   <li>SpaceAuditor: この役割は、ログ、レポート、スペースの設定を表示できます。</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

ユーザー `test@exmaple.com` から、組織 `org_example` およびスペース `space_example` の `SpaceManager` としての役割を削除します。

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

ユーザー `test@exmaple.com` から、組織 `org_example` およびスペース `space_example` の環境 `env_example` の下での `SpaceManager` としての役割を削除します。

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

特定の組織の現行のユーザーの、すべてのスペースの役割を取得します

```
ibmcloud cfee space-roles ORG [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>ORG (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

組織 `org_example` の現行ユーザーのすべてのスペースの役割を取得します。

```
ibmcloud cfee space-roles org_example
```

組織 `org_example` および環境 `env_example` の現行ユーザーのすべてのスペースの役割を取得します。

```
ibmcloud cfee space-roles org_example --env env_example
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

指定されたスペース内のユーザーを役割別に表示します

```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>ORG (必須)</dt>
   <dd>組織の名前。</dd>
   <dt>SPACE (必須)</dt>
   <dd>スペースの名前。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名。未指定の場合、デフォルトは現行の CFEE 環境です。</dd>
  </dl>

<strong>例</strong>:

スペース `space_example` および組織 `org_example` 内のすべてのユーザーを表示します。

```
ibmcloud cfee space-users org_example space_example
```

スペース `space_example`、組織 `org_example`、環境 `env_example` 内のすべてのユーザーを表示します。

```
ibmcloud cfee space-users org_example space_example --env env_example
```
