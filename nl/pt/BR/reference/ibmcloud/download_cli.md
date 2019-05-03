---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, plugin, plug-in, command line, command-line, windows powershell, linux, macos, installer

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Instalando a CLI  {{site.data.keyword.cloud_notm}}  Independente
{: #install-ibmcloud-cli}

A CLI do {{site.data.keyword.cloud}} fornece a interface da linha de comandos para gerenciar recursos no {{site.data.keyword.cloud_notm}}. Ainda é possível usar a CLI `cf` para efetuar login no {{site.data.keyword.cloud_notm}}, mas ela funciona com um serviço do Cloud Foundry no {{site.data.keyword.cloud_notm}}. 

Se você desejar instalar a CLI do {{site.data.keyword.cloud}} e outros plug-ins e ferramentas recomendados para desenvolver aplicativos para o {{site.data.keyword.cloud_notm}}, consulte [Introdução à CLI do {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

Use as etapas a seguir para instalar a CLI do {{site.data.keyword.cloud_notm}} independente:

1. Selecione o instalador de seu S.O. para download.

   Mac OS X de 64 bits:
[instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} /
[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows de 64 bits:
[instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} /
[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 de 64 bits:
[instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window}
/ [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 bits (ppc64le): [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   Para versões de 32 bits e anteriores, acesse a página [ Liberações de CLI do {{site.data.keyword.cloud_notm}}](/docs/cli/reference/ibmcloud?topic=cloud-cli-cli-releases#cli-releases) para fazer download.

2. Execute o instalador
   * Para MacOS e Windows&trade;, execute o instalador.
   * Para Linux&trade;, extraia o pacote e execute o script `install`

3. Direcione um terminal de API e efetue login no {{site.data.keyword.cloud_notm}}:
   ```
   ibmcloud login
   ```
   {: codeblock}
   
Agora, você está pronto para gerenciar os recursos do  {{site.data.keyword.cloud_notm}} . Digite `ibmcloud help` para ver as descrições dos comandos.

Se você estiver usando um ID federado, siga as instruções [aqui](/docs/iam?topic=iam-federated_id#federated_id) para efetuar login com uma senha descartável ou uma chave de API.  
{: tip}

Além dos instaladores, é possível ter outras opções para instalar a CLI do {{site.data.keyword.cloud_notm}}:

* Instalar por meio do shell
* Fazer download do pacote binário e instalar em um diretório customizado

## Instalar por meio do shell
{: #shell_install}

### macOS
{: #shell-install-macos}

Copie e cole o comando a seguir em um terminal de seu Mac OS e execute-o:
```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
{: codeblock}

### Linux
{: #shell-install-linux}

Copie e cole o comando a seguir em um terminal de seu S.O. Linux&trade; e execute-o:
```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
{: codeblock}

### Windows PowerShell
{: #shell-install-windows}

Copie e cole o comando a seguir em um console de terminal do [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") e execute-o:
```
iex (New-Object Net.WebClient). DownloadString ('https://clis.cloud.ibm.com/install/powershell')
```
{: codeblock}

## Instalar em um diretório customizado
{: #install-custom-dir}

Ao usar os instaladores ou um shell script para instalar a CLI do {{site.data.keyword.Bluemix_notm}}, os binários vão para os diretórios do sistema. Se você desejar especificar um diretório diferente, use as etapas a seguir.

### Etapa 1: faça download do pacote binário com base em seu OS usando os links a seguir.
{: #step1-custom-dir}

| Plataforma | Downloads | Soma de verificação |
|---------|----------|---------|
| macOS | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum) |

### Etapa 2: extraia o pacote em um diretório que você especificar.
{: #step2-custom-dir}

   Após a extração do pacote, será possível ver o conteúdo a seguir:

   Para Linux &trade; e macOS:

   ```
   IBM_Cloud_CLI
   UNK -- LICENSE
   UNK -- NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   UNK -- cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: codeblock}

   Para Windows

   ```
   IBM_Cloud_CLI
   UNK -- LICENSE
   UNK -- NOTICE
   UNK -- cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

### Etapa 3: incluir na variável de ambiente `PATH` e ative a conclusão automática do shell.
{: #step3-custom-dir}

   * Inclua o `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` na variável de ambiente `PATH`.
   * Para suporte de conclusão automática de shell (somente MacOS e Linux&trade;), consulte [este guia](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Desinstalando a CLI do  {{site.data.keyword.cloud_notm}}  Independente
{: #uninstall-ibmcloud-cli}

As seções a seguir fornecem detalhes sobre como desinstalar a CLI independente do {{site.data.keyword.cloud_notm}} em plataformas específicas.

### Desinstalando no Windows
{: #uninstall-cli-windows}

1. Clique no botão `Iniciar` e, em seguida, selecione `Painel de Controle`.
2. Na janela pop-up, clique em `Desinstalar um programa`.
3. Na lista de aplicativos pop-up, localize `IBM Cloud Command Line Interface`.
4. Clique com o botão direito em `IBM Cloud Command Line Interface` e selecione `Desinstalar`.
5. O desinstalador é iniciado. Siga as instruções para concluir a desinstalação.

### Desinstalando no Linux e no MacOS
{: #uninstall-cli-linux-macos}

#### Versões anteriores a  ` 0.9.0 `

1. Abra um terminal e execute os comandos a seguir:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`

2. Limpe os scripts de conclusão automática, se os configurou. Para obter mais detalhes, consulte [Ativando a conclusão automática do shell para a CLI do {{site.data.keyword.cloud_notm}} (apenas Linux e macOS)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

#### Versão `0.9.0` e mais recente

1. Abra um terminal e execute o comando a seguir:
  * `/usr/local/ibmcloud/bin/uninstall`
2. Limpe qualquer script de conclusão automática customizada. Para obter mais detalhes, consulte [Ativando a conclusão automática do shell para a CLI do {{site.data.keyword.cloud_notm}} (apenas Linux e macOS)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Outros links para explorar ainda mais a CLI do {{site.data.keyword.cloud_notm}}
{: #other-cli-links}

* [Estenda a CLI do {{site.data.keyword.cloud_notm}} com plug-ins](/docs/cli/reference/ibmcloud?topic=cloud-cli-plug-ins#plug-ins)
* [Comandos gerais da CLI (ibmcloud)](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_cli)

## Relatar problemas e enviar feedback
{: #issues}

Use as opções a seguir para relatar problemas ou enviar novas solicitações de recursos:
* Crie problemas no [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo").
* Deixe mensagens no [{{site.data.keyword.cloud_notm}} Slack de Tech - #canal de ferramentas do desenvolvedor](https://ibm-cloud-tech.slack.com){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo") - Solicitar acesso da equipe [aqui](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo").
