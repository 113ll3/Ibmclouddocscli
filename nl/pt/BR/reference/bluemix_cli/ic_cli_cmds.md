---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos gerais da CLI (ibmcloud)
{: #ibmcloud_cli}

Versão: 0.7.1

A interface de linha de comandos (CLI) do {{site.data.keyword.Bluemix_notm}} fornece um conjunto de comandos que são agrupados por namespace para que os usuários interajam com o {{site.data.keyword.Bluemix_notm}}.

A partir da versão 0.5.0, o cliente da linha de comandos do {{site.data.keyword.Bluemix_notm}} empacota um cliente da linha de comandos Cloud Foundry em sua instalação. Se você tiver seu próprio cf cli instalado, não use os comandos do {{site.data.keyword.Bluemix_notm}} CLI `ibmcloud [command]` e do Cloud Foundry CLI `cf [command]` de sua própria instalação no mesmo contexto. Em vez disso, use `ibmcloud cf [command]` se desejar usar cf cli para gerenciar recursos do Cloud Foundry no contexto do {{site.data.keyword.Bluemix_notm}} CLI.  Observe que `ibmcloud cf api/login/logout/target` não é permitido e deve-se usar `ibmcloud api/login/logout/target` no lugar.

Desde maio de 2018 comandos da CLI do {{site.data.keyword.Bluemix_notm}} mudaram de `bluemix` e `bx` para `ibmcloud`. No entanto, ainda é possível usar os comandos da CLI `bluemix` e `bx` até que sejam removidos em uma data posterior.
{: tip}

A seguir são listados os comandos detalhados que são suportados pelo {{site.data.keyword.Bluemix_notm}} CLI, incluindo seus nomes, argumentos, opções, pré-requisitos, descrições e exemplos.
{:shortdesc}

**Nota:** *Pré-requisitos* listam quais ações são necessárias antes de usar o comando. Os comandos que não têm ações de pré-requisito listam **Nenhum**. Caso contrário, os pré-requisitos podem incluir uma ou mais das ações a seguir:

<dl>
<dt>Nó de Extremidade</dt>
<dd>Um terminal de API deve ser configurado por meio de <code>bluemix api</code> antes de usar o comando.</dd>
<dt>Login</dt>
<dd>É necessário efetuar login usando o comando <code>bluemix login</code> antes de usar esse comando.
Se estiver efetuando login com o ID federado, use a opção '--sso' para se autenticar com uma senha única ou use '--apikey' para se autenticar com a chave API. Acesse o console do {{site.data.keyword.Bluemix_notm}} **Gerenciar** &gt; **Segurança** &gt; **Chaves API da plataforma** para criar chaves API.
</dd>
<dt>Destino</dt>
<dd>O comando <code>bluemix target</code> deve ser usado para configurar uma organização e um espaço antes de usar esse comando.</dd>
<dt>Docker</dt>
<dd>A CLI do Docker (docker) deve estar instalada para executar esse comando.</dd>
</dl>


Use os índices na tabela a seguir para se referir aos comandos ibmcloud usados frequentemente.

## Comandos ibmcloud gerais
{: #ibmcloud_commands_index}

<table summary="General ibmcloud commands.">
<caption>Tabela 1. Comandos gerais ibmcloud</caption>
 <thead>
 <th colspan="5">Comandos ibmcloud gerais</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help](ic_cli_cmds.html#ibmcloud_help)</td>
 <td>[ibmcloud api](ic_cli_cmds.html#ibmcloud_api)</td>
 <td>[ibmcloud config](ic_cli_cmds.html#ibmcloud_config)</td>
 <td>[ibmcloud info](ic_cli_cmds.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](ic_cli_cmds.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](ic_cli_cmds.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](ic_cli_cmds.html#ibmcloud_logout) </td>
 <td>[ibmcloud regiões](ic_cli_cmds.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](ic_cli_cmds.html#ibmcloud_target)</td>
 <td>[ibmcloud update](ic_cli_cmds.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>
 
 ## ibmcloud help
{: #ibmcloud_help}
Exiba a ajuda geral para comandos integrados de primeiro nível e namespaces suportados da CLI {{site.data.keyword.Bluemix_notm}} ou a ajuda para um comando ou namespace integrado específico.

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

Exiba a ajuda geral para a CLI do {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud help
```

Exiba a ajuda para o comando `info`:

```
Informações de ajuda ibmcloud
```

## ibmcloud api
{: #ibmcloud_api}
Configure ou visualize o terminal da API do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
   <dl>
   <dt>API_ENDPOINT (opcional)</dt>
   <dd>O terminal da API que é o destino, por exemplo, `https://api.chinabluemix.net`. Se as opções *API_ENDPOINT* e `--unset` não forem ambas especificadas, o terminal de API atual será exibido.</dd>
   <dt>--unset (opcional)</dt>
   <dd>Remova a configuração do terminal de API.</dd>
   <dt>--skip-ssl-validation (opcional)</dt>
   <dd>Validação SSL de bypass de solicitações de HTTP.</dd>
   </dl>
<strong>Exemplos</strong>:

Configure o terminal da API para api.chinabluemix.net:

```
Ibmcloud api api.chinabluemix.net
```

```
Api https://api.chinabluemix.net--skip-ssl-validation
```

Visualize o terminal de API atual:

```
ibmcloud api
```

Desconfigure o terminal de API:

```
Ibmcloud api -- unset
```

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

Ative a saída de rastreio para solicitações de HTTP:

```
Ibmcloud config -- trace true
```

Rastreie solicitações de HTTP para um arquivo especificado */home/usera/my_trace*:

```
Ibmcloud config -- trace
```

Desative a saída de cor:

```
Ibmcloud config -- color false
```

Configure o código de idioma como zh_Hans:

```
Ibmcloud config -- locale zh_Hans
```

Limpe as configurações do código de idioma:

```
Ibmcloud config -- locale CLEAR
```

## ibmcloud info
{: #ibmcloud_info}

Visualize as informações básicas do {{site.data.keyword.Bluemix_notm}}, incluindo a região atual, a versão do controlador de nuvem e alguns terminais úteis, como terminais para login e a troca de token de acesso.

```
ibmcloud info
```

<strong>Pré-requisitos</strong>: Terminal

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

## ibmcloud login
{: #ibmcloud_login}

Efetue login do usuário.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>Pré-requisitos</strong>: Nenhum

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Opções de comando</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (opcional)</dt>
  <dd> Terminal de API (Por exemplo: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY ou @API_KEY_FILE_PATH</i>
  <dd> Conteúdo da chave API ou o caminho de um arquivo de chave API indicado por @</dd>
  <dt> --sso (opcional) </dt>
  <dd> Use uma senha única para efetuar login </dd>
  <dt> -u <i>USERNAME</i> (opcional)</dt>
  <dd> Nome do usuário</dd>
  <dt> -p <i>PASSWORD</i> (opcional)</dt>
  <dd> Senha</dd>
  <dt> -c <i>ACCOUNT_ID</i> (opcional) </dt>
  <dd> ID da conta de destino</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (opcional) </dt>
  <dd> Nome do grupo de recursos de destino</dd>
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

#### Login interativo

```
ibmcloud login
```

Efetuar login com nome de usuário e senha e configurar a conta de destino, a organização e o espaço:

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Efetuar login com uma senha única e configurar a conta de destino, a organização e o espaço

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Efetuar login com a chave API e configurar os destinos:

#### A chave API tem conta associada

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### A chave API não tem conta associada

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> se a chave API tiver uma conta associada, não será permitido alternar para outra conta.

#### Usar uma senha única

```
ibmcloud login -u UserID --sso
```

Em seguida, a CLI fornecerá um link de URL e solicitará a senha:
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

Abra o link no navegador, que fornecerá instrução para obter a senha. Digite a senha especificada no console e você poderá efetuar login.

## ibmcloud logout
{: #ibmcloud_logout}

Efetue logout do usuário.

```
ibmcloud logout
```

<strong>Pré-requisitos</strong>: Nenhum

## ibmcloud regions
{: #ibmcloud_regions}

Visualize as informações para todas as regiões no {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```

<strong>Pré-requisitos</strong>: Terminal

## ibmcloud target
{: #ibmcloud_target}


Configure ou visualize a conta de destino, região, organização ou espaço.

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i> (opcional)</dt>
   <dd>Nome da região a ser alternada, como 'us-south' ou 'eu-gb'.</dd>
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
Se nenhuma das opções for especificada, a conta, a região, a organização e o espaço atuais serão exibidos.

<strong>Exemplos</strong>:

Configure a conta atual, a organização e o espaço:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

Alterne para uma nova região:

```
ibmcloud target -r eu-gb
```

Visualize a conta, a região, a organização e o espaço atuais:

```
ibmcloud target
```

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
