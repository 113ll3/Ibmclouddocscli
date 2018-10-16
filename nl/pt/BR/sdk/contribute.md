---

copyright:
  years: 2017
lastupdated: "2018-10-04"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Contribuindo com o plug-in do SDK
{: #contribute}

Siga estas diretrizes para contribuir com o plug--in do SDK da CLI do {{site.data.keyword.Bluemix}}.

## Configurando seu ambiente de desenvolvimento
{: #dev-env}

* [CLI ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/cloudfoundry/cli/releases) do Cloud Foundry

   A CLI do Cloud Foundry não é necessária, mas ajuda a acessar o {{site.data.keyword.Bluemix_notm}} por meio do Terminal.

   Para obter mais informações sobre a CLI do Cloud Foundry, veja a [documentação ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](/docs/cli/reference/cfcommands/index.html){: new_window}.

* [CLI ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://clis.{DomainName}/ui/home.html) do {{site.data.keyword.Bluemix_notm}}

   Esse plug-in é instalado na CLI do {{site.data.keyword.Bluemix_notm}}. A CLI do {{site.data.keyword.Bluemix_notm}} também fornece recursos úteis para acessar o {{site.data.keyword.Bluemix_notm}} por meio do Terminal.

   Para obter mais informações sobre a CLI do {{site.data.keyword.Bluemix_notm}}, veja a [documentação ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](/docs/cli/reference/bluemix_cli/index.html){: new_window}.

* [Ambiente de desenvolvimento ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://golang.org/doc/code.html) do Go

   O Go é estrito com relação a locais de pacotes, então sua origem deve ser definida dentro da estrutura de diretório `$GOPATH`. Defina suas variáveis `$GOPATH` e `$GOROOT` e inclua `$GOPATH/bin` em sua variável de ambiente `$PATH`, o que pode ser feito editando seu arquivo de configuração `~/.bash_profile` (no Mac OS).

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Gerenciador de dependência: [govendor ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/kardianos/govendor)

   A ferramenta `govendor` cria e gerencia as dependências do Go. Você não precisa dela a menos que planeje atualizar o diretório do fornecedor.

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

* Estrutura de teste BDD: [Ginkgo ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://onsi.github.io/ginkgo/)

A estrutura de teste é baseada no Ginkgo, uma estrutura de teste BDD para Go. Ele é usado com o [Gomega ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://onsi.github.io/gomega/), que é uma biblioteca de correspondente e asserção para o Ginkgo.

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

   * Obtenha um formulário HTML simples da cobertura de código, use o comando a seguir.

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * Acesse o diretório no qual o arquivo `.coverprofile` está localizado.

* Internacionalização: [go-i18n ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/nicksnyder/go-i18n) e [go-bindata ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/jteeuwen/go-bindata)

A internacionalização é baseada no go-i18n, que é um pacote e ferramenta de linha de comandos que fornece suporte para traduzir um aplicativo Go em várias linguagens. Os pacotes configuráveis de tradução são pré-processados pelo go-bindata, que é um comando que converte qualquer arquivo de entrada em código-fonte do Go gerenciável.

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

* Depuração: [delve ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/derekparker/delve)

O delve é um depurador para a linguagem de programação Go e é usado pelo [Visual Studio Code ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://code.visualstudio.com/).

   * Instale o `delve` usando o comando a seguir.

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Para Mac OS, siga as [instruções ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://blog.ralch.com/tutorial/golang-debug-with-delve/) para criar o certificado autoassinado necessário.


## Bibliotecas de tempo de execução necessárias
{: #runtime-libs}

As bibliotecas de tempo de execução necessárias são gerenciadas sob o diretório `vendor` e são confirmadas no repositório Git para assegurar a estabilidade, pois o Go não fornece um gerenciador de dependência robusto.

### Dependências de tempo de execução
{: #runtime-dependencies}

As dependências aninhadas não são listadas.

* [github.com/IBM-Cloud/ibm-cloud-cli-sdk ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/IBM-Cloud/ibm-cloud-cli-sdk)

   O SDK do plug-in da CLI do {{site.data.keyword.Bluemix_notm}}, que fornece infraestrutura para desenvolver plug-ins da CLI do {{site.data.keyword.Bluemix_notm}}.

* [github.com/urfave/cli ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/urfave/cli)

   Este pacote fornece infraestrutura para construir apps de linha de comandos no Go. O plug-in da CLI do {{site.data.keyword.Bluemix_notm}} depende de uma versão mais antiga desta biblioteca (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/asaskevich/govalidator)

   Esse pacote fornece um número de validadores e limpadores para sequências, estruturas e coleções. Use este pacote em vez de implementar nossos próprios validadores.

* [github.com/parnurzeal/gorequest ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/parnurzeal/gorequest)

   Esse pacote implementa um cliente HTTP simplificado para ajudar a manipular solicitações e respostas de HTTP.

* [github.com/briandowns/spinner ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/briandowns/spinner)

   Esse pacote implementa um spinner de CLI para fornecer feedback do usuário enquanto as operações longas, como geração de SDK, estão sendo processadas.

* [github.com/cloudfoundry-attic/jibber_jabber ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/cloudfoundry-attic/jibber_jabber)

   Esse pacote é usado para detectar a linguagem atual do sistema operacional.


## Clonando o repositório
{: #clone-repo}

Este [repositório ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/tree/compute) deve ser clonado para a [estrutura de diretório ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://golang.org/doc/code.html) do Go devido a como o `govendor` funciona, que também segue as melhores práticas do Go.

* Importe dependências internas por meio de um nome do pacote completo.

   ```
   import (
      ...
      "github.ibm.com/ibm-cloud-mobile-services/bmd-codegen-sdkgen-cli-cli-plugin/plugin")
   ```
   {: codeblock}

* Clone o repositório.

   ```
   mkdir -p $GOPATH/src/github.ibm.com/ibm-cloud-mobile-services
   cd $GOPATH/src/github.ibm.com/ibm-cloud-mobile-services
   git clone https://github.ibm.com/ibm-cloud-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## Construindo, testando e instalando o plug-in
{: #build-plug-in}

Construa o plug-in escolhendo um dos comandos a seguir.

```
cd $GOPATH/src/github.ibm.com/ibm-cloud-mobile-services/bmd-codegen-sdkgen-cli-plugin go build main.go
```
{: codeblock}

```
cd $GOPATH/src/github.ibm.com/ibm-cloud-mobile-services/bmd-codegen-sdkgen-cli-plugin sh bin/build.sh
```
{: codeblock}

**Nota**: o script de construção também instala o plug-in para a CLI do {{site.data.keyword.Bluemix_notm}}.

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

Instale e chame o plug-in como uma CLI do {{site.data.keyword.Bluemix_notm}} escolhendo um dos comandos a seguir.

```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
