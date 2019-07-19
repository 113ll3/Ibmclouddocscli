---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-01"

keywords: IBM Cloud Developer Tools CLI, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Introdução à CLI do {{site.data.keyword.cloud_notm}}
{: #ibmcloud-cli}

Neste tutorial, você instala um conjunto de ferramentas do Desenvolvedor do {{site.data.keyword.cloud}}, verifica a instalação e configura o ambiente. As ferramentas do Desenvolvedor do {{site.data.keyword.cloud_notm}} oferecem uma abordagem de linha de comandos para criar, desenvolver e implementar aplicativos da web, de dispositivo móvel e de microsserviço.
{: shortdesc}

Com essa instalação, você obterá a CLI do {{site.data.keyword.cloud_notm}} independente, mais as seguintes ferramentas:

* `Homebrew` (somente Mac)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* Plug-in do {{site.data.keyword.dev_cli_notm}}
* Plug-in do {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in do {{site.data.keyword.registrylong_notm}}
* Plug-in do {{site.data.keyword.containerlong_notm}}
* Plug-in do `sdk-gen`

## Antes de começar
{: #idt-prereq}

É necessária uma conta do [{{site.data.keyword.cloud_notm}} ](https://cloud.ibm.com/){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") e os requisitos do sistema a seguir:

* Se você estiver executando o Windows, algumas funções não serão suportadas, a menos que você esteja executando o Windows 10 Pro.
* Deve-se usar o canal estável para o Docker com uma versão mínima de 1.13.1.

## Etapa 1. Execute o comando de instalação
{: #step1-install-idt}

* Para Mac e Linux, execute o comando a seguir:
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Para o Windows 10 Pro, execute o comando a seguir como um administrador:
  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Clique com o botão direito no ícone do Windows PowerShell e selecione **Executar como
administrador**.
  {: tip}

  Também é possível fazer download do script do instalador por meio desse [repositório do GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo").

<!--Uncomment when this linked topic goes to prod.
  For the steps to install these tools manually, see [Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in components manually](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).
-->

## Etapa 2. Verificar a instalação
{: #step2-verify-idt}

Para verificar se a CLI e as ferramentas do Desenvolvedor foram instaladas com êxito, execute o comando `help`:
```
ibmcloud dev help
```
{: codeblock}

A saída lista as instruções de uso, a versão atual e os comandos suportados.

## Etapa 3. Configure seu ambiente
{: #step3-configure-idt-env}

1. Efetue login no {{site.data.keyword.cloud_notm}} com seu IBMid. Se você tiver múltiplas contas, deverá selecionar qual conta usar. Se você não especificar uma região com a sinalização `-r`, deverá também escolher uma região.
  ```
  ibmcloud login
  ```
  {: codeblock}
  
  Se as suas credenciais forem rejeitadas, talvez você esteja usando um ID federado. Para efetuar login com uma identidade federada, use a sinalização `--sso`. Consulte
[Efetuando login com um ID federado](/docs/iam/federated_id?topic=iam-federated_id#federated_id) para obter mais detalhes.
  {: tip}

2. Para usar os serviços do Cloud Foundry, destine uma organização e um espaço.
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  Opcionalmente, é possível usar a saída do comando anterior para configurar manualmente a organização e o espaço
com o comando a seguir:
  ```
  ibmcloud target -o <value> -s <value>
  ```
  {: codeblock}

## Próximas Etapas
{: #next-steps}

Agora você está pronto para desenvolver e implementar o seu primeiro aplicativo! Para obter mais informações, consulte [Criando e implementando aplicativos usando a CLI](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli).
