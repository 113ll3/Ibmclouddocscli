---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos gerais da CLI (ibmcloud sl)
{: #softlayer_cli}

O plug-in do {{site.data.keyword.BluSoftlayer}} foi mesclado na CLI do {{site.data.keyword.Bluemix_notm}}. Não é mais necessário instalar o plug-in.
{: tip}

Use os comandos de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}} na interface da linha de comandos (CLI) do {{site.data.keyword.Bluemix_notm}} para configurar e gerenciar os serviços do SoftLayer.

Desde maio de 2018 comandos da CLI do {{site.data.keyword.Bluemix_notm}} mudaram de `bluemix` e `bx` para `ibmcloud`. No entanto, ainda é possível usar os comandos da CLI `bluemix` e `bx` até que sejam removidos em uma data posterior.
{: tip}

Para iniciar, instale o {{site.data.keyword.Bluemix_notm}} CLI. Veja
[IBM Cloud CLI ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window} para obter detalhes.

Para obter uma lista completa de comandos da CLI do {{site.data.keyword.Bluemix_notm}}, consulte:
Comandos do [{{site.data.keyword.Bluemix_notm}}
(ibmcloud)](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli).

Os comandos a seguir são compatíveis. Use o comando `ibmcloud sl` para ver a lista de comandos disponíveis:

<table summary="Comandos gerais ordenados alfabeticamente que possuem links que levam a mais informações sobre o comando">
<caption>Tabela 1. Comandos gerais de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
   </tbody>
 </table>
 
 Para visualizar informações da ajuda para os comandos, execute: `ibmcloud sl [command] -h`
 
 ## Ibmcloud sl init
{: #sl_init}

Inicializar as definições de configuração que são usadas para se conectar ao ambiente de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}. A configuração inclui o nome do usuário, a chave API ou a senha, a conta e o terminal.
```
Ibmcloud sl init [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL do terminal de API da infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}, o padrão é: https://api.softlayer.com/rest/v3.1 para autenticação da chave API, https://api.softlayer.com/mobile/v3.1 para autenticação do IBMid.</dd>
<dt>-u, --sl-user</dt>
<dd>Nome do usuário da infraestrutura de Gen1.</dd>
<dt>-p, --sl-password</dt>
<dd>Senha ou chave API.</dd>
<dt>-c, --account-id</dt>
<dd>ID da conta.</dd>
<dt>-q, --security-question-id</dt>
<dd>ID da pergunta de segurança usado para autenticar; pergunte ao proprietário da conta se você não souber.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Resposta à pergunta de segurança usada para autenticação; pergunte ao proprietário da conta se você não souber.</dd>
<dt>-s, --security-code</dt>
<dd>Código de segurança gerado pelo fornecedor de segurança quando a autenticação de 2 fatores está ativada.</dd>
<dt>-v, --security-vendor</dt>
<dd>Fornecedor de segurança que fornece o código de segurança para autenticação, as opções são: VERISIGN, TOTP, PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Token de autenticação quando a autenticação de telefone está ativada.</dd>
</dl>

Por exemplo, login com nome do usuário e senha/chave API da infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}
```
$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:
1. Login with {{site.data.keyword.BluSoftlayer_notm}} infrastructure user name and password/API key
2. Use {{site.data.keyword.Bluemix_notm}} Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Nome do usuário: []> user@example.com
Chave API ou senha: []> abcd

Terminal da API:    https://api.softlayer.com/rest/v3.1
Nome do usuário:       user@example.com
Chave API:         xxxxxxxxxx
```
Por exemplo, use a conexão única do {{site.data.keyword.Bluemix_notm}} para efetuar login no Softlayer
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account example user's Account (65ce8074c6c62b5)

API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south User:           user@example.com Account:        example user's Account (65ce8074c6c62b5)
No org or space targeted, use 'ibmcloud target --cf or ibmcloud target -o ORG -s SPACE'


$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:

1. Login with Softlayer user name and password/API key
2. Use IBM Cloud Single-Sign-On
Enter a number> 2
{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint URL: [https://api.softlayer.com/mobile/v3.1]>
Setting account to: 123456
OK

{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint:    https://api.softlayer.com/mobile/v3.1

Account ID:                123456
User ID:                   user@example.com
IMS token:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

Visualizar informações da ajuda para todos os comandos para operar o ambiente de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}.
```
ibmcloud sl help
```
