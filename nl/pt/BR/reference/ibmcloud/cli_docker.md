---

copyright:

  years: 2018
lastupdated: "2018-11-13"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Usando o {{site.data.keyword.dev_cli_notm}} por meio de um contêiner do Docker

Com o contêiner do Docker do {{site.data.keyword.dev_cli_notm}}, você obtém a CLI do
{{site.data.keyword.Bluemix}}, além das ferramentas a seguir:

* `Git`
* `Helm`
* `kubectl`
* `curl`
* Plug-in do {{site.data.keyword.dev_cli_notm}}
* Plug-in do {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in do {{site.data.keyword.registrylong_notm}}
* Plug-in do {{site.data.keyword.containerlong_notm}}
* Plug-in do `sdk-gen`

## Antes de começar
{: #prereq}

É necessário uma conta do [{{site.data.keyword.Bluemix_notm}}
](https://console.bluemix.net/){: new_window} ![Ícone
de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") e deve-se instalar a versão estável do Docker mais recente antes de executar as etapas a
seguir.

## Etapa 1. Puxe a imagem do Docker do hub do Docker.
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Etapa 2. Inicie o contêiner do Docker.
{: #step2}

Use o comando a seguir para iniciar o contêiner do Docker do {{site.data.keyword.dev_cli_notm}}.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Etapa 3. Efetue login no {{site.data.keyword.Bluemix_notm}} com o IBMid.
{: #step3}

```
ibmcloud login
```
{: codeblock}


Se as suas credenciais forem rejeitadas, talvez você esteja usando um ID federado. Consulte
[Efetuando login com um ID federado](/docs/iam/login_fedid.html#federated_id) para obter mais detalhes.
{: tip}

O plug-in da CLI do {{site.data.keyword.dev_cli_notm}} usa dois contêineres para facilitar a construção e o teste do aplicativo. O primeiro é o contêiner de ferramentas, que contém os utilitários necessários para construir e testar seu aplicativo. O `Dockerfile` para esse contêiner é definido pelo parâmetro [`dockerfile-tools`](/docs/cli/idt/commands.html#command-parameters). Você pode pensar nele como um contêiner de desenvolvimento, pois ele contém as ferramentas que são normalmente usadas para o desenvolvimento de um tempo de execução específico.

O segundo contêiner é o contêiner de execução, que imita de perto o ambiente de tempo de execução real do aplicativo, uma vez que ele é implementado para a nuvem. Esse contêiner está em um formato que é adequado para ser implementado para o uso no {{site.data.keyword.Bluemix_notm}}, por exemplo. Como resultado, um ponto de entrada que inicia seu aplicativo é definido. Ao selecionar a execução do aplicativo por meio do plug-in da CLI do {{site.data.keyword.dev_cli_notm}}, ele usa esse contêiner. O `Dockerfile` para esse contêiner é definido pelo parâmetro
[`dockerfile-run`](/docs/cli/idt/commands.html#run-parameters).

Agora você está pronto para usar o {{site.data.keyword.dev_cli_notm}} para gerenciar os recursos do
{{site.data.keyword.Bluemix_notm}} e desenvolver e implementar os aplicativos.
