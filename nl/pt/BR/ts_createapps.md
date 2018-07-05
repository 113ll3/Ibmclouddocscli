---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-21"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Resolução de problemas para o {{site.data.keyword.Bluemix_notm}} Developer Tools
{: #troubleshoot}

Os problemas gerais com o uso da CLI do {{site.data.keyword.dev_cli_short}} para criar apps podem incluir falhas de implementação ou código que não pode ser recuperado ao criar um app. Em muitos casos, é possível recuperar-se desses problemas seguindo algumas etapas simples.
{:shortdesc}

## Erro de nome do host quando você cria um app com um padrão não móvel
{: #hostname-error}

Você poderá ver o erro a seguir se usar a CLI do {{site.data.keyword.dev_cli_short}} para implementar um app no Cloud
Foundry. Se você inserir um nome do host que acredita ser exclusivo, você ainda poderá ver essa mensagem.

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

Esse erro é causado por um token de login expirado.
{: tsCauses}

Efetue login novamente.

```
bx login
```
{: codeblock}
{: tsResolve}

## Falhas gerais com a CLI do {{site.data.keyword.dev_cli_short}}
{: #general}

Você poderá ver o erro a seguir se usar os comandos da CLI do {{site.data.keyword.dev_cli_short}} `create`, `delete`, `list` ou `code`:

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

Esse erro é causado por um token de login expirado.
{: tsCauses}

Efetue login novamente.

```
bx login
```
{: codeblock}
{: tsResolve}

## Erro: nenhuma imagem como essa quando você executa um novo app
{: #nosuchimage}

Você pode ver o erro a seguir ao executar um app sem construí-lo primeiro.

```
$ bx dev run
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```
{: tsSymptoms}

Deve-se construir um app antes de executá-lo.
{: tsCauses}

Execute o comando a seguir no seu diretório de aplicativos atual para construir seu app:

```
bx dev build
```
{: codeblock}

Execute o comando a seguir no seu diretório de aplicativos atual para iniciar seu app:

```
bx dev run
```
{: tsResolve}

## Erro do broker de serviço ao incluir o recurso {{site.data.keyword.objectstorageshort}}
{: #os}

Você poderá ver o erro a seguir se usar a CLI do {{site.data.keyword.dev_cli_short}} para criar dois apps com o recurso {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

Esse erro é devido ao serviço {{site.data.keyword.objectstorageshort}}, que fornece somente uma instância do plano grátis do {{site.data.keyword.objectstorageshort}}.
{: tsCauses}

É solicitado que você escolha um plano diferente para evitar esse erro.
{: tsResolve}

## Falha ao obter o código ao criar um app
{: #code}

Você poderá ver o erro a seguir se usar a CLI do {{site.data.keyword.dev_cli_short}} para criar um app:

```
FAILED                            
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

Esse erro deve-se a um tempo limite interno.
{: tsCauses}

É possível obter o código de uma das maneiras a seguir:

* Execute o comando a seguir usando a CLI:

   ```
   bx dev code <your-app-name>
   ```
   {: codeblock}

   Substitua `<your-app-name>` pelo nome do app que você especificou durante a criação do app.

* Use o {{site.data.keyword.dev_console}}.

	1. Selecione seu [app ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://console.bluemix.net/developer/appservice/apps) no {{site.data.keyword.dev_console}}.

	2. Clique em **Fazer download do código**.

{: tsResolve}

## Erro ao executar `bx dev run` para apps Node.js
{: #node}

Você poderá ver o erro a seguir se estiver executando o `bx dev run` com a CLI do {{site.data.keyword.dev_cli_short}} para os apps Node.js Web ou BFF:

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}
{: tsSymptoms}

Esse erro ocorre quando o módulo `appmetrics` é instalado em uma arquitetura diferente. Módulos npm nativos que estão instalados em uma arquitetura não funcionam em outra. As imagens incluídas do Docker baseiam-se no kernel Linux.
{: tsCauses}

Exclua a pasta `node_modules` e execute o comando `bx dev run` novamente.
{: tsResolve}

## Falha ao implementar no {{site.data.keyword.Bluemix_notm}}

A falha ocorre ao tentar implementar o {{site.data.keyword.Bluemix_notm}} com a CLI do
{{site.data.keyword.dev_cli_short}}, mas nenhum erro é exibido.
{: tsSymptoms}

Você pode não estar com login efetuado em sua conta.
{: tsCauses}

Efetue login e tente novamente.

```
bx login
```
{: tsResolve}

## Falha ao implementar o Kubernetes no {{site.data.keyword.Bluemix_notm}}

A falha a seguir pode ser exibida após o nome do cluster ser solicitado:

```
FAILED
Falha ao executar a ação:  status de saída 1:

FAILED
Falha ao configurar a implementação com o cluster '<cluster-name>' devido a: status de saída 1
```
{: tsSymptoms}

Isso é mais provável devido a um nome de cluster que não é válido. É possível confirmar a causa executando o mesmo comando com `--trace` e os detalhes a seguir podem ser incluídos na saída de erro:

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Execute 'bx cs clusters' para listar todos os clusters aos quais você tem acesso.","type":"Provisioning"}
```
{: tsCauses}

Para verificar se o cluster usado está correto e se você o configurou para implementação, execute:

```
bx cs cluster-config <cluster-name>
```
{: tsResolve}

## Falha ao implementar um destino de imagem

A falha a seguir pode ser exibida após o destino de imagem de implementação ser solicitado:

```
FAILED
Falha ao executar a ação:  status de saída 1:denied: o acesso solicitado ao recurso foi negado


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

Isso é mais provável devido a um destino de imagem de implementação que não é válido. Mais especificamente, o namespace, que é o valor médio no destino de imagem de implementação, pode não ser válido.

Verifique se o namespace no destino de imagem de implementação corresponde a um dos namespaces localizados na execução:

```
bx cr namespaces
```
{: tsResolve}

## Reinstalando ferramentas
{: #appendix}

Todos os pré-requisitos instalam para a maioria dos usuários usando os instaladores de plataforma. Caso você precise instalar manualmente quaisquer componentes, aqui estão as instruções:

Para instalar o plug-in dev, deve-se primeiro instalar a [CLI do IBM Cloud](https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started).

Para usar o próprio plug-in dev, deve-se instalá-lo executando o comando a seguir: `bx plugin install dev -r
Bluemix`

Para executar e depurar apps localmente, deve-se também instalar o [Docker](https://www.docker.com/get-docker).

Para implementar um app como um contêiner, deve-se também instalar o Kubernetes, o Helm e os seguintes plug-ins da CLI do IBM
Cloud:

Para instalar o Kubernetes:
* Usuários do Mac: `curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Usuários do Linux: `curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Usuários do Windows: `curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

Para instalar o Helm:
* Usuários do Mac e do Linux: `export DESIRED_VERSION=v2.6.0` `curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Usuários do Windows: faça download e instale o binário em https://github.com/kubernetes/helm/releases/tag/v2.6.0

Para instalar o plug-in container-registry: `bx plugin install container-registry`

Para instalar o plug-in container-registry: `bx plugin install container-service`
