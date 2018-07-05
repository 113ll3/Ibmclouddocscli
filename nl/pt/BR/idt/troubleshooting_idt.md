---
copyright:
  years: 2017, 2018
lastupdated: "2018-06-21"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# Resolução de problemas do IBM Cloud Developer Tools
{: #ts}

Alguns problemas conhecidos com a {{site.data.keyword.dev_cli_notm}} são documentados, junto a suas soluções alternativas.
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## Problemas Conhecidos
{: #knownissues}

As seções a seguir descrevem os problemas conhecidos e as possíveis resoluções.


### O nome do host é considerado um erro quando você cria um projeto com um padrão não móvel
{: #hostname}

Será possível ver o erro a seguir se você usar a {{site.data.keyword.dev_cli_short}} para criar um projeto por meio dos padrões Web App, BFF ou Microservice:

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### Causa
{: #hostname-cause}

Esse erro deve-se a um token de login expirado.


#### Resolução
{: #hostname-resolution}

Efetue login novamente.

```
ibmcloud login
```
{: codeblock}


### Falhas gerais com a {{site.data.keyword.dev_cli_short}}
{: #general}

Será possível ver o erro a seguir se você usar os comandos create, delete, list ou code da {{site.data.keyword.dev_cli_short}}:

```
Failed to <command> project.
```
{: codeblock}


#### Causa
{: #general-cause}

Esse erro deve-se a um token de login expirado.


#### Resolução
{: #general-resolution}

Efetue login novamente.

```
ibmcloud login
```
{: codeblock}


### Erro: não há essa imagem ao executar um novo projeto
{: #nosuchimage}

O erro a seguir pode ser exibido ao executar um projeto sem construí-lo primeiro.

```
$ ibmcloud dev run testProject
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


#### Causa
{: #nosuchimage-cause}

Deve-se construir um projeto antes de executá-lo.


#### Resolução
{: #nosuchimage-resolution}

Execute o comando a seguir no diretório de projeto atual para construir seu aplicativo:

```
ibmcloud dev build
```
{: codeblock}

Execute o comando a seguir no diretório de projeto atual para iniciar seu aplicativo:

```
ibmcloud dev run
```


### Erro do broker de serviço ao incluir o recurso {{site.data.keyword.objectstorageshort}}
{: #os}

Será possível ver o erro a seguir se você usar a {{site.data.keyword.dev_cli_short}} para criar dois projetos com o recurso {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### Causa
{: #os-cause}

Esse erro acontece devido ao serviço {{site.data.keyword.objectstorageshort}}, que fornece somente uma instância do plano grátis do {{site.data.keyword.objectstorageshort}}.


#### Resolução
{: #os-resolution}

É solicitado que você escolha um plano diferente para evitar esse erro.


### Falha ao obter o código durante a criação do projeto
{: #code}

Será possível ver o erro a seguir se você usar a {{site.data.keyword.dev_cli_short}} para criar um projeto:

```
FAILED                            
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}


#### Causa
{: #code-cause}

Esse erro deve-se a um tempo limite interno.


#### Resolução
{: #code-resolution}

É possível obter o código de uma das maneiras a seguir:

* Execute o comando a seguir usando a CLI:

   ```
   ibmcloud dev code <your-project-name>
   ```
   {: codeblock}

   Substitua `<your-project-name>` com o nome do projeto especificado durante a criação do projeto.

* Use o {{site.data.keyword.dev_console}}.

	1. Selecione seu [projeto ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://console.{DomainName}/developer/projects) no {{site.data.keyword.dev_console}} e clique em **Obter o código**.

	2. Clique em **Gerar código**.

	3. Depois que o código for gerado, clique em **Fazer download do código**.


### Erro ao executar `ibmcloud dev run` para projetos Node.js
{: #node}

Será possível ver o erro a seguir se você estiver executando `ibmcloud dev run` com o {{site.data.keyword.dev_cli_short}} para projetos Node.js Web ou BFF:

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


#### Causa
{: #node-cause}

Esse erro ocorre quando o módulo `appmetrics` é instalado em uma arquitetura diferente. Módulos npm nativos que estão instalados em uma arquitetura não funcionam em outra. As imagens incluídas do Docker baseiam-se no kernel Linux.


#### Resolução
{: #node-resolution}

Exclua a pasta `node_modules` e execute `ibmcloud dev run` novamente.


### Falha ao implementar no {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploy}

É possível tentar implementar o {{site.data.keyword.Bluemix_notm}} com o {{site.data.keyword.dev_cli_short}} e ver que ele não é implementado no {{site.data.keyword.Bluemix_notm}}, mas não há erro.


#### Causa
{: #cause1}

Talvez você não esteja com login efetuado em sua conta.

#### Resolução
{: #resolution1}

Efetue login e tente novamente.

```
ibmcloud login
```


### Falha ao implementar o Kubernetes no {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploytokube}

Você pode ver essa falha após o prompt inicial para o seu nome do cluster:

```
FAILED
Falha ao executar a ação:  status de saída 1:

FAILED
Falha ao configurar a implementação com o cluster '<cluster-name>' devido a: status de saída 1
```


#### Causa
{: #cause2}

Muito provavelmente, isso ocorreu devido a um nome do cluster inválido e pode ser confirmado executando o mesmo comando com
`--trace`. Talvez você veja isto na saída de erro:

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### Resolução
{: #resolution2}

Certifique-se de que você esteja usando o cluster correto e que tenha configurado seu cluster para implementação, executando

```
ibmcloud cs cluster-config <cluster-name>
```


### Falha ao implementar o Kubernetes no {{site.data.keyword.Bluemix_notm}}

Você pode ver essa falha após o prompt para o destino da imagem de implementação:

```
FAILED
Falha ao executar a ação:  status de saída 1:denied: o acesso solicitado ao recurso foi negado


FAILED
Falha ao enviar por push a imagem de execução identificada como 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' para o registro do Docker devido a: status de saída 1
```


#### Causa
{: #cause3}

Muito provavelmente, isso é devido a um destino de imagem de implementação inválido. Mais especificamente, pode ser um namespace inválido, o valor médio no destino de imagem de implementação


#### Resolução
{: #resolution3}

Certifique-se de que o namespace no destino da imagem de implementação corresponda a um dos namespaces que é localizado em
execução

```
Ibmcloud cr namespaces
```



## APÊNDICE
{: #appendix}

Todos os pré-requisitos são instalados para a maioria dos usuários que estão usando os instaladores de plataforma. Caso você precise instalar manualmente quaisquer componentes, aqui estão as instruções:

Para instalar o plug-in dev, a [CLI do IBM Cloud](../reference/bluemix_cli/get_started.md#getting-started)
deve ser instalada primeiro.

Para usar o próprio plug-in dev, deve-se instalá-lo executando o comando a seguir: `ibmcloud plugin install dev -r
Bluemix`

Para executar e depurar aplicativos localmente, também deve-se instalar o [Docker ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://www.docker.com/get-docker).

Para implementar um aplicativo como um contêiner, deve-se também instalar o `Kubernetes`,
o `Helm` e os seguintes plug-ins da CLI do IBM Cloud:

Para instalar o Kubernetes:
* Usuários do Mac: `curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Usuários do Linux: `curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Usuários do Windows: `curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

Para instalar o Helm:
* Usuários do Mac e do Linux: `export DESIRED_VERSION=v2.6.0` `curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Usuários do Windows: faça download e instale o binário em https://github.com/kubernetes/helm/releases/tag/v2.6.0

Para instalar o plug-in de container-registry: `ibmcloud plugin install
container-registry`

Para instalar o plug-in de container-service: `ibmcloud plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## Obtendo ajuda e suporte
{: #gettinghelp}

Se você tiver problemas ou dúvidas sobre o {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.dev_console}} ou o {{site.data.keyword.dev_cli_notm}}, procure informações ou faça perguntas em um fórum para obter ajuda. Também é possível abrir um chamado de suporte.

Quando você posta nos fóruns, é possível identificar suas perguntas, para que as equipes de desenvolvimento do {{site.data.keyword.Bluemix_notm}} sejam notificadas.

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

Se tiver questões técnicas sobre como desenvolver ou implementar um app com o {{site.data.keyword.dev_console}} ou a {{site.data.keyword.dev_cli_notm}}:

* Poste sua pergunta no [Stack Overflow ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix) e marque-a com `bluemix-dev-services` e `ibm-bluemix`.
* Poste sua pergunta no [Slack ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://ibm-cloud-tech.slack.com/) no canal `bluemix-dev-services`. [Inscreva-se ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://ibm.biz/IBMCloudNativeSlack) hoje.


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

Consulte [Obtendo ajuda![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/support/index.html#getting-help) para obter mais detalhes sobre o uso dos fóruns.

Para obter informações sobre como abrir um chamado de suporte da {{site.data.keyword.IBM}} ou sobre os níveis de suporte e as severidades dos chamados, veja [Entrando em contato com o suporte ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/support/index.html#contacting-support).

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
