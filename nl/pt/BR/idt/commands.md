---

copyright:
   years: 2017, 2019
lastupdated: "2019-02-14"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Comandos de plug-in da CLI do {{site.data.keyword.dev_cli_notm}}  (ibmcloud dev)
{: #idt-cli}

Versão: 2.1.4 Liberada: 31 de agosto de 2018

Desde maio de 2018, os comandos da CLI do {{site.data.keyword.cloud}} `bluemix` e `bx` agora são `ibmcloud`. No entanto, ainda é possível usar os comandos da CLI `bluemix` e `bx` até que eles sejam removidos posteriormente.
{: tip}

Use os comandos da CLI do {{site.data.keyword.dev_cli_notm}} (`ibmcloud dev`) a seguir para criar um aplicativo, gerenciar, implementar, depurar e testá-lo.

- [build](#build): construa o aplicativo em um contêiner local.
- [code](#code): faça download do código para um aplicativo.
- [console](#console): abre o console do {{site.data.keyword.cloud_notm}} para um aplicativo.
- [create](#create): cria um novo aplicativo e fornece a você a opção de incluir serviços.
- [debug](#debug): depure o seu aplicativo em um contêiner local.
- [delete](#delete): exclui um aplicativo de seu espaço.
- [ deploy ](#deploy): Implemente um aplicativo no  {{site.data.keyword.cloud_notm}}.
- [diag](#diag): exibe informações de versão sobre dependências instaladas.
- [edit](#edit): inclua ou remova serviços de um aplicativo existente.
- [enable](#enable): atualize um aplicativo existente para uso com o {{site.data.keyword.cloud_notm}} Developer Tools.
- [get-credentials](#get-credentials): obtém credenciais que são requeridas pelo aplicativo. para ativar o uso de serviços  {{site.data.keyword.cloud_notm}}  conectados.
- [help](#help): ajuda na sintaxe e nos argumentos da CLI.
- [list](#list): liste todos os aplicativos do {{site.data.keyword.cloud_notm}} em um grupo de recursos.
- [run](#run): execute o seu aplicativo em um contêiner local.
- [shell](#shell): abra um shell em um contêiner local.
- [status](#status): verifique o status dos contêineres que são usados pela CLI.
- [ stop ](#stop): pare um contêiner.
- [test](#test): teste o seu aplicativo em um contêiner local.
- [view](#view): visualize a URL implementada do aplicativo para teste e visualização.
- [compound commands](#compound): execute múltiplos comandos em uma única instrução de linha de comandos.

## compilação
{: #build}

Se você estiver usando o Windows&trade;, deverá estar executando o Windows&trade; 10 Pro ou mais recente.

É possível construir seu aplicativo usando o comando `build`. Os comandos `test`, `debug` e `run` esperam localizar um aplicativo compilado, portanto, deve-se executar uma operação `build` antecipadamente.

O elemento de configuração `build-cmd-debug` é usado para construir o aplicativo para todos os usos, exceto para `run`. Você constrói seu aplicativo para depuração especificando a opção da linha de comandos `--debug`. O elemento de configuração `build-cmd-run` é usado quando você está construindo o aplicativo para uso com o comando `run`.

Para construir com múltiplos contêineres, o seu aplicativo deve ter um arquivo [Editar](https://docs.docker.com/compose/overview/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo"), que é especificado no `cli-config.yml`ou é possível usar o parâmetro de comando `dockerfile-tools` para fornecer um.

Execute o comando a seguir em seu diretório de aplicativo atual para construir seu aplicativo:  
```
Ibmcloud dev build [ --debug ]
```
{: codeblock}

## code
{: #code}

Use o comando `code` para fazer download de um aplicativo criado anteriormente com código de modelo de aplicativo e arquivos de configuração para o {{site.data.keyword.cloud_notm}}. É possível usar esse comando quando é necessário extrair uma segunda cópia de um aplicativo.

Execute o comando a seguir para fazer download do código de um aplicativo especificado.
```
ibmcloud dev code <applicationName>
```
{: codeblock}

## console
{: #console}

Use o comando `console` para abrir um navegador da web para o console da web do seu aplicativo no {{site.data.keyword.cloud_notm}}. É possível executar o comando `ibmcloud dev console` de dentro de sua pasta do aplicativo. A CLI tenta localizar um aplicativo correspondente no {{site.data.keyword.cloud_notm}} que tem o mesmo ID do aplicativo que o diretório atual. Se o sistema não for capaz de localizar um nome correspondente, ele abrirá o painel da web e Móvel no {{site.data.keyword.cloud_notm}} em vez do aplicativo específico.

É possível fornecer um nome do aplicativo e a CLI ignora a correspondência com base no nome da pasta ou do aplicativo. Nesse caso, a CLI abre o console do aplicativo nomeado em um navegador da web.  

Execute o comando a seguir para abrir um navegador da web para o console da web do seu aplicativo.
```
ibmcloud dev console [ applicationName ]
```
{: codeblock}

## create
{: #create}

Crie um aplicativo, enviando prompt para todas as informações, incluindo tipo de recurso, linguagem, kit do iniciador e opções da Cadeia de ferramentas do DevOps incluindo o IBM Cloud Foundry ou o Cloud Foundry Enterprise Environment e o Kubernetes. O aplicativo é criado no diretório atual.

Para criar um aplicativo no diretório atual e para associar serviços a ele, execute o comando a seguir:
```
Ibmcloud dev criar
```
{: codeblock}

## depuração
{: #debug}

Se você estiver usando o Windows&trade;, deverá executar o Windows&trade; 10 Pro ou mais recente.

É possível depurar o aplicativo por meio do comando `debug`. Uma construção deve primeiro ser concluída com relação ao aplicativo, usando o comando de construção com o argumento `--debug`. Ao iniciar o comando `debug`, um contêiner é iniciado fornecendo uma ou mais
portas de depuração, conforme definido pelo valor de `container-port-map-debug` no
cli-config.yml ou especificado na linha de comandos. Conecte sua ferramenta de depuração favorita à porta ou portas e será possível depurar seu aplicativo normalmente.

Primeiro, compile seu aplicativo:
```
ibmcloud dev build --debug
```
{: codeblock}

Para iniciar, execute o comando a seguir em seu diretório de aplicativo atual para depurar seu aplicativo:
```
Ibmcloud dev debug
```
{: codeblock}

Para depurar, conecte sua ferramenta de depuração à porta especificada.

Para sair da sessão de depuração, use `CTRL-C`.

### Parâmetros de comando de depuração
{: #debug-parameters}

Os parâmetros a seguir são exclusivos para o comando `debug` e
ajudam na depuração de um aplicativo. Há [parâmetros adicionais](#command-parameters) que são compartilhados com outros comandos.

#### `container-port-map-debug`
{: #port-map-debug}

* Mapeamentos de porta para a porta de depuração. O primeiro valor é a porta para usar no S.O. do host, o segundo é a porta no contêiner [host-port:container-port].
* Uso: `ibmcloud dev debug--container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parâmetro que é usado para construir o código para DEBUG.
* Uso: `ibmcloud dev debug--build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parâmetro que é usado para especificar um comando para iniciar a depuração no contêiner de ferramentas. Use esse parâmetro se o `build-cmd-debug` iniciar seu aplicativo em depuração.
* Uso: `ibmcloud dev debug --debug-cmd /the/debug/command`

## excluir
{: #delete}

Use o comando `delete` para remover aplicativos de seu espaço do {{site.data.keyword.cloud_notm}}. É possível executar o comando sem parâmetros para listar os aplicativos disponíveis e selecionar o aplicativo na lista numerada para excluir. O código do aplicativo e os diretórios não são removidos de seu espaço em disco local.

Execute o comando a seguir para excluir seu aplicativo do {{site.data.keyword.cloud_notm}}:
```
ibmcloud dev delete <applicationName>
```
{: codeblock}

Os serviços do {{site.data.keyword.cloud_notm}}  não são removidos.
{: note}

## implementar
{: #deploy}

É possível implementar um aplicativo como um aplicativo Cloud Foundry ou como um contêiner.

Antes de implementar um aplicativo do Cloud Foundry no {{site.data.keyword.cloud_notm}}, um arquivo `manifest.yml` deve estar presente no diretório raiz do seu aplicativo.

Antes de implementar um aplicativo como um contêiner, deve-se instalar localmente o [Kubernetes](https://kubernetes.io/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e o [Helm](https://github.com/kubernetes/helm){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo"). A versão cliente do Helm não deve ser mais recente do que a versão do servidor do Helm. É possível localizar ambos executando `helm version`. Recomenda-se usar a v2.4.2 para a versão cliente.

Para implementar seu aplicativo no Kubernetes, deve-se especificar o `deploy-target` como `container` no `cli-config.yml` ou usar o parâmetro `-t container`.

Outros parâmetros necessários para configurar a implementação do Kubernetes também podem ser especificados no `cli-config.yml` usando os argumentos da linha de comandos. Se você não definir esses parâmetros no `cli-config.yml`, deverá implementar com o parâmetro `-t container`. Em seguida, você será solicitado a fornecer todos os outros valores.

```yaml
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

No `cli-config.yml`, é possível escolher definir o local de um gráfico Helm na propriedade `chart-path` e configurar o `deploy-image-target` conforme mostrado no exemplo. O elemento `deploy-image-target` no `cli-config.yml` é usado em vez dos elementos `repository` e `tag` no arquivo `chart/values.yml`. Para implementar no {{site.data.keyword.cloud_notm}} especificamente, configure o elemento de configuração `ibm-cluster` para o nome do cluster Kubernetes que você criou no {{site.data.keyword.cloud_notm}}.

Execute o comando a seguir em seu diretório de aplicativo atual para construir seu aplicativo:  
```
ibmcloud dev build
```
{: codeblock}

Execute o comando a seguir em seu diretório de aplicativo atual para implementar seu aplicativo:
```
ibmcloud dev deploy
```
{: codeblock}

### Implemente no {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment 
{: #deploy-cfee}

É possível implementar em um {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment. Para fazer isso, configure o seu ambiente local para esse ambiente usando `ibmcloud target --cf` e, em seguida, escolha o ambiente correto nessa lista. É possível, então, usar o comando `deploy` como você faria para o {{site.data.keyword.cloud_notm}} Public Cloud Foundry.

### Parâmetros do comando de implementação
{: #deploy-parameters}

Os parâmetros a seguir podem ser usados com o comando `deploy` ou atualizando o arquivo `cli-config.yml` do aplicativo diretamente. Há [parâmetros adicionais](#command-parameters) que são compartilhados com outros comandos.

#### `chart-path`
{: #chart-path}

* Parâmetro usado para uma implementação de contêiner para especificar o local do gráfico Helm usado para a implementação.
* Uso `ibmcloud dev deploy -- chart-path [ /the/path ]`

#### `deploy-target`
{: #deploy-target}

* Parâmetro usado opcionalmente para indicar o tipo de implementação a ser concluída. O tipo de implementação padrão é buildpack.
* Uso `ibmcloud dev deploy -t | -- target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parâmetro que é usado com uma implementação de contêiner como o nome da imagem de destino para a implementação. O valor não deve incluir uma versão. Por exemplo: image-name:{versão} porque a versão é incrementada automaticamente e anexada por `deploy`.
* Uso `ibmcloud dev deploy--deploy-image-target [ image-name ]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parâmetro usado opcionalmente para definir o nome do cluster do Kubernetes para uma implementação de contêiner no {{site.data.keyword.Bluemix_notm}}
* Uso `ibmcloud dev deploy -- ibm-cluster [ cluster-name ]`

#### `host `
{: #host}

* Parâmetro opcionalmente usado para definir o nome do host do aplicativo quando você implementa no Cloud Foundry.
* Uso  ` ibmcloud dev deploy -- host [ hostname ] `

#### `domain`
{: #domain}

* Parâmetro opcionalmente usado para definir o domínio do aplicativo quando você implementa no Cloud Foundry.
* Uso  ` ibmcloud dev deploy --domain [ domain ] `

## diag
{: #diag}

Esse comando é usado como um diagnóstico para exibir as informações da versão das dependências instaladas para a CLI do {{site.data.keyword.dev_cli_notm}}. Isso é útil para determinar se quaisquer dependências estão ausentes para você para ajudar a depurar problemas.

Execute o comando a seguir para exibir as versões das dependências instaladas:
```
ibmcloud dev diag
```
{: codeblock}

## editar
{: #edit}

Edite o seu aplicativo com opções como conectá-lo a um aplicativo já no {{site.data.keyword.cloud_notm}}, gerenciando os serviços do {{site.data.keyword.cloud_notm}} do aplicativo e sua Cadeia de ferramentas do {{site.data.keyword.cloud_notm}} que implementa no IBM Cloud Kubernetes, no Cloud Foundry ou no Cloud Foundry Enterprise Environment. Com um aplicativo local que está conectado a um aplicativo no {{site.data.keyword.cloud_notm}}, use `edit` para incluir novos serviços, conectar e desconectar os serviços existentes ou remover serviços existentes de sua conta. Além disso, é possível criar ou visualizar uma cadeia de ferramentas do {{site.data.keyword.cloud_notm}} para o aplicativo. Execute o comando a seguir na raiz do diretório de aplicativo:
```
ibmcloud dev edit
```
{: codeblock}

Se você não tiver serviços existentes em sua conta, esse comando mostrará a você uma lista de grupos de serviços dos quais é possível selecionar um serviço para se conectar ao seu aplicativo.

No entanto, se você tiver algum serviço existente em sua conta, esse comando mostrará a você uma lista desses serviços e se cada serviço está conectado ao aplicativo ou não.

* Um serviço conectado fornece a você opções para desconectar o serviço de seu aplicativo ou excluir o serviço de sua conta, desconectando-o de todos os aplicativos aos quais ele está conectado.

* Um serviço desconectado fornece a você opções para conectar esse serviço ao seu aplicativo ou excluir o serviço de sua conta. Conectar um serviço existente também faz download de arquivos, como credenciais ou código-fonte, para começar a usar esse serviço.

Também é possível incluir um novo serviço em seu aplicativo, no qual você é guiado através dos prompts de seleção de serviço e faz download de arquivos adicionais como arquivos de credencial ou código-fonte para começar a usar o novo serviço.

## enable
{: #enable}

Ative um aplicativo existente para a implementação do  {{site.data.keyword.cloud_notm}} . O comando `enable` tenta detectar automaticamente a linguagem de um aplicativo existente e, em seguida, solicitar informações adicionais necessárias. Isso gera e inclui arquivos que podem ser usados para contêineres do Docker local, implementação do Cloud Foundry, implementação do Cloud Foundry Enterprise Environment ou implementação de Container do Kubernetes. Todos os ambientes de implementação podem ser utilizados por meio de uma `deploy` manual ou usando uma Cadeia de ferramentas do DevOps.

Quando conectado ao {{site.data.keyword.cloud_notm}}, é possível escolher conectar esse aplicativo local a um aplicativo que já está no {{site.data.keyword.cloud_notm}} ou criar um novo aplicativo do {{site.data.keyword.cloud_notm}}. Para aproveitar os recursos do {{site.data.keyword.cloud_notm}}, como serviços e cadeias de ferramentas do DevOps, um aplicativo no {{site.data.keyword.cloud_notm}} é necessário. Quando um app do {{site.data.keyword.cloud_notm}} for criado para um app que é clonado de um repositório Git, o app {{site.data.keyword.cloud_notm}} incluirá esse repositório em sua configuração. 

` Ativar `  é um recurso Beta. Se você tiver problemas ao ativar o seu aplicativo, a nossa [página de resolução de problemas](/docs/cli/ts_createapps.html#troubleshoot) terá ajuda para você. Em particular, `enable` não é destinado a aplicativos ou estruturas móveis. Para aplicativos complexos que produzem vários ativos implementáveis, cada componente do aplicativo deve ser ativado individualmente. 

Execute o comando a seguir para ativar um aplicativo existente no diretório atual:
```
Ibmcloud dev enable
```
{: codeblock}

A presença de arquivos necessários fornece detecção de idioma do aplicativo para uma estrutura do projeto válida.  

* A presença de um arquivo `package.json` identifica um aplicativo Node.js.
* A presença de um arquivo `package.swift` identifica um aplicativo Swift.
* A presença de um arquivo `setup.py` ou `requirements.txt` identifica um aplicativo Python.
* A presença de um arquivo `pom.xml` ou `build.gradle` identifica um aplicativo Java.
	* A presença de um `pom.xml` identifica um aplicativo Maven.
	* A presença de um `build.gradle` identifica um aplicativo Gradle.

Opcionalmente, também é possível substituir a linguagem do aplicativo detectado usando o argumento `--language`. Somente aplicativos válidos e completos são suportados. O comando ativar não modifica o seu código-fonte.

### ativar opções de idioma
{: #enable-language-options}

As opções de linguagem incluem:
* node
* swift
* python
* java-ee (interpretado como Java&trade; - Java&trade; EE)
* java-mp (interpretado como Java&trade; - Java&trade; MicroProfile)
* java-spring (interpretado como Java&trade; - Spring Framework)

Os arquivos que são criados usando o comando `ibmcloud dev enable` e têm conflitos de nomenclatura com arquivos existentes na pasta do aplicativo, são salvos com uma extensão de arquivo `.merge`.  

### Parâmetros de comando de ativação
{: #enable-parameters}

Os parâmetros a seguir podem ser usados com o comando `enable` ou atualizando o arquivo `cli-config.yml` do aplicativo diretamente. Há [parâmetros adicionais](#command-parameters) que são compartilhados com outros comandos.

#### `language`
{: #enable-language}

* Parâmetro usado para especificar a linguagem do aplicativo a ser ativada.
* Uso `ibmcloud dev enable -l | -- language [ language ]`

#### `force`
{: #enable-force}

* Parâmetro usado para forçar a reativação de um aplicativo já ativado.
* Uso `ibmcloud dev enable -f | -- force`

#### `no-create`
{: #enable-no-create}

* Parâmetro para evitar a criação de um app no {{site.data.keyword.Bluemix_notm}} ao criar os arquivos de ativação localmente.
* Uso `ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

As credenciais Get são requeridas pelo aplicativo para ativar o uso de serviços conectados.

## help
{: #help}

Por padrão, se nenhuma ação ou argumento for passado ou se a ação 'help' for fornecida, esse comando mostrará um texto de "Ajuda" geral. A ajuda geral exibida inclui uma descrição dos argumentos base e uma listagem das ações disponíveis.  

Execute o comando a seguir para exibir informações da ajuda Geral:
```
ibmcloud dev help
```
{: codeblock}

## listar
{: #list}

É possível listar todos os aplicativos {{site.data.keyword.cloud_notm}} em um grupo de recursos.

Execute o comando a seguir para listar seus aplicativos:
```
ibmcloud dev list
```
{: codeblock}

## execução
{: #run}

Se você estiver usando o Windows&trade;, deverá executar o Windows&trade; 10 Pro ou mais recente.

É possível executar seu aplicativo por meio do comando `run`. Uma construção deve primeiro ser concluída com relação ao aplicativo, usando o comando `build`. Quando você executa o comando `run`, o contêiner de execução é iniciado e expõe as portas conforme definido pelo parâmetro `container-port-map`. O parâmetro `run-cmd` será usado para chamar o aplicativo se o contêiner de execução `Dockerfile` não contiver um ponto de entrada para concluir esta etapa.

Para ser executado com múltiplos contêineres, o seu aplicativo deverá conter um arquivo [Editar](https://docs.docker.com/compose/overview/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo"), que é especificado no `cli-config.yml` ou é possível usar o parâmetro de comando `dockerfile-run` para fornecer um.

Primeiro, compile seu aplicativo:
```
ibmcloud dev build
```
{: codeblock}

Execute o comando a seguir em seu diretório de aplicativo atual para iniciar seu aplicativo:
```
ibmcloud dev run
```
{: codeblock}

Para sair da sessão, use `CTRL-C`.

### Parâmetros de comando de execução
{: #run-parameters}

Os parâmetros a seguir são exclusivos para o comando `run` e
ajudam no gerenciamento do aplicativo dentro do contêiner de execução.
Há [parâmetros adicionais](#command-parameters) que são compartilhados com outros comandos.

#### `container-name-run`
{: #container-name-run2}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev run--container-name-run [<applicationName>]`

#### `container-path-run`
{: #container-path-run}

* Local no contêiner para compartilhar na execução.
* Uso: `ibmcloud dev run--container-path-run [ /path/to/app ]`

#### `host-path-run`
{: #host-path-run}

* Local no sistema host para compartilhar no contêiner em execução.
* Uso: `ibmcloud dev run--host-path-run [ /path/to/app/bin ]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile para o contêiner de execução.
* Se você pretende executar com vários contêineres, este deve ser um arquivo Editar.
* Para usar múltiplos arquivos editar, coloque uma lista delimitada por vírgula dos nomes de arquivo entre aspas duplas.
* Uso: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* Uso: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Imagem a ser criada de `dockerfile-run`.
* Uso: `ibmcloud dev run--image-name-run [ /path/to/image-name ]`

#### `run-cmd`
{: #run-cmd}

* O parâmetro que é usado para executar o código no contêiner de execução. Use esse parâmetro se a sua imagem iniciar o aplicativo.
* Uso: `ibmcloud dev run -- run-cmd [ /the/run/command ]`

## shell
{: #shell}

Se você estiver usando o Windows&trade;, deverá ser executado o Windows&trade; 10 Pro ou mais recente.

É possível abrir o shell dentro do contêiner de execução ou de ferramentas com o comando `shell`.

Ao executar o comando a seguir:
```
Ibmcloud dev shell
```
{: codeblock}

A CLI do {{site.data.keyword.dev_cli_short}} abre um shell interativo no contêiner do docker do aplicativo. O contêiner de destino padrão para o comando shell é definido pelo valor `container-shell-target` no arquivo `cli-config.yml`, em que os valores válidos são `run` ou `tools`. Se esse valor não estiver definido ou um valor inválido for especificado, então, o comando `shell` direcionará o contêiner `tools` por padrão. O comando shell abre o contêiner no diretório especificado pela instrução `WORKDIR` no Dockerfile correspondente. Se `WORKDIR` não estiver listado no Dockerfile, a raiz do contêiner será usada como o diretório ativo. Consulte [esta referência](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") para obter mais informações.

Como alternativa, é possível decidir passar `run` ou `tools` como um argumento para o comando; esse contêiner é trazido e o shell é aberto para ele. Da mesma forma, é possível usar o parâmetro `container-name` para passar o nome do contêiner no qual você deseja efetuar shell. No entanto, essa sinalização deve ser reservada para quando nenhum contêiner está em execução. Os argumentos `run` e `tools` são mais flexíveis e permitem que você alterne entre os contêineres quando um estiver em execução. Por exemplo, se o contêiner de ferramentas estiver em execução e você executar `ibmcloud dev shell run`, o contêiner `tools` será interrompido e o contêiner `run` será iniciado e vice-versa.

Se o contêiner de destino `run` ou `tools` ainda não estiver em execução quando você executar o comando `shell`, então, o contêiner de destino será iniciado. No entanto, o padrão `Cmd` ou `Entrypoint` no Dockerfile é substituído para ser iniciado diretamente no shell em vez de iniciar o processo do servidor. Isso permite iniciar o contêiner `run` ou `tools` e iniciar manualmente o servidor com seus próprios comandos arbitrários ou customizados.

Também é possível especificar o executável shell que você deseja abrir usando o parâmetro `container-shell`. Por padrão, `/bin/sh` é usado. Se você preferir usar o shell bash, especifique o valor `container-shell` como `/bin/bash`; no entanto, tenha em mente que o bash não está disponível automaticamente em todas as variantes do Linux&trade;.

Quaisquer argumentos adicionais que você passar para o comando além das sinalizações serão analisados como o comando a ser executado quando o shell for aberto. Se você fornecer um comando, o shell dentro do contêiner sairá após executar o comando e retornará você para o seu terminal.

Por exemplo, é possível executar o comando &trade; `ls` do Linux dentro do shell do contêiner de ferramentas, chamando `ibmcloud dev shell tools ls`. Também é possível especificar sinalizações adicionais a serem passadas para a execução do comando shell, agrupando os argumentos entre aspas, como `ibmcloud dev shell "ls -la"`.

### Parâmetros de comando shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nome do contêiner no qual você deseja efetuar shell.
* Uso: `ibmcloud dev shell -- container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Especifica qual shell deve ser executado dentro do contêiner (o padrão é /bin/sh).
* Uso: `ibmcloud dev shell -- container-shell [ path/to/shell ]`

## status
{: #status}

Se você estiver usando o Windows&trade;, deverá estar executando o Windows&trade; 10 Pro ou mais recente.

É possível consultar o status dos contêineres que são usados pela CLI do
{{site.data.keyword.dev_cli_short}}, conforme definido por `container-name-run` e
por `container-name-tools`.

Execute o comando a seguir em seu diretório de aplicativos atual para verificar o status do contêiner:
```
Ibmcloud dev status
```
{: codeblock}

[Parâmetros do comando de status](#command-parameters)

## stop
{: #stop}

Se você estiver usando o Windows&trade;, deverá ser executado o Windows&trade; 10 Pro ou mais recente.

É possível parar seus contêineres por meio do comando `stop`.

Para parar as ferramentas e executar os contêineres, conforme definido em seu arquivo `cli-config.yml`, execute:
```
Ibmcloud dev stop
```
{: codeblock}

Para parar um contêiner que não está definido no arquivo `cli-config.yml`, é possível especificar um parâmetro de linha de comandos extra para substituí-lo. Se nenhum contêiner for especificado no arquivo `cli-config.yml` ou na linha de comandos, o comando stop simplesmente será retornado.

### Parâmetros de comando de parada
{: #stop-parameters}

Os parâmetros a seguir são usados para o comando `stop`. Há [parâmetros adicionais](#command-parameters) que são compartilhados com outros comandos.

#### `container-name-run`
{: #container-name-run}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev stop--container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* O nome do contêiner para o contêiner de ferramentas.
* Uso: `ibmcloud dev stop--container-name-tools [<applicationName>]`

## test
{: #test}

Se você estiver usando o Windows&trade;, deverá executar o Windows&trade; 10 Pro ou mais recente.

É possível testar o aplicativo por meio do comando `test`. Uma construção deve primeiro ser concluída com relação ao aplicativo, usando o comando `build --debug`. O contêiner de ferramentas é, então, usado para iniciar o `test-cmd` para o aplicativo.

Primeiro, compile seu aplicativo:
```
ibmcloud dev build --debug
```
{: codeblock}

Execute o comando a seguir para testar seu aplicativo:
```
Teste ibmcloud dev
```
{: codeblock}

### Parâmetros de comando de teste
{: #test-parameters}

O parâmetro a seguir é exclusivo para o comando `test`. Há [parâmetros adicionais](#command-parameters) que são compartilhados com outros comandos.

#### `test-cmd`
{: #test-cmd}

* O parâmetro que é usado para especificar um comando para testar códigos no contêiner de ferramentas.
* Uso: `ibmcloud dev test -- test-cmd /the/test/command`

## view
{: #view}

É possível visualizar a URL na qual seu aplicativo é implementado por meio do comando `view`. Execute esse comando no diretório raiz do aplicativo que você deseja visualizar. O comando `view` também abre a URL em seu navegador padrão.

Para aplicativos implementados no Cloud Foundry, a URL consiste no nome do host do aplicativo e no domínio do aplicativo.

Para aplicativos implementados no Kubernetes, a URL consiste no endereço IP do nó no qual ele está implementado e na porta pública. Se o comando determinar que o aplicativo foi implementado no Kubernetes, a ferramenta CLI solicitará confirmação. Se você especificar que o aplicativo não foi implementado no Kubernetes, então, a URL do Cloud Foundry será mostrada. Se você esperava que o comando mostrasse a URL para um aplicativo implementado do Kubernetes, assegure-se de que o `cli-config.yml` contenha uma entrada para `chart-path` ou forneça-a por meio da linha de comandos conforme mostrado [aqui](#chart-path).

Execute o comando a seguir para visualizar seu aplicativo:
```
Visualização ibmcloud dev
```
{: codeblock}

### Parâmetros de comando de visualização
{: #view-parameters}

Os parâmetros a seguir são exclusivos para o comando `view`.

#### `deploy-target`

* Parâmetro opcionalmente usado para indicar o tipo de implementação para efetuar bypass do prompt.
* Uso `dev ibmcloud visualização -t | -- target buildpack|container`

#### `no-open`
{: #no-open}

* O parâmetro que é usado para especificar para não abrir o navegador.
* Uso: `ibmcloud dev view --no-open`

#### `web-app-root`
{: #web-app-root}

* Raiz do projeto para anexar na URL do aplicativo do Cloud Foundry e do Kubernetes.
* Uso: `ibmcloud dev view--web-app-root [ root ]`

#### `ibm-cluster`
{: #ibm-cluster2}

* Parâmetro opcionalmente usado para definir o nome do cluster Kubernetes quando você destinar uma implementação de contêiner.
* Uso `ibmcloud dev view -- ibm-cluster [ cluster-name ]`

## Comandos compostos
{: #compound}

Você é capaz de executar vários comandos em uma instrução de linha de comandos, separando os comandos de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}} com o delimitador `/`. As sinalizações adicionais da linha de comandos poderão ser usadas após você especificar os comandos compostos. Os comandos a seguir são exemplos de como é possível usar comandos compostos:
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Todas as sinalizações devem ficar após o comando final e ser aplicadas a todos os comandos aos quais essa sinalização está associada. Usando o `ibmcloud dev build/deploy/view -t container --trace` como um exemplo, a sinalização `--trace` é aplicada a todos os três comandos, mas o `-t` é aplicável somente aos dois comandos finais e não será aplicado ao comando `build`.

Os comandos a seguir podem ser usados com esse recurso:
`build, debug, deploy, get-credentials, run, stop, test, view`

Se um comando falhar por qualquer motivo, os comandos subsequentes não serão executados.

Se algum comando seguir `debug` ou `run`, a execução continuará se `debug` ou `run` for finalizado por meio de outros meios além de eliminar o processo por meio da janela do terminal atual. `CTRL+C` elimina o processo e não executa os comandos subsequentes. Por exemplo, é possível executar `ibmcloud dev stop` de outra janela do terminal para parar o contêiner em execução e continuar a execução para o próximo comando.

## Parâmetros para construir, depurar, executar e testar
{: #command-parameters}

Os parâmetros a seguir podem ser usados com os comandos `build|debug|run|test` ou atualizando o arquivo `cli-config.yml` do aplicativo diretamente. Parâmetros extras estão disponíveis para os comandos [`debug`](#debug-parameters) e [`run`](#run-parameters).

Os parâmetros de comando que são inseridos na linha de comandos têm precedência sobre a configuração `cli-config.yml`.
{: note}

#### `config-file`  
{: #config-file}

* Especifique um arquivo cli-config.yml para ser usado para um comando.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* O nome do contêiner para o contêiner de ferramentas.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

#### `host-path-tools`
{: #host-path-tools}

* Local no host a ser compartilhado para construção, depuração, teste.
* Uso: `ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Local no contêiner a ser compartilhado para construção, depuração, teste.
* Uso: `ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Mapeamentos de porta para o contêiner. O primeiro valor é a porta para usar no S.O. do host, o segundo é a porta no contêiner [host-port:container-port].
* Uso: `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Dockerfile para o contêiner de ferramentas.
* Uso: `ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Imagem a ser criada de `dockerfile-tools`.
* Uso: `ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* Use essa opção para definir montagens entre o sistema host e o contêiner de execução.
* Os valores `host-path-run` e `container-path-run` são inseridos no início desta lista.
* Como uma melhor prática e para evitar resultados inesperados, é possível construir e executar usando as mesmas configurações de montagem.
* Uso: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Use essa opção para definir montagens entre o sistema host e o contêiner de ferramentas.
* Os valores `host-path-tools` e `container-path-tools` são inseridos no início desta lista.* Como uma melhor prática e para evitar resultados inesperados, é possível construir e depurar usando as mesmas configurações de montagem.
* Uso: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parâmetro que é usado para especificar um comando para construir códigos para todos os usos, exceto DEBUG.
* Uso: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `rastreamento`
{: #trace}

* Use esse parâmetro para fornecer saída detalhada.
* Uso: `ibmcloud dev <build|debug|run|test> --trace`
