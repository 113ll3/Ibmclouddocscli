---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# アカウント、ユーザー、および組織の管理
 {: #ibmcloud_commands_account}

<table summary="アカウント、組織、スペース、および役割を管理するために使用できる ibmcloud コマンド。">
<caption>表 1. アカウント、組織、スペース、および役割を管理するためのコマンド</caption>
 <thead>
 <th colspan="5">アカウント、組織、スペース、および役割を管理するためのコマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list](cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users](cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud app domain-cert](cli_acct_org_role.html#ibmcloud_app_domain_cert)</td>
  <td>[ibmcloud app domain-cert-add](cli_acct_org_role.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](cli_acct_org_role.html#ibmcloud_app_domain_cert_remove)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud account orgs
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

## ibmcloud account org
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

## ibmcloud account org-create
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

## ibmcloud account org-replicate
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

## ibmcloud account org-rename
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

## ibmcloud account spaces
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

## ibmcloud account space
{: #ibmcloud_account_space}

このコマンドの機能とオプションは [cf space ![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window} コマンドと同じです。

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

このコマンドの機能とオプションは [cf create-space![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} コマンドと同じです。

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


このコマンドの機能とオプションは [cf rename-space![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} コマンドと同じです。

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


このコマンドの機能とオプションは [cf delete-space![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} コマンドと同じです。

## ibmcloud account org-users
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

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

組織にユーザーを追加します (組織管理者が必要)。

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
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

## ibmcloud account org-roles
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

## ibmcloud account org-role-set
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

## ibmcloud account org-role-unset
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

## ibmcloud account space-users
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

## ibmcloud account space-role-set
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

## ibmcloud account space-role-unset
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

## ibmcloud account list
{: #ibmcloud_account_list}

現行ユーザーのすべてのアカウントをリストします

```
ibmcloud account list
```

<strong>前提条件</strong>: エンドポイント、ログイン

## ibmcloud account org-account
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

## ibmcloud account users
{: #ibmcloud_account_users}

アカウントに関連付けられているユーザーを表示します。 この操作は、アカウントの所有者のみが実行できます。

```
ibmcloud account users
```

## ibmcloud account user-remove
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

## ibmcloud account user-invite
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

## ibmcloud account user-reinvite
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

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

ドメインの証明書情報をリストします。

```
ibmcloud app domain-cert DOMAIN_NAME
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
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

現在の組織内の、指定したドメインに証明書を追加します。

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
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
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

現在の組織内の、指定したドメインから証明書を削除します。

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>DOMAIN (必須)</dt>
   <dd>証明書を削除するドメイン。</dd>
   <dt>-f (オプション)</dt>
   <dd>確認なしで削除を強制します。</dd>
   </dl>
