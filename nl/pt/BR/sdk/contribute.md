---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-29"

keywords: cli, contribute plug-in, sdk plug-in, cloud foundry cli, go environment, internationalization, ginkgo, govendor

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Contribuindo com o plug-in do SDK
{: #contribute}

Siga estas diretrizes para contribuir com o plug--in do SDK da CLI do {{site.data.keyword.cloud}}.

## Configurando seu ambiente de desenvolvimento
{: #dev-env}

* CLI do [ do Cloud Foundry](https://github.com/cloudfoundry/cli/releases){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo").

   A CLI do Cloud Foundry não é requerida, mas ela ajuda a acessar {{site.data.keyword.cloud_notm}} em um terminal.

   Para obter mais informações sobre a CLI do Cloud Foundry, consulte a [documentação](/docs/cli?topic=cloud-cli-cf#cf).

* {{site.data.keyword.cloud_notm}} [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Esse plug-in é incluído na CLI do {{site.data.keyword.cloud_notm}} e fornece
recursos úteis para acessar o {{site.data.keyword.cloud_notm}} na linha de comandos.

* [Ambiente de desenvolvimento ](https://golang.org/doc/code.html){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") do Go

   O Go é rigoroso com os locais dos pacotes, portanto, sua origem deve ser definida dentro
da estrutura de diretório `$GOPATH`. Deve-se definir suas variáveis `$GOPATH` e `$GOROOT` e incluir `$GOPATH/bin` em
sua variável de ambiente `$PATH`. É possível editar o arquivo de configuração `~/.bash_profile` (no Mac) para fazer essas mudanças.

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Gerenciador de dependência: [`govendor `](https://github.com/kardianos/govendor){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

   A ferramenta `govendor` cria e gerencia as dependências do Go. Você não precisa dela, a menos que planeje atualizar o diretório do fornecedor.

   * Instale-a usando o comando a seguir.

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * Inicialize o `govendor` em seu diretório de projeto usando o comando a seguir.

      ```
      govendor init
      ```
      {: codeblock}

   * Inclua dependências de `$GOPATH` no diretório do fornecedor usando o comando a seguir.

      ```
      govendor add +local
      ```
      {: codeblock}

* Estrutura de teste BDD: [Ginkgo ](http://onsi.github.io/ginkgo/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

A estrutura de teste é baseada no Ginkgo, uma estrutura de teste BDD para Go e é usada com [`gomega`](http://onsi.github.io/gomega/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo"), que é uma biblioteca de correspondência e asserção para o Ginkgo.

   * Instale o `ginkgo` usando o comando a seguir.

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * Instale o `gomega` usando o comando a seguir.

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * Execute testes de unidade usando o comando a seguir.

      ```
      ginkgo -r
      ```
      {: codeblock}

      * Para incluir cobertura de código, anexe `-cover` ao comando.

   * Para obter um formato HTML de cobertura de código propício, use o comando a seguir.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * Você é levado para o diretório no qual o arquivo `.coverprofile` está localizado.

* Globalização: [go-i18n](https://github.com/nicksnyder/go-i18n){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e [go-bindata](https://github.com/jteeuwen/go-bindata){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

A globalização é baseada em `go-i18n`, que é uma ferramenta de linha de comandos e pacote que fornece suporte para traduzir um aplicativo Go em vários idiomas. Os pacotes configuráveis
de tradução são pré-processados pelo comando `go-bindata` que converte qualquer arquivo de entrada no código-fonte gerenciável do Go.

   * Instale o `go-i18n` usando o comando a seguir.

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * Instale o `go-bindata` usando o comando a seguir.

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* Depuração: [delve ](https://github.com/go-delve/delve){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

O delve é um depurador para a linguagem de programação Go e é usado pelo [Visual Studio Code ](https://code.visualstudio.com/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo").

   * Instale o `delve` usando o comando a seguir.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Para Mac OS, siga as [instruções ](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") para criar o certificado autoassinado necessário.


## Bibliotecas de tempo de execução necessárias
{: #runtime-libs}

As bibliotecas de tempo de execução necessárias são gerenciadas sob o diretório `vendor` e são confirmadas para o repositório Git para assegurar a estabilidade, pois o Go não fornece um gerenciador de dependência robusto.

### Dependências de tempo de execução
{: #runtime-dependencies}

As dependências aninhadas não são listadas.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ](https://github.ibm.com/Bluemix/bluemix-cli-sdk){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

   O SDK do plug-in da CLI do {{site.data.keyword.cloud_notm}}, que fornece infraestrutura para desenvolver plug-ins da CLI do {{site.data.keyword.cloud_notm}}.

* [github.com/urfave/cli ](https://github.com/urfave/cli){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

   Este pacote fornece a infraestrutura para construir apps de linha de comandos no Go. O
plug-in da CLI do {{site.data.keyword.cloud_notm}} depende de uma versão mais antiga desta
biblioteca (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ](https://github.com/asaskevich/govalidator){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

   Esse pacote fornece um número de validadores e limpadores para sequências, estruturas e coleções. Use esse pacote em vez de implementar seus próprios validadores.

* [github.com/parnurzeal/gorequest ](https://github.com/parnurzeal/gorequest){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

   Esse pacote implementa um cliente HTTP simplificado para ajudar a manipular solicitações e respostas de HTTP.

* [github.com/briandowns/spinner ](https://github.com/briandowns/spinner){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

   Esse pacote implementa um spinner de CLI para fornecer feedback do usuário enquanto as operações longas, como geração de SDK, estão sendo processadas.

* [github.com/cloudfoundry-attic/jibber_jabber ](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

   Esse pacote é usado para detectar a linguagem atual do sistema operacional.

## Clonando o repositório
{: #clone-repo}

O repositório deve ser clonado na [estrutura de diretório](https://golang.org/doc/code.html){: new_window} do Go ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") por causa de como o `govendor` funciona, o que também segue as melhores práticas do Go.

* Importe dependências internas por meio de um nome do pacote completo.

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* Clone o repositório.

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## Construindo, testando e instalando o plug-in
{: #build-plug-in}

Construa o plug-in escolhendo um dos comandos a seguir.
```
cd $GOPATH/src/github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin
go build main.go
```
{: codeblock}

```
cd $GOPATH/src/github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin
sh bin/build.sh
```
{: codeblock}

O script de construção também instala o plug-in para a CLI do {{site.data.keyword.Bluemix_notm}}.
{: note}

Teste o plug-in escolhendo um dos comandos a seguir.
```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

Execute testes de integração com testes de unidade e cobertura.
```
sh bin/testAll.sh
```
{: codeblock}

Execute o plug-in como uma CLI independente.
```
./main
```
{: codeblock}

Instale e chame o plug-in como uma CLI do {{site.data.keyword.cloud_notm}} escolhendo um dos comandos a seguir.
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
