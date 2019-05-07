---

copyright:
  years: 2019
lastupdated: "2019-04-29"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Instalando o plug-in da CLI do {{site.data.keyword.cloud_notm}} developer tools manualmente
{: #install-devtools-manually}

É possível instalar manualmente o plug-in da interface da linha de comandos (CLI) das ferramentas do desenvolvedor do {{site.data.keyword.cloud}} se você preferir um controle mais granular para instalar os componentes. Caso contrário, todos os pré-requisitos serão instalados automaticamente para a maioria dos usuários usando os [instaladores de plataforma](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt).
{: shortdesc}

## Antes de começar
{: cli-before-you-begin}

* Instale a [CLI do {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) independente para obter suporte para instalar plug-ins da linha de comandos para o {{site.data.keyword.cloud_notm}}.
* Instale o comando [curl](https://curl.haxx.se/download.html){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") para fazer download de pacotes por meio da linha de comandos.

## Instalando o plug-in da CLI do {{site.data.keyword.cloud_notm}} developer tools
{: #install-devtools-idt}

É possível usar os comandos da CLI do {{site.data.keyword.cloud_notm}} developer tools para criar um aplicativo, gerenciar, implementar, depurar e testá-lo.

Para instalar o plug-in do {{site.data.keyword.cloud_notm}} developer tools, execute o comando a seguir: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Instalando o Docker
{: #install-devtools-docker}

Para executar e depurar apps localmente, instale o [Docker](https://www.docker.com/get-started){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo").

## Instalando a ferramenta de linha de comandos do Kubernetes
{: #idt-install-kube}

Para visualizar uma versão local do painel do Kubernetes e para implementar apps em seus clusters, instale a [ferramenta de linha de comandos do Kubernetes](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") para a sua plataforma:

* Mac:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
  ```
  {: codeblock}

* &trade; Linux:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
  ```
  {: codeblock}

* &trade; Windows:
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
  ```
  {: codeblock}

O prefixo para executar comandos usando a ferramenta de linha de comandos do Kubernetes é `kubectl`. Para obter mais informações, consulte [Configurando a CLI e a API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Instalando o plug-in da CLI do {{site.data.keyword.registrylong_notm}}
{: #idt-install-container-registry-cli-plugin}

É possível usar o plug-in da CLI `container-registry` para configurar seu próprio namespace de imagem em um registro privado hospedado e gerenciado pela IBM. Onde é possível armazenar e compartilhar imagens do Docker com todos os usuários em sua conta do {{site.data.keyword.cloud_notm}}.

* Para instalar o plug-in do {{site.data.keyword.registrylong}}, execute o comando a seguir:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

Para obter mais informações, consulte a [referência de comando do {{site.data.keyword.registrylong}}](/docs/services/Registry?topic=registry-registry_cli_reference).

## Instalando o plug-in da CLI do {{site.data.keyword.containerlong_notm}}
{: #idt-install-kubernetes-cli-plugin}

Para criar e gerenciar clusters do Kubernetes no {{site.data.keyword.containerlong}}:

* Para instalar o plug-in do {{site.data.keyword.registryshort_notm}}, execute o comando a seguir:
  ```
  Ibmcloud plugin install container-service
  ```
  {: codeblock}

Para obter mais informações, consulte a [referência de comando do {{site.data.keyword.registryshort_notm}}](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference).

## Instalando o Helm
{: #idt-install-helm}

Instale o [Helm](https://helm.sh/docs/){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo"), que é um gerenciador de pacote baseado em Kubernetes.

* Usuários do Mac e Linux &trade;, executem os comandos a seguir:
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Os usuários do Windows&trade; podem fazer download e instalar o [binário](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} do Helm ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo").

## Instalando o plug-in da CLI do {{site.data.keyword.openwhisk_short}}
{: #idt-install-functions}

É possível usar o plug-in da CLI do {{site.data.keyword.openwhisk}} para gerenciar seus fragmentos de código em ações, empacotar ações em pacotes e criar acionadores e regras para ativar suas ações para responder a eventos.

Para instalar o plug-in da CLI do {{site.data.keyword.openwhisk_short}}, execute o
comando a seguir:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Para obter mais informações, consulte [Configurando o plug-in da CLI do {{site.data.keyword.openwhisk_short}}](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli).

## Instalando o plug-in da CLI do SDK Generator
{: #idt-install-sdk-gen}

Como um desenvolvedor do {{site.data.keyword.cloud_notm}}, é possível usar o plug-in para gerar SDKs em sua definição de API de REST compatível com [Open API Specification](https://www.openapis.org/){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo"). Conforme a definição da API de REST evolui, é possível usar o plug-in para gerar novamente somente o SDK, em vez de gerar novamente o projeto inteiro.

Para instalar o plug-in da CLI do SDK Generator, execute o comando a seguir:
```
Ibmcloud plugin install sdk-gen
```
{: codeblock}

Para obter mais informações, consulte  [ Gerador de SDK ](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli).
