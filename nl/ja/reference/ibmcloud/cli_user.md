---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-07"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# クラシック・インフラストラクチャーのユーザーの管理
{: #manage-sl-users}

以下のコマンドを使用して、{{site.data.keyword.cloud}} クラシック・インフラストラクチャーのユーザーを管理します。
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

ユーザーを作成するには、次のようにします。
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--email</dt>
<dd>このユーザーの E メール・アドレス。 作成に必要です。</dd>
<dt>--password</dt>
<dd>このユーザーに設定するパスワード。 パスワードが指定されていない場合は、パスワード生成の E メールがユーザーに送信されます。このパスワードは 24 時間で有効期限が切れます。 自分用のパスワードを生成するには '-p generate' オプションを指定します。 パスワードは、8 文字以上の英字の大文字小文字、数字、記号で構成する必要があります。</dd>
<dt>--from-user</dt>
<dd>このユーザーを作成するためのテンプレートとして使用する基本ユーザー。 デフォルトは、このコマンドを実行しているユーザーを使用することです。 --template に指定された情報で、このテンプレートの情報が置き換えられます。</dd>
<dt>--template</dt>
<dd>https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/ を記述する JSON ストリング。</dd>
<dt>--api-key</dt>
<dd>このユーザーの API キーを作成します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

ユーザーの状況を `CANCEL_PENDING` に設定します。これにより、そのアカウントは直ちに無効になり、最終的には自動化された内部プロセスによってアカウントから削除されます。
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

ユーザーの詳細を表示するには、次のようにします。
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--keys</dt>
<dd>ユーザー API キーを表示します。</dd>
<dt>--permissions</dt>
<dd>このユーザーに割り当てられた許可を表示します。 マスター・ユーザーの許可は表示しません。</dd>
<dt>--hardware</dt>
<dd>このユーザーがアクセスできるハードウェアを表示します。</dd>
<dt>--virtual</dt>
<dd>このユーザーがアクセスできる仮想ゲストを表示します。</dd>
<dt>--logins</dt>
<dd>このユーザーの過去 30 日間のログイン履歴を表示します。</dd>
<dt>--events</dt>
<dd>このユーザーの監査ログを表示します。</dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

ユーザーの詳細を編集するには、次のようにします。
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--template</dt>
<dd>https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/ を記述する JSON ストリング。</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

特定のユーザー許可を有効または無効にするには、次のようにします。
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--enable</dt>
<dd>選択した許可を有効または無効にします。 受け入れられる入力は 'true' と 'false' です。 デフォルトは 'true' です。</dd>
<dt>--permission</dt>
<dd>設定する許可 `keyName` (複数インスタンスが許可されます)。 すべての許可を選択するには、キーワード ALL を使用します。</dd>
<dt>--from-user</dt>
<dd>このユーザーの許可に一致する許可を設定します。 該当する許可を追加したり削除したりします。</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

ユーザーをリストするには、次のようにします。
```
ibmcloud sl user list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--column</dt>
<dd>表示する列。 [オプション: id、username、email、displayName、status、hardwareCount、virtualGuestCount][default: id,username,email,displayName]。</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

ユーザー許可を表示するには、次のようにします。
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

