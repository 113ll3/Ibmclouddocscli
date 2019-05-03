---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-21"

keywords: troubleshoot cli, debug app cli, developer tools, ibmcloud cli, ibmcloud help, ibmcloud dev, cli, plugin, debug splug-in, command line, command-line, developer tools

subcollection: cloud-cli

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
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Resolução de problemas para o plug-in da CLI do {{site.data.keyword.cloud_notm}} Developer Tools
{: #troubleshoot}

Os problemas gerais com o uso da interface da linha de comandos (CLI) do {{site.data.keyword.dev_cli_short}} para criação de apps podem incluir falhas de implementação ou código que não pode ser recuperado. Em muitos casos, é possível recuperar-se desses problemas seguindo algumas etapas simples.
{: shortdesc}

## Por que obtenho um erro de nome do host ao criar um app com um padrão não móvel?
{: #ts-cli-hostname-error}
{: troubleshoot}

O erro a seguir poderá ser exibido se você usar a CLI do {{site.data.keyword.dev_cli_short}} para implementar um app para o Cloud Foundry. Se você inserir um nome de host exclusivo, ainda poderá ver essa mensagem.
```
The hostname <myHostname> is taken.
```
{: screen}
{: tsSymptoms}

Esse erro é causado por um token de login expirado.
{: tsCauses}

Efetue login novamente executando o comando a seguir:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Por que obtenho falhas de comando geral?
{: #ts-cli-general-failures}
{: troubleshoot}

O erro a seguir poderá ser exibido se você usar os comandos `create`, `delete`, `list` ou `code`:
```
Failed to <command> application.
```
{: screen}
{: tsSymptoms}

Esse erro é causado por um token de login expirado.
{: tsCauses}

Efetue login novamente executando o comando a seguir:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Por que a imagem para meu novo app não é reconhecida?
{: #ts-cli-nosuchimage}
{: troubleshoot}

Quando você tenta `ibmcloud dev run` um app sem construí-lo primeiro, o erro a seguir pode ser exibido.
```
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image ibmcloud-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: ibmcloud-dev-testProject
```
{: screen}
{: tsSymptoms}

Deve-se construir um app antes de executá-lo. Execute o comando a seguir em seu diretório de aplicativos atual:
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

Execute o comando a seguir no seu diretório de aplicativos atual para iniciar seu app:
```
ibmcloud dev run
```
{: tsResolve}

## Por que eu obtenho um erro de broker de serviço ao incluir o recurso do {{site.data.keyword.objectstorageshort}}?
{: #ts-cli-object-storage}
{: troubleshoot}

O erro a seguir poderá ser exibido se você usar a CLI para criar dois apps com o recurso do {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: screen}
{: tsSymptoms}

Esse erro é devido ao serviço {{site.data.keyword.objectstorageshort}}, que fornece somente uma instância do plano grátis do {{site.data.keyword.objectstorageshort}}.
{: tsCauses}

Selecione um plano diferente.
{: tsResolve}

## Por que meu código não é recuperado quando eu crio um app?
{: #retrieve-code-error}
{: troubleshoot}

O erro a seguir poderá ser exibido ao usar a CLI para criar um app:
```
COM FALHA
Aplicativo criado, mas não foi possível obter código
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
{: tsSymptoms}

Esse erro deve-se a um tempo limite interno.
{: tsCauses}

Use uma das maneiras a seguir para obter o código:

* Execute o seguinte comando:

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Substitua `<your-app-name>` pelo nome do app que você especificou durante a criação do app.

* Use o {{site.data.keyword.dev_console}}.

	1. Selecione seu [app ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/resources) no {{site.data.keyword.dev_console}}.

	2. Clique em **Fazer download do código**.
{: tsResolve}

## Por que não posso executar o comando `ibmcloud dev run` para apps Node.js?
{: #ts-cli-node}
{: troubleshoot}

O erro a seguir poderá ser exibido se você executar o comando `ibmcloud dev run` para os apps Node.js Web ou BFF:

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
{: screen}
{: tsSymptoms}

Esse erro ocorre quando o módulo `appmetrics` é instalado em uma arquitetura diferente. Módulos npm nativos que estão instalados em uma arquitetura não funcionam em outra. As imagens incluídas do Docker baseiam-se no kernel Linux.
{: tsCauses}

Exclua a pasta `node_modules` e execute o comando `ibmcloud dev run` novamente.
{: tsResolve}

## Por que não posso implementar no {{site.data.keyword.cloud_notm}}?
{: #ts-cli-deploy-issues}
{: troubleshoot}

Ocorre uma falha ao tentar implementar no {{site.data.keyword.cloud_notm}}, mas nenhum erro é exibido.
{: tsSymptoms}

Você pode não estar com login efetuado em sua conta.
{: tsCauses}

Execute o comando a seguir para efetuar login e tente novamente.
```
ibmcloud login
```
{: tsResolve}

## Por que não posso implementar em Kubernetes no {{site.data.keyword.cloud_notm}}?
{: #ts-cli-kube-deploy}
{: troubleshoot}

A falha a seguir pode ser exibida após o nome do cluster ser solicitado:
```
FAILED
Falha ao executar a ação:  status de saída 1:

FAILED
Falha ao configurar a implementação com o cluster '<cluster-name>' devido a: status de saída 1
```
{: screen}
{: tsSymptoms}

Isso é mais provável devido a um nome de cluster que não é válido. É possível confirmar a causa executando o mesmo comando com `--trace` e os detalhes a seguir podem ser incluídos na saída de erro:
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: screen}
{: tsCauses}

Certifique-se de estar usando o cluster correto e que ele esteja configurado para implementação, executando:
```
ibmcloud cs cluster-config <cluster-name>
```
{: codeblock}
{: tsResolve}

## Por que não posso implementar um destino de imagem?
{: #ts-deploy-image-target}
{: troubleshoot}

A falha a seguir pode ser exibida após o destino de imagem de implementação ser solicitado:
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

Isso é mais provável devido a um destino de imagem de implementação que não é válido. Mais especificamente, o namespace, que é o valor médio no destino de imagem de implementação, pode não ser válido.
{: tsCauses}

Certifique-se de que o namespace no destino da imagem de implementação corresponda a um dos namespaces que são exibidos ao executar o comando a seguir:
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## Por que o idioma para o meu app não pode ser determinado?
{: #ts-cli-determine-language}
{: troubleshoot}

A falha a seguir poderá ser exibida ao tentar iniciar seu app:
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application
directly. 
```
{: screen}
{: tsSymptoms}

Esse erro pode ser devido a uma das causas a seguir:
- Executar o comando [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) por meio de um diretório que não é o diretório de origem de seu aplicativo.
- Executar o comando [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) para um app de um idioma que não é reconhecido.
{: tsCauses}

Certifique-se de executar o comando no diretório do app que contém o código-fonte para o app. Se isso não resolver o problema e o idioma for um dos [idiomas suportados](/docs/cli/idt?topic=cloud-cli-idt-cli#enable-language-options), use o parâmetro `--language` para especificar o idioma.
{: tsResolve}

## Por que não posso construir ou executar um app que tenha sido ativado para implementação na nuvem?
{: #ts-cli-cloud-enabled-apps}
{: troubleshoot}

Várias falhas poderão ser encontradas ao tentar [construir](/docs/cli/idt?topic=cloud-cli-idt-cli#build) ou [executar](/docs/cli/idt?topic=cloud-cli-idt-cli#run) um app que tenha sido ativado.
{: tsSymptoms}

As diferentes causas possíveis podem ser localizadas em cada um dos links a seguir.
{: tsCauses}

- Para obter mais informações sobre como resolver esses problemas com um app Spring, consulte [Ativando aplicativos Spring Boot existentes para implementação na nuvem](/docs/java-spring?topic=java-spring-enable_existing#enable_existing).
- Para obter mais informações sobre como resolver esses problemas com um app `Node.js`, consulte [Ativando aplicativos Node.js existentes para implementação na nuvem](/docs/node?topic=nodejs-enable_existing#enable_existing).
{: tsResolve}

<!--
## How to manually install the {{site.data.keyword.dev_cli_notm}} CLI components separately
{: #ts-cli-install-devtools-manually}
{: troubleshoot}

To manually install the {{site.data.keyword.dev_cli_notm}} CLI components separately, you can follow these [steps](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).
-->



