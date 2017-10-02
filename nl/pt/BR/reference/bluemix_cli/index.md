---



copyright:

  years: 2015, 2017
lastupdated: "2017-07-12"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Introdução ao {{site.data.keyword.Bluemix_notm}} CLI
{: #getting-started}

A CLI do {{site.data.keyword.Bluemix_notm}} fornece uma maneira unificada para você interagir com seus aplicativos, contêineres, infraestruturas e outros serviços usando uma interface da linha de comandos. 

**Restrição**: o {{site.data.keyword.Bluemix_notm}} CLI não é suportado por Cygwin, portanto, não use o {{site.data.keyword.Bluemix_notm}} CLI na janela de linha de comandos do Cygwin.

**Nota**: caso sua rede contenha um servidor proxy HTTP entre o host que executa a CLI e o {{site.data.keyword.Bluemix_notm}}, deve-se especificar o nome do host ou o endereço IP do servidor proxy na variável de ambiente HTTP_PROXY.

**Nota:** a ferramenta CLI do {{site.data.keyword.Bluemix_notm}} empacotou uma interface da linha de comandos do Cloud Foundry em sua instalação. No entanto, não é permitido combinar o uso de comandos da CLI do {{site.data.keyword.Bluemix_notm}} `bx xxx` e comandos da CLI do Cloud Foundry `cf xxx` se você tem sua própria instalação cf cli. Em vez disso, use `bluemix cf` se desejar usar cf cli para gerenciar recursos do Cloud Foundry. No backend, ela executa comandos da CLI do Cloud Foundry empacotada em um contexto compartilhado com a CLI do {{site.data.keyword.Bluemix_notm}}.  Além disso, `bluemix cf api/login/logout/target` não é permitido, use `bluemix api/login/logout/target`.

## Instalando o {{site.data.keyword.Bluemix_notm}} CLI
{: #install_bluemix_cli}

<!-- Online installation Currently Production Only! Please don't forget to replace the domain name-->

### Instalação online

Com acesso a uma conexão de Internet, copie e cole o comando a seguir em um console de terminal e execute-o.

**macOS
**
```
sh <(curl -fsSL https://clis.ng.bluemix.net/install/osx)
```

**Linux**
```
sh <(curl -fsSL https://clis.ng.bluemix.net/install/linux)
```

**Windows PowerShell**

Copie e cole o comando a seguir em um console de terminal do [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell) e execute-o.
```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```

### Instalação offline

<!-- End of online installation -->

Para Mac OS e Windows, faça download do
[pacote de CLI do {{site.data.keyword.Bluemix_notm}}](/docs/cli/index.html#downloads) e execute o instalador.

Para o Linux, siga estas etapas:

  1. Faça download do pacote e extraia-o. Por
exemplo:

  ```
  ~$ tar -xvf Bluemix_CLI.tar.gz
  Bluemix_CLI/
  Bluemix_CLI/update_global_config
  Bluemix_CLI/install_bluemix_cli
  Bluemix_CLI/bx/
  Bluemix_CLI/bx/bash_autocomplete
  Bluemix_CLI/bx/zsh_autocomplete
  Bluemix_CLI/bin/
  Bluemix_CLI/bin/bluemix
  ~$
  ```

  2. Acesse o diretório `Bluemix_CLI` e execute o comando `./install_bluemix_cli` com permissão raiz. É possível executar o comando como um usuário raiz ou usar o comando `sudo` para obter a permissão raiz. Por
exemplo:

  ```
  ~# cd Bluemix_CLI
  ~/Bluemix_CLI# sudo ./install_bluemix_cli
  Superuser privileges are required to run this script.
  The Cloud Foundry CLI version 6.15 is already installed.
  Copying files...
  The Bluemix CLI installed successfully. To get started, open a new Linux terminal and enter "bluemix help", or enter "bx help" as short name.
  ~/Bluemix_CLI#
  ```

Agora é possível começar a usar o {{site.data.keyword.Bluemix_notm}} CLI ou instalar plug-ins adicionais.

## Primeiras etapas com a CLI do {{site.data.keyword.Bluemix_notm}}

Para configurar a ferramenta da CLI do {{site.data.keyword.Bluemix_notm}}, será necessário especificar a API a ser usada.  Isso dependerá da região com a qual você trabalhará; para obter uma lista, use:

```
 ~ $ bluemix regions
Listing Bluemix regions...

Name       Geolocation      Customer   Deployment   Domain               CF API Endpoint                  Type
eu-de      Germany          IBM        Production   eu-de.bluemix.net    https://api.eu-de.bluemix.net    public
au-syd     Sydney           IBM        Production   au-syd.bluemix.net   https://api.au-syd.bluemix.net   public
us-south   US South         IBM        Production   ng.bluemix.net       https://api.ng.bluemix.net       public
eu-gb      United Kingdom   IBM        Production   eu-gb.bluemix.net    https://api.eu-gb.bluemix.net    public
```

Para a região que você deseja acessar, pegue o `CF API Endpoint` e use-o para especificar o terminal de API, como a seguir:

```
~ $ bluemix api https://api.eu-gb.bluemix.net
Setting api endpoint to https://api.eu-gb.bluemix.net...
OK

API endpoint: https://api.eu-gb.bluemix.net (CF API version: 2.75.0)
Login não efetuado. Use 'bx login' to log in.
```

Em seguida, siga o prompt para efetuar login:

```
 ~ $ bluemix login
API endpoint: https://api.eu-gb.bluemix.net

Email> user@example.com

Password>
Authenticating...
OK

```

Será possível especificar a organização e o espaço a serem usados com os comutadores `-o` e `-s`, caso contrário, o comando de login solicitará que você escolha quando houver mais de um.

A CLI do {{site.data.keyword.Bluemix_notm}} agora está configurada e pronta para o uso.

## Instalando um plug-in
{: #install_plug-in}

A CLI do {{site.data.keyword.Bluemix_notm}} suporta uma estrutura de extensão de plug-in para integrar outros comandos além daqueles integrados.


É possível instalar um plug-in do repositório, localmente ou por meio de um servidor remoto. O {{site.data.keyword.Bluemix_notm}} possui repositórios que hospedam os plug-ins do {{site.data.keyword.Bluemix_notm}} CLI e os plug-ins do Cloud Foundry CLI:

   * [Repositório de plug-in da CLI do {{site.data.keyword.Bluemix_notm}}](http://clis.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg), que hospeda plug-ins da CLI do {{site.data.keyword.Bluemix_notm}}.

Para instalar por meio do repositório, execute as etapas a seguir:

  1. Localize o plug-in no repositório. Depois de ter instalado o {{site.data.keyword.Bluemix_notm}} CLI, o repositório oficial `Bluemix` é incluído por padrão. É possível listar os plug-ins no repositório do `Bluemix` usando o comando `bluemix plugin repo-plugins`. Por
exemplo:

  ```
  ~$ bluemix plugin repo-plugins -r Bluemix
  Getting plug-ins from repository 'Bluemix'...

  Repository: Bluemix
  Name           Description                                    Versions
  auto-scaling   Bluemix CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            Bluemix Network Security Group plugin          0.1.1

  ~$
  ```

  2. Instale o plug-in do repositório `Bluemix` usando o comando `bluemix plugin install`. Por
exemplo:

  ```
  ~$ bluemix plugin install auto-scaling -r Bluemix
  Looking up 'auto-scaling' from repository 'Bluemix'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```


Para instalar um plug-in por meio de seu ambiente local, execute as etapas a seguir:

  1. Faça download do plug-in. Por
exemplo:

  ```
  ~$ wget http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64.0.2.2--2016-02-18 14:02:12-- http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64.0.2.2
  Resolving public.dhe.ibm.com... 9.17.248.112
  Connection to public.dhe.ibm.com|9.17.248.112|:80... connected.
  HTTP request sent, awaiting response... 200 OK
  Length: 9857792 (9.4M) [text/plain]
  Saving to: 'auto-scaling-darwin-amd64-0.2.2'

  auto-scaling-darwin-0.2.2 100%[===================>] 9.40M 518KB/s in 22s

  2016-02-18 14:02:34 (443 KB/s) - `auto-scaling-darwin-amd64-0.2.2' saved [9857792/9857792]
  ```

  2. Para sistemas equivalentes ao UNIX, deve-se tornar o arquivo transferido por download executável usando o comando `chmod`. Por
exemplo:

  ```
  ~$ sudo chmod 755 auto-scaling-darwin-amd64-0.2.2
  Password:
  ~$
  ```

  3. Instale o plug-in usando o comando `bluemix plugin install`. Por
exemplo:

  ```
  ~$ bluemix plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing pluign './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```

Para instalar por meio de um servidor remoto, execute as etapas a seguir:

  1. Instale o plug-in por meio de uma URL remota diretamente usando o comando `bluemix plugin install`. Por
exemplo:

  ```
  ~$ bluemix plugin install http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```


Agora você está pronto para usar as linhas de comandos do {{site.data.keyword.Bluemix_notm}}. Execute `bluemix help` para ver a lista de comandos e descrições. 

## Entre em contato

Use as opções a seguir para localizar informações sobre a liberação, fornecer feedback e fazer perguntas:
 * Para obter detalhes sobre as liberações mais recentes e para relatar problemas: [SDK da CLI do {{site.data.keyword.Bluemix_notm}}](https://github.com/IBM-Bluemix/bluemix-cli-sdk){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg)
 * Para fazer perguntas e compartilhar conhecimento com a comunidade: [Canal Slack bluemix-cli](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg)
