---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-04"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gerenciando usuários de infraestrutura clássica
{: #manage-sl-users}

Use os comandos a seguir para gerenciar os usuários da infraestrutura clássica do {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

Para criar um usuário:
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>Opções de comando</strong>:
<dl>
<dt>--email</dt>
<dd>Endereço de e-mail para este usuário. Necessário para criação.</dd>
<dt>--password</dt>
<dd>Senha a ser configurada para esse usuário. Se nenhuma senha for fornecida, será enviado a um e-mail ao usuário para gerar uma, que expirará em 24 horas. Especifique a opção '-p generate' para gerar uma senha para você. As senhas requerem 8 ou mais caracteres, caracteres maiúsculos e minúsculos, um número e um símbolo.</dd>
<dt>--from-user</dt>
<dd>Usuário base a ser usado como um modelo para criar esse usuário. O padrão é usar o usuário que está executando esse comando. As informações fornecidas em --template substituem esse modelo.</dd>
<dt>--template</dt>
<dd>Uma sequência JSON que descreve https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/.</dd>
<dt>--api-key</dt>
<dd>Crie uma chave de API para esse usuário.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

Configura o status de um usuário para `CANCEL_PENDING`, que desativa imediatamente a conta e, finalmente, é removido da conta por um processo interno automatizado.
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

Para visualizar os detalhes de um usuário:
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>Opções de comando</strong>:
<dl>
<dt>--keys</dt>
<dd>Mostrar a chave de API de usuários.</dd>
<dt>--permissions</dt>
<dd>Exibir permissões designadas a esse usuário. Os usuários principais não mostrarão nenhuma permissão.</dd>
<dt>--hardware</dt>
<dd>Exibir o hardware ao qual esse usuário tem acesso.</dd>
<dt>--virtual</dt>
<dd>Exibir os guests virtuais aos quais esse usuário tem acesso.</dd>
<dt>--logins</dt>
<dd>Mostrar o histórico de login desse usuário para os últimos 30 dias.</dd>
<dt>--events</dt>
<dd>Mostrar log de auditoria para esse usuário.</dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

Para editar os detalhes de um usuário:
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>Opções de comando</strong>:
<dl>
<dt>--template</dt>
<dd>Uma sequência JSON que descreve https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/.</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

Para ativar ou desativar permissões de usuário específicas:
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>Opções de comando</strong>:
<dl>
<dt>--enable</dt>
<dd>Ativar ou desativar permissões selecionadas. As entradas aceitas são 'true' e 'false'. O padrão é 'true'.</dd>
<dt>--permission</dt>
<dd>Permissão `keyName` para configurar, várias instâncias permitidas. Use a palavra-chave ALL para selecionar TODAS as permissões.</dd>
<dt>--from-user</dt>
<dd>Configurar permissões para corresponder às permissões desse usuário. Inclui e remove as permissões apropriadas.</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

Para listar usuários:
```
ibmcloud sl user list [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--column</dt>
<dd>Coluna a ser exibida. [opções: id,username,email,displayName,status,hardwareCount,virtualGuestCount]  [default: id,username,email,displayName].</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

Para visualizar permissões de usuário:
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

