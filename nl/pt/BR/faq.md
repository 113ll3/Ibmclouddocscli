---

copyright:
  years: 2019
lastupdated: "2019-06-10"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# FAQ
{: #ibm-cli-faq}

## É necessário usar a versão mais recente da CLI do {{site.data.keyword.cloud_notm}}?
{: #cli-latest-version}

Sim, deve-se usar a versão mais recente. É possível verificar qual versão você está usando
ao executar o comando a seguir:

```
ibmcloud -v
```
{: codeblock}

## Como atualizar a CLI
{: #cli-update-version}

Execute o comando a seguir para atualizar para a versão mais recente da CLI:

```
Atualizar ibmcloud
```
{: codeblock}

## Como ser notificado sobre novas liberações da CLI?
{: #cli-get-notified}

Sim, você fica atualizado sobre novas liberações da CLI à medida que elas se tornam disponíveis. Assine o [repositório de liberações da CLI do {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")

## Qual é a estrutura de arquivo para os aplicativos {{site.data.keyword.cloud_notm}}?
{: #cli-file-structure}

Os aplicativos que são criados ou ativados por meio da CLI vêm com configurações pré-configuradas encapsuladas no arquivo `cli-config.yml`. O `cli-config.yml` contém entradas padrão que são usadas pelos comandos da CLI que podem ser substituídos por valores que são transmitidos por meio da linha de comandos.

Os apps que são implementados em uma cadeia de ferramentas do DevOps também podem conter arquivos como `toolchain.yml` e `pipeline.yml`. Os apps que estão sendo implementados manualmente podem conter arquivos `manifest.yml` e arquivos de gráfico do Helm (para implementação no Cloud Foundry ou no Kubernetes, por exemplo).

## Como os contêineres locais são usados?
{: #cli-faq-containers}

O plug-in da CLI do {{site.data.keyword.dev_cli_long}} usa dois contêineres para facilitar a construção e o teste de seu app. O primeiro é o contêiner de ferramentas, que contém os utilitários necessários para construir e testar seu app. O `Dockerfile` para esse contêiner é definido pelo parâmetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Você pode pensar nele como um contêiner de desenvolvimento, pois ele contém as ferramentas que são normalmente usadas para o desenvolvimento de um tempo de execução específico.

O segundo contêiner é o contêiner de execução, que imita estreitamente o ambiente de tempo de execução real de seu app depois que ele é implementado na nuvem. Esse contêiner está em um formato que é adequado para ser implementado para o uso no {{site.data.keyword.cloud_notm}}, por exemplo. Como resultado, é definido um ponto de entrada que inicia seu app. Quando você seleciona para executar seu app por meio da CLI do plug-in da CLI do {{site.data.keyword.dev_cli_long}}, ele usa esse contêiner. O `Dockerfile` para esse contêiner é definido pelo parâmetro
[`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

## Como implementar o código existente?

Para implementar um código base existente, veja [Gerando ativos de
implementação e ativação de nuvem](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

