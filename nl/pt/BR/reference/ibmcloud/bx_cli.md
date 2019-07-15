---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-10"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# Comandos gerais da CLI (ibmcloud)
{: #ibmcloud_cli}

A interface da linha de comandos (CLI) do {{site.data.keyword.cloud_notm}} fornece um conjunto de comandos que são agrupados por namespace para que os usuários interajam com o {{site.data.keyword.cloud_notm}}.
{: shortdesc}

O cliente da linha de comando do {{site.data.keyword.cloud_notm}} empacota um cliente da linha de comando do Cloud Foundry em sua instalação. Se você tiver a sua própria CLI do Cloud Foundry instalada, não use os comandos da CLI do {{site.data.keyword.cloud_notm}} e os comandos da CLI do Cloud Foundry de sua própria instalação no mesmo contexto. Em vez disso, use **`ibmcloud cf [command]`** se desejar usar a CLI do Cloud Foundry para gerenciar recursos do Cloud Foundry no contexto da CLI do {{site.data.keyword.cloud_notm}}. Observe que **`ibmcloud cf api/login/logout/target`** não é permitido e é necessário usar **`ibmcloud api/login/logout/target`** como alternativa.

Desde maio de 2018 comandos da CLI do {{site.data.keyword.cloud_notm}} mudaram de **`bluemix`** e **`bx`** para **`ibmcloud`**. No entanto, ainda é possível usar os comandos da CLI **`bluemix`** e **`bx`** até que eles sejam removidos posteriormente.
{: tip}

A seguir são listados os comandos detalhados suportados pela CLI do {{site.data.keyword.cloud_notm}}, incluindo seus nomes, argumentos, opções, pré-requisitos, descrições e exemplos.

Os pré-requisitos listam quais ações são necessárias antes de usar o comando e podem incluir uma ou mais das ações a seguir:

<dl>
<dt>Docker</dt>
<dd>Instale a CLI do Docker.</dd>
<dt>Nó de Extremidade</dt>
<dd>Use o comando **`ibmcloud api`** para configurar um terminal de API.</dd>
<dt>Efetuar login</dt>
<dd>Use o comando **`ibmcloud login`** para efetuar login. Se você estiver efetuando login com um ID federado, use a opção **`--sso`** para se autenticar com uma senha única ou use a opção **`--apikey`** para se autenticar com uma chave de API.</dd>
<dt>Destino</dt>
<dd>Use o comando **`ibmcloud target`** para configurar uma organização e um espaço.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Exibe a ajuda geral para comandos integrados de primeiro nível e namespaces suportados da CLI do {{site.data.keyword.cloud_notm}} ou a ajuda para um comando ou um namespace integrado específico.

```
Ibmcloud help [ COMMAND | NAMESPACE ]
```

### Pré-requisito
{: #help-prereqs}

Nenhum.

### Opções de comandos
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>O comando ou namespace para o qual a ajuda é exibida. Se não especificado, a ajuda geral para a CLI do {{site.data.keyword.cloud_notm}} será mostrada. Opcional.</dd>
</dl>

### Exemplos
{: #help-examples}

Exiba a ajuda geral para a CLI do {{site.data.keyword.cloud_notm}}:
```
ibmcloud help
```
{: codeblock}

Exiba a ajuda para o comando **`dev`**:
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

Configure ou visualize o terminal da API do {{site.data.keyword.cloud_notm}}.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

### Pré-requisito
{: #api-prereqs}

Nenhum.

### Opções de comandos
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>O terminal de API que é direcionado, por exemplo, `https://cloud.ibm.com`. Se nem a opção **`API_ENDPOINT`** nem a opção **`--unset`** forem especificadas, o terminal de API atual será exibido. Opcional.</dd>
<dt>--skip-ssl-validation</dt>
<dd>Validação SSL de bypass de solicitações de HTTP. Opcional.</dd>
<dt>--unset</dt>
<dd>Remova a configuração do terminal de API.</dd>
</dl>

### Exemplos
{: #api-examples}

Configure o terminal de API como cloud.ibm.com:
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com--skip-ssl-validation
```
{: codeblock}

Visualize o terminal de API atual:
```
ibmcloud api
```
{: codeblock}

Remova o terminal de API:
```
Ibmcloud api -- unset
```
{: codeblock}

## Ibmcloud config
{: #ibmcloud_config}

Grava valores padrão no arquivo de configuração.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### Pré-requisito
{: #config-prereqs}

Nenhum.

### Opções de comandos
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>Ative ou desative a verificação de versão da CLI. Os valores válidos são `true` ou `false`.</dd>
<dt>--color</dt>
<dd>Ative ou desative a saída de cor. Essa opção está desativada por padrão. Os valores válidos são `true` ou `false`.</dd>
<dt>--http-timeout</dt>
<dd>O valor de tempo limite para solicitações de HTTP em segundos. O valor padrão é 60 segundos.</dd>
<dt>--locale</dt>
<dd>Configure um código padrão de idioma. Se nenhum valor for especificado, o código de idioma anterior será excluído. </dd>
<dt>--trace</dt>
<dd>Rastreie solicitações de HTTP para o terminal ou arquivo especificado. Os valores válidos são `true` ou `false`.</dd>
</dl>

É possível especificar somente uma das opções de cada vez.
{: tip}

### Exemplos
{: #config-examples}

Configure o tempo limite de solicitação de HTTP como 30 segundos:
```
Ibmcloud config -- http-timeout 30
```
{: codeblock}

Ative a saída de rastreio para solicitações de HTTP:
```
Ibmcloud config -- trace true
```
{: codeblock}

Rastreie solicitações de HTTP para o arquivo `/home/usera/my_trace`:
```
Ibmcloud config -- trace
```
{: codeblock}

Desative a saída de cor:
```
Ibmcloud config -- color false
```
{: codeblock}

Configure o código de idioma como zh_Hans:
```
Ibmcloud config -- locale zh_Hans
```
{: codeblock}

Limpe as configurações do código de idioma:
```
Ibmcloud config -- locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

O comando **`ibmcloud info`** não está mais disponível a partir da versão 0.14 da CLI. Para instalar a versão mais recente da CLI, consulte [Instalando a CLI do {{site.data.keyword.cloud_notm}} independente](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).

## Cf ibmcloud
{: #ibmcloud_cf}

Chame a CLI integrada do Cloud Foundry.
```
Ibmcloud [ -q, -- quiet ] cf COMMAND ...
```

### Pré-requisito
{: #info-prereqs}

Nenhum.

### Opções de comandos
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>Não exiba a mensagem de chamada.</dd>
</dl>

### Exemplos
{: #info-examples}

Liste os apps Cloud Foundry:

```
Ibmcloud cf apps
```

Liste os serviços do Cloud Foundry sem exibir a mensagem `Invoking cf command...`:
```
Ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf install
{: #ibmcloud_cf_install}

Instale uma CLI do Cloud Foundry para a CLI do IBM Cloud
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### Pré-requisito
{: #cfinstall-prereqs}

Nenhum.

### Opções de comandos
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>Especifique a versão da CLI do Cloud Foundry para instalar</dd>
  <dt>--restore</dt>
  <dd>Restaure para a versão pré-empacotada da CLI do Cloud Foundry</dd>
  <dt>-f, --force</dt>
  <dd>Forçar instalação sem confirmação</dd>
</dl>

### Exemplos
{: #cfinstall-examples}

Instale a CLI do Cloud Foundry `6.44.1`:

```
ibmcloud cf install -v 6.44.1
```

Instale a versão mais recente da CLI do Cloud Foundry sem confirmação:

```
ibmcloud cf install -f
```

Recupere para a CLI do Cloud Foundry empacotada padrão:

```
ibmcloud cf install --restore
```

## ibmcloud login
{: #ibmcloud_login}

Efetue login na CLI do {{site.data.keyword.cloud_notm}}.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```
### Pré-requisito
{: #login-prereqs}

Nenhum.

### Opções de comandos
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>O terminal de API, por exemplo, `cloud.ibm.com`. </dd>
<dt>--apikey API_KEY ou @API_KEY_FILE_PATH</dt>
<dd>O conteúdo da chave de API ou o caminho de um arquivo-chave de API indicado pelo símbolo @.</dd>
<dt>-u USER_NAME</dt>
<dd>O nome do usuário. Opcional.</dd>
<dt>-p PASS_WORD</dt>
<dd>A senha do usuário. Opcional.</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>O ID da conta de destino. Essa opção é exclusiva com a opção **`--no account`**.</dd>
<dt>--no-account</dt>
<dd>Login forçado sem a conta. Essa opção não é recomendada e é exclusiva com a opção **`-c`**.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>O nome do grupo de recursos de destino. Opcional.</dd>
<dt>-r REGION</dt>
<dd>O nome da região de destino, por exemplo, us-south ou eu-gb.</dd>
<dt>-- no-region</dt>
<dd>Login forçado sem ter uma região como destino.</dd>
<dt>-o ORG</dt>
<dd>O nome da organização de destino. Essa opção foi descontinuada. Use **`ibmcloud target -o org_name`** no lugar. Opcional.</dd>
<dt>-s SPACE</dt>
<dd>O nome do espaço de destino. Essa opção foi descontinuada. Use **`ibmcloud target -s space_name`** no lugar. Opcional.</dd>
<dt>--no-iam</dt>
<dd>Force a autenticação com o servidor de login em vez do IAM público.</dd>
<dt>--skip-ssl-validation</dt>
<dd>Ignore a validação de SSL de solicitações de HTTP. Essa opção não é recomendada.</dd>
</dl>

### Exemplos
{: #login-examples}

Efetue login interativamente.

```
ibmcloud login
```
{: codeblock}

Efetue login com um nome de usuário e uma senha e configure uma conta de destino, uma organização e um espaço:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Efetue login com uma senha única e configure uma conta de destino, uma organização e um espaço:
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Configure sua organização e seu espaço do Cloud Foundry. É possível executar o comando a seguir para identificar interativamente a organização e o espaço:

```
ibmcloud target --cf
```
{: codeblock}

Ou, se você souber a qual organização e a qual espaço o serviço pertence, será possível usar o comando a seguir:

```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

Use uma chave de API com uma conta associada:

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

Use uma chave de API sem nenhuma conta associada:

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

Se a chave de API tiver uma conta associada, a alternância para outra conta não será suportada.
{: note}

Use uma senha única:

```
ibmcloud login -u UserID --sso
```
{: codeblock}

Em seguida, a CLI fornece um link de URL e solicita a senha:

```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

Abra o link em um navegador para obter uma senha. Insira a senha fornecida no console para efetuar login.

## ibmcloud logout
{: #ibmcloud_logout}

Efetue logout da CLI.

```
ibmcloud logout
```
{: codeblock}

### Pré-requisito
{: #logout-prereqs}

Nenhum.

## ibmcloud regions
{: #ibmcloud_regions}

Visualize as informações para todas as regiões no {{site.data.keyword.cloud_notm}}.

```
ibmcloud regions
```
{: codeblock}

### Pré-requisito
{: #regions-prereqs}

Use o comando **`ibmcloud api`** para configurar um terminal de API.

## ibmcloud target
{: #ibmcloud_target}

Configure ou visualize a conta de destino, a região, a organização ou o espaço.

```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

### Pré-requisito
{: #target-prereqs}

* Use o comando **`ibmcloud api`** para configurar um terminal de API.
* Use o comando **`ibmcloud login`** para efetuar login. Se você estiver efetuando login com um ID federado, use a opção **`--sso`** para se autenticar com uma senha única ou use a opção **`--apikey`** para se autenticar com uma chave de API.

### Opções de comandos
{: #target-options}

<dl>
<dt>-c ACCOUNT_ID</dt>
<dd>O ID da conta de destino. Opcional.</dd>
<dt>-r REGION</dt>
<dd>O nome da região de destino, por exemplo, us-south ou eu-gb. Opcional.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>O nome do grupo de recursos de destino. Opcional.</dd>
<dt>--cf</dt>
<dd>Especifique interativamente a organização e o espaço de destino.</dd>
<dt>--cf-api</dt>
<dd>O terminal de API do Cloud Foundry.</dd>
<dt>-o ORG</dt>
<dd>O nome da organização de destino. Opcional.</dd>
<dt>-s SPACE</dt>
<dd>O nome do espaço de destino. Opcional.</dd>
<dt>-- unset-region</dt>
<dd>Limpe a região de destino.</dd>
<dt>--unset-resource-group</dt>
<dd>Limpe o grupo de recursos de destino.</dd>
<dt>--output FORMAT</dt>
<dd>O formato de saída especificado. O JSON é atualmente o único formato suportado.</dd>
</dl>

Se nenhuma das opções estiver especificada, a conta, a região, a organização e o espaço atuais serão exibidos.
{: note}

### Exemplos
{: #target-examples}

Configure a conta, a organização e o espaço atuais:
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

Alterne para uma nova região:
```
ibmcloud target -r eu-gb
```
{: codeblock}

Visualize a conta, a região, a organização e o espaço atuais:
```
ibmcloud target
```
{: codeblock}

## Atualizar ibmcloud
{: #ibmcloud_update}

Atualize a CLI para a versão mais recente.

```
Atualizar ibmcloud [ -f ]
```
### Pré-requisito
{: #update-prereqs}

### Opções de comandos
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>Force uma atualização sem confirmação. Privilégio de administrador é necessário.</dd>
</dl>

## Comandos gerais de serviço de infraestrutura clássica
{: #classic-service-commands}

Use comandos de infraestrutura clássica na CLI do {{site.data.keyword.cloud_notm}} para configurar e gerenciar serviços de infraestrutura.

Execute o comando **`ibmcloud sl`** para ver a lista de comandos disponíveis:
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Classic infrastructure Block Storage
   cdn             Classic infrastructure Content Delivery Network
   file            Classic infrastructure File Storage
   dns             Classic infrastructure Domain Name System
   globalip        Classic infrastructure Global IP addresses
   hardware        Classic infrastructure hardware servers
   image           Classic infrastructure Compute images
   ipsec           Classic infrastructure IPSEC VPN
   loadbal         Classic infrastructure Load balancers
   security        Classic infrastructure SSH Keys and SSL Certificates
   securitygroup   Classic infrastructure network security groups
   subnet          Classic infrastructure Network subnets
   ticket          Classic infrastructure Manage Tickets
   vlan            Classic infrastructure Network VLANs
   vs              Classic infrastructure Virtual Servers
   order           Classic infrastructure Orders
   user            Classic infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

Para visualizar informações da ajuda sobre um comando, execute o comando a seguir:
```
ibmcloud sl [ command ] -h
```

O comando **`ibmcloud sl init`** não está mais disponível como a versão da CLI `0.14`. Para instalar a versão mais recente da CLI, consulte [Instalando a CLI do {{site.data.keyword.cloud_notm}} independente](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Visualize as informações da ajuda para todos os comandos para operar o ambiente de infraestrutura clássica.
```
ibmcloud sl help
```
{: codeblock}

