---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# Comandos gerais da CLI (ibmcloud)
{: #ibmcloud_cli}

A interface de linha de comandos (CLI) do {{site.data.keyword.cloud_notm}} fornece um conjunto de comandos que são agrupados por namespace para que os usuários interajam com o {{site.data.keyword.cloud_notm}}.

O cliente da linha de comando do {{site.data.keyword.cloud_notm}} empacota um cliente da linha de comando do Cloud Foundry em sua instalação. Se você tiver o seu próprio cf cli instalado, não use os comandos da CLI do {{site.data.keyword.cloud_notm}} `ibmcloud [command]` e os comandos da CLI do Cloud Foundry `cf [command]` de sua própria instalação no mesmo contexto. Em vez disso, use `ibmcloud cf [command]` se desejar usar cf cli para gerenciar recursos do Cloud Foundry no contexto do {{site.data.keyword.cloud_notm}} CLI. Observe que `ibmcloud cf api/login/logout/target` não é permitido e é necessário usar `ibmcloud api/login/logout/target` como alternativa.

Desde maio de 2018 comandos da CLI do {{site.data.keyword.cloud_notm}} mudaram de `bluemix` e `bx` para `ibmcloud`. No entanto, ainda é possível usar os comandos da CLI `bluemix` e `bx` até que eles sejam removidos posteriormente.
{: tip}

A seguir são listados os comandos detalhados que são suportados pelo {{site.data.keyword.cloud_notm}} CLI, incluindo seus nomes, argumentos, opções, pré-requisitos, descrições e exemplos.
{: shortdesc}

Os *Pré-requisitos* listam quais ações são necessárias antes de usar o comando. Os comandos que não têm ações de pré-requisito listam **Nenhum**. Caso contrário, os pré-requisitos podem incluir uma ou mais das ações a seguir:

<dl>
<dt>Nó de Extremidade</dt>
<dd>Um terminal de API deve ser configurado por meio de <code>ibmcloud api</code> antes de usar o comando.</dd>
<dt>Login</dt>
<dd>O login usando o comando <code>ibmcloud login</code> é necessário antes de usar esse comando.
Se estiver efetuando login com o ID federado, use a opção '--sso' para se autenticar com uma senha única ou use '--apikey' para se autenticar com a chave API.
</dd>
<dt>Destino</dt>
<dd>O comando <code>ibmcloud target</code> deve ser usado para configurar uma organização e um espaço antes de usar esse comando.</dd>
<dt>Docker</dt>
<dd>A CLI do Docker (docker) deve estar instalada para executar esse comando.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Exiba a ajuda geral para comandos integrados de primeiro nível e namespaces suportados da CLI {{site.data.keyword.cloud_notm}} ou a ajuda para um comando ou namespace integrado específico.

```
Ibmcloud help [ COMMAND | NAMESPACE ]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE (opcional)</dt>
   <dd>O comando ou namespace para o qual a ajuda é exibida. Se não especificado, a ajuda geral para a CLI do {{site.data.keyword.Bluemix_notm}} será mostrada.</dd>
   </dl>

<strong>Exemplos</strong>:

Exiba a ajuda geral para a CLI do {{site.data.keyword.cloud_notm}}:
```
ibmcloud help
```
{: codeblock}

Exiba a ajuda para o comando `info`:
```
Informações de ajuda ibmcloud
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

Configure ou visualize o terminal da API do {{site.data.keyword.cloud_notm}}.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
   <dl>
   <dt>API_ENDPOINT (opcional)</dt>
   <dd>O terminal de API que é direcionado, por exemplo, `https://cloud.ibm.com`. Se as opções *API_ENDPOINT* e `--unset` não forem especificadas, o terminal de API atual será exibido.</dd>
   <dt>--unset (opcional)</dt>
   <dd>Remova a configuração do terminal de API.</dd>
   <dt>--skip-ssl-validation (opcional)</dt>
   <dd>Validação SSL de bypass de solicitações de HTTP.</dd>
   </dl>
<strong>Exemplos</strong>:

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

Desconfigure o terminal de API:
```
Ibmcloud api -- unset
```
{: codeblock}

## Ibmcloud config
{: #ibmcloud_config}

Grave os valores padrão no arquivo de configuração.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>O valor de tempo limite para solicitações de HTTP. O valor padrão é 60 segundos.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>Rastreie solicitações de HTTP para o terminal ou arquivo especificado.</dd>
   <dt>--color true|false</dt>
   <dd>Ative ou desative a saída de cor. A saída de cor é ativada por padrão.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Configure um código padrão de idioma. Se LOCALE for <i>CLEAR</i>, o código de idioma anterior será excluído.</dd>
   <dt>--check-version true|false</dt>
   <dd>Ative ou desative a verificação de versão da CLI.</dd>
   </dl>

Somente uma dessas opções pode ser especificada por vez.

<strong>Exemplos</strong>:

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

Rastreie solicitações de HTTP para um arquivo especificado */home/usera/my_trace*:
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

O comando `ibmcloud info` não está mais disponível como a versão da CLI `0.14`. Para instalar a versão mais recente da CLI, consulte [Instalando a CLI do {{site.data.keyword.cloud_notm}} independente](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## Cf ibmcloud
{: #ibmcloud_cf}

Chamar o CF CLI integrado
```
Ibmcloud [ -q, -- quiet ] cf COMMAND ...
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>Desativar a mensagem "Chamando comando cf..."</dd>
</dl>

<strong>Exemplos</strong>:

Liste apps cf:

```
Ibmcloud cf apps
```

Listar serviços cf sem a mensagem "Chamando comando cf...":
```
Ibmcloud -q cf services
```
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

Efetue login do usuário.
```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```

<strong>Pré-requisitos</strong>: Nenhum

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Opções de comando</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (opcional)</dt>
  <dd> Terminal de API (por exemplo: cloud.ibm.com)</dd>
  <dt> --apikey <i>API_KEY ou @API_KEY_FILE_PATH</i>
  <dd> Conteúdo da chave de API ou o caminho de um arquivo-chave de API que é indicado por @</dd>
  <dt> --sso (opcional) </dt>
  <dd> Use uma senha descartável para efetuar login </dd>
  <dt> -u <i>USERNAME</i> (opcional)</dt>
  <dd> Nome do usuário</dd>
  <dt> -p <i>PASSWORD</i> (opcional)</dt>
  <dd> Senha</dd>
  <dt> -c <i>ACCOUNT_ID</i> (opcional) </dt>
  <dd> ID da conta de destino. Essa opção é exclusiva com -- no-account</dd>
  <dt> --no-account (opcional) </dt>
  <dd> Forçar login sem conta. Essa opção não é recomendada. Essa opção é exclusiva com -c.</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (opcional) </dt>
  <dd> Nome do grupo de recursos de destino</dd>
  <dt> -r REGION</dt>
  <dd> Nome da região, como 'us-south' ou 'eu-gb'</dt>
  <dt> -- no-region</dt>
  <dd> Force o login sem destinar uma região.</dd>
  <dt> -o <i>ORG</i> (opcional)</dt>
  <dd> Nome da organização de destino (descontinuado, use 'ibmcloud target -o ORG')</dd>
  <dt> -s <i>SPACE</i> (opcional) </dt>
  <dd> Nome do espaço de destino (descontinuado, use 'ibmcloud target -s SPACE')</dd>
  <dt> --no-iam </dt>
  <dd> Forçar a autenticação com o servidor de login em vez do IAM público</dd>
  <dt> --skip-ssl-validation (opcional) </dt>
  <dd> Validação SSL de bypass de solicitações de HTTP. Essa opção não é recomendada.</dd>
</dl>

<strong>Exemplos</strong>:

### Login interativo

```
ibmcloud login
```
{: codeblock}

Efetue login com o nome do usuário e senha e configure a conta de destino, a organização e o espaço:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Efetue login com uma senha descartável e configure a conta de destino, a organização e o espaço
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

### A chave de API tem a conta que está associada

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### A chave de API não tem nenhuma conta que está associada

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> se a Chave de API tiver uma conta associada, a alternância para outra conta não será permitida.

### Usar uma senha única
```
ibmcloud login -u UserID --sso
```
{: codeblock}

Em seguida, a CLI fornece um link de URL e solicita uma senha:
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

Abra o link no navegador, para obter uma senha. Digite a senha fornecida no console e será possível efetuar login.

## ibmcloud logout
{: #ibmcloud_logout}

Efetue logout do usuário.
```
ibmcloud logout
```
{: codeblock}

<strong>Pré-requisitos</strong>: Nenhum

## ibmcloud regions
{: #ibmcloud_regions}

Visualize as informações para todas as regiões no {{site.data.keyword.Bluemix_notm}}.
```
ibmcloud regions
```
{: codeblock}

<strong>Pré-requisitos</strong>: Terminal

## ibmcloud target
{: #ibmcloud_target}


Configure ou visualize a conta de destino, a região, a organização ou o espaço.
```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i> (opcional)</dt>
   <dd>Nome da região a ser alternada, como 'us-south' ou 'eu-gb'.</dd>
   <dt>-- unset-region</dt>
   <dd>Desconfigurar região destinada</dd>
   <dt>-c <i>ACCOUNT_ID</i> (opcional)</dt>
   <dd>O ID da conta que será o destino.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (opcional)</dt>
   <dd>Nome do grupo de recursos</dd>
   <dt>--cf</dt>
   <dd>Selecione de forma interativa o espaço e a organização de destino</dd>
   <dt>-o <i>ORG_NAME</i> (opcional)</dt>
   <dd>O nome da organização que será o destino.</dd>
   <dt>-s <i>SPACE_NAME</i> (opcional)</dt>
   <dd>O nome do espaço que será o destino.</dd>
   </dl>
Se nenhuma das opções estiver especificada, a conta, a região, a organização e o espaço atuais serão exibidos.

<strong>Exemplos</strong>:

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

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
<dl>
  <dt>-f</dt>
  <dd>Forçar atualização sem confirmação. Privilégio de administrador é necessário.</dd>
</dl>


## Comandos gerais de serviço de infraestrutura clássica
{: #softlayer_cli}

Use os comandos de infraestrutura clássica na interface da linha de comandos (CLI) do {{site.data.keyword.cloud_notm}} para configurar e gerenciar os serviços de infraestrutura.

Execute o comando `ibmcloud sl` para ver a lista de comandos disponíveis:
```
USAGE:
   bx sl command [arguments...] [ opções ...]

COMMANDS:
   block           Gen1 infrastructure Block Storage
   cdn             Gen1 infrastructure Content Delivery Network
   file            Gen1 infrastructure File Storage
   dns             Gen1 infrastructure Domain Name System
   globalip        Gen1 infrastructure Global IP addresses
   hardware        Gen1 infrastructure hardware servers
   image           Gen1 infrastructure Compute images
   ipsec           Gen1 infrastructure IPSEC VPN
   loadbal         Gen1 infrastructure Load balancers
   security        Gen1 infrastructure SSH Keys and SSL Certificates
   securitygroup   Gen1 infrastructure network security groups
   subnet          Gen1 infrastructure Network subnets
   ticket          Gen1 infrastructure Manage Tickets
   vlan            Gen1 infrastructure Network VLANs
   vs              Gen1 infrastructure Virtual Servers
   order           Gen1 infrastructure Orders
   user            Gen1 infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

Para visualizar informações da ajuda sobre um comando, execute:
```
ibmcloud sl [ command ] -h
```

O comando `ibmcloud sl init` não está mais disponível como a versão da CLI `0.14`. Para instalar a versão mais recente da CLI, consulte [Instalando a CLI do {{site.data.keyword.cloud_notm}} independente](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Visualize as informações da ajuda para todos os comandos para operar o ambiente de infraestrutura clássica.
```
ibmcloud sl help
```
{: codeblock}

