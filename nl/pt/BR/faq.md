---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Perguntas mais frequentes (FAQ)
{: #ibm-cli-faq}

## Qual é a estrutura de arquivo para os aplicativos {{site.data.keyword.cloud_notm}}?
{: #cli-file-structure}

Os aplicativos que são criados ou ativados por meio da CLI vêm com configurações pré-configuradas encapsuladas no arquivo `cli-config.yml`. O `cli-config.yml` contém entradas padrão que são usadas pelos comandos da CLI que podem ser substituídos por valores que são transmitidos por meio da linha de comandos.

Os aplicativos que foram implementados em um DevOps Toolchain também podem conter arquivos, como `toolchain.yml` e `pipeline.yml`. Os aplicativos que estão sendo implementados manualmente podem conter um `manifest.yml` e arquivos de gráfico do Helm (para implementação no Cloud Foundry ou Kubernetes, por exemplo).

## Como os contêineres locais são usados?
{: #cli-faq-containers}

O plug-in da CLI do {{site.data.keyword.dev_cli_long}} usa dois contêineres para facilitar a construção e o teste de seu aplicativo. O primeiro é o contêiner de ferramentas, que contém os utilitários necessários para construir e testar seu aplicativo. O `Dockerfile` para esse contêiner é definido pelo parâmetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Você pode pensar nele como um contêiner de desenvolvimento, pois ele contém as ferramentas que são normalmente usadas para o desenvolvimento de um tempo de execução específico.

O segundo contêiner é o contêiner de execução, que imita de perto o ambiente de tempo de execução real do aplicativo, uma vez que ele é implementado para a nuvem. Esse contêiner está em um formato que é adequado para ser implementado para o uso no {{site.data.keyword.cloud_notm}}, por exemplo. Como resultado, um ponto de entrada que inicia seu aplicativo é definido. Ao selecionar a execução do aplicativo por meio do plug-in da CLI do {{site.data.keyword.dev_cli_long}}, ele usa esse contêiner. O `Dockerfile` para esse contêiner é definido pelo parâmetro
[`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

# Como implementar o código existente?
Para implementar um código base existente, siga estas etapas para [ativar seu app](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

## Blogs de referência, vídeos e documentação
{: #cli-faq-reference}

### Blogs
{: #cli-blogs}

- [Implementando no {{site.data.keyword.cloud_notm}} Private com o plug-in da CLI do {{site.data.keyword.dev_cli_long}}](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [Implementando no Kubernetes no {{site.data.keyword.cloud_notm}} com o plug-in da CLI do {{site.data.keyword.dev_cli_long}}](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Ativar projetos existentes para o {{site.data.keyword.cloud_notm}} com o plug-in da CLI do {{site.data.keyword.dev_cli_long}}](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### Vídeos
{: #cli-videos}

- [Como implementar no Kubernetes no {{site.data.keyword.cloud_notm}} com o plug-in da CLI do {{site.data.keyword.dev_cli_long}}](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [Como implementar projetos existentes no {{site.data.keyword.cloud_notm}} com o plug-in da CLI do {{site.data.keyword.dev_cli_long}}](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [Criar, depurar e implementar um app Node.js com o plug-in da CLI do {{site.data.keyword.dev_cli_long}} e VSCode](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### Documentação e tutoriais
- [Implementação contínua para o Kubernetes](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [Resolução de problemas para o plug-in da CLI do {{site.data.keyword.dev_cli_long}}](/docs/cli?topic=cloud-cli-troubleshoot)
- [Comandos de plug-in da CLI do {{site.data.keyword.dev_cli_long}} (ibmcloud dev)](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [Depuração de aplicativo local para o plug-in da CLI do {{site.data.keyword.dev_cli_long}}](/docs/cli/idt?topic=cloud-cli-local-debug)

**Para relatar problemas ou fornecer feedback, é possível usar o [{{site.data.keyword.cloud_notm}} Tech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com) - Solicitar acesso de equipe [aqui](https://slack-invite-ibm-cloud-tech.mybluemix.net/).**
