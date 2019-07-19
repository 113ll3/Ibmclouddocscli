---

copyright:
  years: 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Instalando os componentes do plug-in da CLI de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}} manualmente
{: #install-devtools-manually}

Se você preferir controle mais granular para instalar componentes de ferramentas do desenvolvedor, poderá instalá-los manualmente usando as etapas a seguir. Caso contrário, todos os pré-requisitos serão instalados automaticamente para a maioria dos usuários usando os [instaladores de plataforma](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt).
{: shortdesc}

## Antes de começar
{: cli-before-you-begin}

* Instale a CLI do [{{site.data.keyword.cloud}} independente](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) para que seja possível suportar a instalação de plug-ins de linha de comandos para o `ibmcloud`.
* Instale o comando [curl](https://curl.haxx.se/download.html){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") para fazer download de pacotes por meio da linha de comandos.

## Etapa 1. Instalando o plug-in da CLI de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}}
{: #install-devtools-idt}

É possível usar os comandos da CLI de ferramentas do desenvolvedor (ibmcloud dev) {{site.data.keyword.cloud_notm}} para criar um aplicativo, gerenciar, implementar, depurar e testá-lo.

Instale o plug-in `dev` executando o comando a seguir: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Etapa 2. Instalando o Docker
{: #install-devtools-docker}

Para executar e depurar apps localmente, instale o [Docker](https://www.docker.com/get-docker){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo").

## Etapa 3. Instalando o Kubernetes:
{: #idt-install-kube}

O Kubernetes é um mecanismo de orquestração de contêiner de software livre para automatizar a implementação, o ajuste de escala e o gerenciamento de aplicativos containerizados.

Para suportar implementações conteinerizadas, instale o Kubernetes para a sua plataforma:

* MacOS:
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

## Etapa 4. Instalando plug-ins da CLI do Kubernetes
{: #idt-install-kubernetes-cli-plugins}

Para gerenciar implementações do Kubernetes por meio da linha de comandos, instale os plug-ins de contêiner a seguir:

* Instale o plug-in  ` container-registry ` :
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

* Instale o plug-in  ` container-service ` :
  ```
  Ibmcloud plugin install container-service
  ```
  {: codeblock}

Para obter mais informações, consulte [Configurando a CLI e a API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Etapa 5. Instalando o Helm:
{: #idt-install-helm}

Instale o [Helm](https://helm.sh/docs/){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo"), que é um gerenciador de pacote baseado em Kubernetes.

* Usuários do MacOS e Linux&trade;, executem os comandos a seguir:
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Os usuários do Windows&trade; podem fazer download e instalar o [binário](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} do Helm![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo").

## Etapa 6. Instalando o plug-in da CLI do  {{site.data.keyword.openwhisk_short}}
{: #idt-install-functions}

É possível usar o plug-in da CLI do {{site.data.keyword.openwhisk}} para gerenciar os seus fragmentos de código em ações, criar acionadores e regras para ativar as suas ações para responder a eventos e empacotar ações em pacotes.

Para instalar o plug-in da CLI do {{site.data.keyword.openwhisk_short}}, execute o
comando a seguir:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Para obter mais informações, consulte [Configurando o plug-in da CLI do {{site.data.keyword.openwhisk_short}}](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli).

## Etapa 7. Instalando o plug-in da CLI do SDK Generator
{: #idt-install-sdk-gen}

Como um desenvolvedor no {{site.data.keyword.cloud_notm}}, é possível usar esse plug-in para gerar os SDKs de sua definição de API de REST compatível com a [Especificação da Open API ](https://www.openapis.org/){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo"). À medida que você faz mudanças na definição de API de REST, é possível usar esse plug-in para gerar novamente apenas o SDK, em vez de gerar novamente o projeto inteiro.

Instale o plug-in da CLI do SDK Generator:
```
Ibmcloud plugin install sdk-gen
```
{: codeblock}

Para obter mais informações, consulte  [ Gerador de SDK ](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli).
