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

# 管理標準基礎架構使用者
{: #manage-sl-users}

請使用下列指令來管理 {{site.data.keyword.cloud}} 標準基礎架構使用者。
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

若要建立使用者，請執行：
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>指令選項</strong>：
<dl>
<dt>--email</dt>
<dd>此使用者的電子郵件位址。建立時需要。</dd>
<dt>--password</dt>
<dd>為此使用者設定的密碼。如果未提供密碼，會傳送一封電子郵件給使用者，以產生一個密碼，該電子郵件會在 24 小時後到期。指定 '-p generate' 選項，可為您產生密碼。密碼需要 8 個字元、大小寫字母、數字及符號。</dd>
<dt>--from-user</dt>
<dd>用來作為建立此使用者之範本的基本使用者。預設為使用執行此指令的使用者。--template 中提供的資訊會取代此範本。</dd>
<dt>--template</dt>
<dd>說明 https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/ 的 JSON 字串。</dd>
<dt>--api-key</dt>
<dd>為此使用者建立 API 金鑰。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

將使用者的狀態設為 `CANCEL_PENDING`，這會立即停用帳戶，最後由自動的內部處理程序從帳戶中移除。
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

若要檢視使用者的詳細資料，請執行：
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>指令選項</strong>：
<dl>
<dt>--keys</dt>
<dd>顯示使用者 API 金鑰。</dd>
<dt>--permissions</dt>
<dd>顯示指派給此使用者的許可權。主要使用者將不顯示任何許可權。</dd>
<dt>--hardware</dt>
<dd>顯示此使用者有權存取的硬體。</dd>
<dt>--virtual</dt>
<dd>顯示此使用者有權存取的虛擬來賓。</dd>
<dt>--logins</dt>
<dd>顯示此使用者在過去 30 天的登入歷程。</dd>
<dt>--events</dt>
<dd>顯示此使用者的審核日誌。</dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

若要編輯使用者的詳細資料，請執行：
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>指令選項</strong>：
<dl>
<dt>--template</dt>
<dd>說明 https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/ 的 JSON 字串。</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

若要啟用或停用特定的使用者許可權，請執行：
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>指令選項</strong>：
<dl>
<dt>--enable</dt>
<dd>啟用或停用選取的許可權。接受的輸入為 'true' 和 'false'。預設值為 'true'。</dd>
<dt>--permission</dt>
<dd>要設定的許可權 `keyName`，接受多個實例。使用關鍵字 ALL 來選取 ALL 許可權。</dd>
<dt>--from-user</dt>
<dd>設定許可權以符合此使用者的許可權。新增及移除適當的許可權。</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

若要列出使用者，請執行：
```
ibmcloud sl user list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--column</dt>
<dd>要顯示的直欄。[選項：id、username、email、displayName、status、hardwareCount、virtualGuestCount]  [預設值：id、username、email、displayName]。</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

若要檢視使用者許可權，請執行：
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

