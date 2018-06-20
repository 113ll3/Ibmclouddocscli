---

copyright:

   years: 2017, 2018

lastupdated: "2018-06-08"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}  

# {{site.data.keyword.dev_cli_notm}} CLI (ibmcloud dev) comandos
{: #idt-cli}

Versão: 1.2.0
Liberação: 08 de março de 2018

Desde maio de 2018 comandos da CLI do {{site.data.keyword.Bluemix_notm}} mudaram de `bluemix` e `bx` para `ibmcloud`. No entanto, ainda é possível usar os comandos da CLI `bluemix` e `bx` até que sejam removidos em uma data posterior.
{: tip}

Use os comandos da CLI do {{site.data.keyword.dev_cli_notm}} (ibmcloud dev) a seguir para criar um projeto, implementar, depurar e testá-lo.

- [build](#build): construa o projeto em um contêiner local
- [code](#code): faça download do código de um projeto
- [console](#console): abre o console do IBM Cloud para um projeto
- [create](#create): cria um novo projeto e dá a opção de incluir serviços
- [debug](#debug): depure seu aplicativo em um contêiner local
- [delete](#delete): exclui um projeto de seu espaço
- [deploy](#deploy): implemente um aplicativo no IBM Cloud
- [enable](#enable): inclua arquivos do IBM Cloud em um projeto existente
- [get-credentials](#get-credentials): obtém credenciais que são necessárias pelo
projeto para ativar o uso de serviços ligados
- [help](#help): ajuda sobre sintaxe e argumentos do IDT
- [list](#list): liste todos os projetos do IBM Cloud em um espaço
- [run](#run): execute seu aplicativo em um contêiner local
- [shell](#shell): abra um shell em um contêiner local
- [status](#status): verifique o status dos contêineres que são usados pela CLI
- [stop](#stop): pare um contêiner
- [test](#test): teste seu aplicativo em um contêiner local
- [view](#view): visualize os apps implementados por URL para teste e
visualização
- [compound commands](#compound): execute vários comandos em uma instrução de linha
de comandos



## compilação
{: #build}

É possível construir seu aplicativo usando o comando `build`. Os comandos `test`, `debug` e `run` esperam localizar um projeto compilado, portanto deve-se primeiro executar uma operação `build` antecipadamente.  

O elemento de configuração `build-cmd-debug` é usado para construir o aplicativo para todos os usos, exceto para `run`. Você constrói seu aplicativo para depuração especificando a opção da linha de comandos `--debug`.  O elemento de configuração `build-cmd-run` é usado quando você
está construindo o aplicativo para uso com o comando `run`.

Para construir com múltiplos contêineres, seu projeto deve conter um arquivo
[Compose](https://docs.docker.com/compose/overview/), que é especificado no
`cli-config.yml` ou é possível usar o parâmetro de comando `dockerfile-tools`
para fornecer um. Consulte [Editar arquivo](/docs/apps/projects/compose_file.html) para obter mais informações.

Execute o comando a seguir no diretório de projeto atual para construir seu aplicativo:  

```
Ibmcloud dev build [ --debug ]
```
{: codeblock}


[Parâmetros do comando de construção](#command-parameters)


## code
{: #code}

Use o comando `code` para fazer download de um projeto criado anteriormente com o código de modelo de aplicativo e arquivos de configuração para o {{site.data.keyword.Bluemix_notm}}.  Isso é útil ao precisar extrair uma segunda cópia de um projeto que você criou.

Execute o comando a seguir para fazer download do código de um projeto especificado.

```
ibmcloud dev code <projectName>
```
{: codeblock}


## console
{: #console}

Use o comando `console` para abrir um navegador da web para o console da web do seu aplicativo no IBM Cloud.  É possível executar o comando `ibmcloud dev console` de dentro da pasta de seu projeto e a CLI tenta localizar um projeto correspondente no IBM Cloud que tenha o mesmo ID do projeto que o diretório atual. Se o sistema não consegue localizar um nome correspondente, ele abre o painel Web e Móvel no IBM Cloud em vez do projeto específico.

É possível fornecer um nome de projeto e a CLI ignora a correspondência com base no nome de pasta/aplicativo. Nesse caso, a CLI abre console do projeto nomeado em um navegador da web.  

Execute o comando a seguir para abrir um navegador da web para o console da web do seu aplicativo.

```
Ibmcloud dev console [ projectName ]
```
{: codeblock}


## create
{: #create}

Crie um projeto, solicitando todas as informações, incluindo tipo de recurso, linguagem, kit do iniciador e opções de cadeia de ferramentas do DevOps. O projeto é criado no diretório atual.

Para criar um projeto no diretório atual e associar serviços a ele, execute o comando a seguir:

```
Ibmcloud dev criar
```
{: codeblock}


## depuração
{: #debug}

É possível depurar o aplicativo por meio do comando `debug`. Uma construção deve primeiro ser concluída com relação ao projeto usando o comando de construção com o argumento `--debug`. Ao iniciar o comando `debug`, um contêiner é iniciado fornecendo uma ou mais
portas de depuração, conforme definido pelo valor de `container-port-map-debug` no
cli-config.yml ou especificado na linha de comandos. Conecte sua ferramenta de depuração favorita à porta ou portas e será possível depurar seu aplicativo normalmente.

Primeiro, compile seu projeto:

```
ibmcloud dev build --debug
```
{: codeblock}

Para iniciar, execute o comando a seguir no diretório de projeto atual para depurar seu aplicativo:

```
Ibmcloud dev debug
```
{: codeblock}

Para depurar, conecte sua ferramenta de depuração à porta especificada.

Para sair da sessão de depuração, use `CTRL-C`.


### Parâmetros de comando de depuração
{: #debug-parameters}

Os parâmetros a seguir são exclusivos para o comando `debug` e
ajudam na depuração de um aplicativo. Há [parâmetros adicionais](#command-parameters) compartilhados com outros comandos.

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

* Parâmetro que é usado para especificar um comando para chamar a depuração no contêiner de ferramentas. Use esse parâmetro se o `build-cmd-debug` iniciar seu aplicativo em depuração.
* Uso: `ibmcloud dev debug --debug-cmd /the/debug/command`



## excluir
{: #delete}

Use o comando `delete` para remover projetos do seu espaço do {{site.data.keyword.Bluemix}}. É possível executar o comando sem parâmetros para listar os projetos disponíveis e selecionar o projeto na lista numerada para exclusão. O código do projeto e os diretórios não são removidos do seu espaço de disco local.

Execute o comando a seguir para excluir seu projeto do {{site.data.keyword.Bluemix}}:

```
ibmcloud dev delete <projectName>
```
{: codeblock}


**Nota:** os serviços do {{site.data.keyword.Bluemix}} **não** são removidos.


## implementar
{: #deploy}

É possível implementar um aplicativo como um aplicativo Cloud Foundry ou como um contêiner.

Para implementar como um aplicativo Cloud Foundry no {{site.data.keyword.Bluemix}}, um arquivo `manifest.yml` deve estar presente no diretório raiz do seu projeto.

Para implementar um aplicativo como um contêiner, deve-se instalar localmente o [Kubernetes](https://kubernetes.io/) e o [Helm](https://github.com/kubernetes/helm). A versão do cliente Helm não deve ser mais recente que a versão do servidor Helm. É possível localizar ambos executando `helm version`. Recomendamos usar v2.4.2 para a versão do cliente.

No `cli-config.yml`, é possível escolher definir o local de um gráfico Helm na propriedade `chart-path`, configurar o elemento `deploy-target` para `container` e configurar o `deploy-image-target` como mostrado no exemplo. O elemento `deploy-image-target` no `cli-config.yml` é usado em vez dos elementos `repository` e `tag` no arquivo `chart/values.yml`. Para
implementar no {{site.data.keyword.Bluemix}} especificamente, configure o elemento de configuração `ibm-cluster` para o nome do cluster do Kubernetes que você criou no {{site.data.keyword.Bluemix}},
conforme descrito no [Tutorial: criando clusters](/docs/containers/cs_tutorials.html#cs_cluster_tutorial).

Para obter mais informações sobre o fornecimento, configuração e implementação para um cluster do Kubernetes, veja o tutorial [Implementar um aplicativo da web escalável no Kubernetes](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes).

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

Se você não os definir no cli-config.yml, deverá implementar com o parâmetro `-t contêiner`, e todos os outros valores serão solicitados.

Execute o comando a seguir no diretório de projeto atual para construir seu aplicativo:  

```
ibmcloud dev build
```
{: codeblock}

Execute o comando a seguir em seu diretório de projeto atual para implementar o projeto:

```
ibmcloud dev deploy
```
{: codeblock}


### Parâmetros do comando de implementação
{: #deploy-parameters}

Os parâmetros a seguir podem ser usados com o comando `deploy` ou atualizando o arquivo `cli-config.yml` do projeto diretamente. Há [parâmetros adicionais](#command-parameters) compartilhados com outros comandos.

#### `chart-path`
{: #chart-path}

* Parâmetro usado para uma implementação de contêiner para especificar o local do gráfico Helm usado para a implementação.
* Uso `ibmcloud dev deploy -- chart-path [ /the/path ]`

#### `deploy-target`
{: #deploy-target}

* Parâmetro usado opcionalmente para indicar o tipo de implementação a ser concluída.  O tipo de implementação padrão é buildpack.
* Uso `ibmcloud dev deploy -t | -- target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parâmetro usado com uma implementação de contêiner como o nome da imagem de destino para a implementação (por exemplo, para identificar um registro do Docker).  O valor não deve incluir uma versão, por exemplo: image-name:{version}, porque a versão é incrementada e anexada automaticamente pelo `deploy`.
* Uso `ibmcloud dev deploy--deploy-image-target [ image-name ]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parâmetro usado opcionalmente para definir o nome do cluster do Kubernetes para uma implementação de contêiner no {{site.data.keyword.Bluemix}}
* Uso `ibmcloud dev deploy -- ibm-cluster [ cluster-name ]`


## enable
{: #enable}

Ative um projeto existente para implementação do {{site.data.keyword.Bluemix_notm}}. O comando `enable` tenta detectar automaticamente a linguagem de um projeto existente e, em seguida, solicita as informações adicionais necessárias. Isso gera e inclui arquivos que podem ser usados para contêineres do Docker local, a implementação do CloudFoundry ou a implementação do Kubernetes/Contêiner.

Execute o comando a seguir para ativar um projeto existente no diretório atual para implementação do {{site.data.keyword.Bluemix_notm}}:

```
Ibmcloud dev enable
```
{: codeblock}

A presença de arquivos necessários fornece detecção de linguagem do projeto para uma estrutura do projeto válida.  

* A presença de um arquivo `package.json` identifica um projeto Node.js.
* A presença de um arquivo `package.swift` identifica um projeto Swift.
* A presença de um arquivo `setup.py` ou `requirements.txt` identifica um projeto Python.
* A presença de um arquivo `pom.xml` ou `build.gradle` identifica um projeto Java.
	* A presença de um `pom.xml` identifica um projeto Maven.
	* A presença de um `build.gradle` identifica um projeto Gradle.

Opcionalmente, também é possível substituir a linguagem do projeto detectada usando o argumento `--language`.  No entanto, somente projetos válidos e completos são suportados. O comando de ativação não modifica o seu código-fonte.

As opções de linguagem incluem:
* node
* swift
* python
* java-ee (interpretado como Java - Java EE)
* java-mp (interpretado como Java - Java MicroProfile)
* java-spring (interpretado como Java - Spring Framework)

Os arquivos criados usando o comando `ibmcloud dev enable` que têm conflitos de nomenclatura com os arquivos existentes na pasta do projeto são salvos com uma extensão de arquivo `.merge`.  

### Parâmetros de comando de ativação
{: #enable-parameters}

Os parâmetros a seguir podem ser usados com o comando `enable` ou atualizando o arquivo `cli-config.yml` do projeto diretamente. Há [parâmetros adicionais](#command-parameters) compartilhados com outros comandos.

#### `language`
{: #enable-language}

* Parâmetro usado para especificar a linguagem do projeto a ser ativada.
* Uso `ibmcloud dev enable -l | -- language [ language ]`

#### `force`
{: #enable-force}

* Parâmetro usado para forçar a reativação de um projeto já ativado.
* Uso `ibmcloud dev enable -f | -- force`


## get-credentials
{: #get-credentials}

Obtém as credenciais requeridas pelo projeto para ativar o uso de serviços de limite.


## help
{: #help}

Por padrão, se nenhuma ação ou argumento for passado ou se a ação 'help' for fornecida, esse comando mostrará um texto de "Ajuda" geral. A ajuda geral exibida inclui uma descrição dos argumentos de base, bem como uma listagem das ações disponíveis.  

Execute o comando a seguir para exibir informações da ajuda Geral:

```
ibmcloud dev help
```
{: codeblock}


## listar
{: #list}

É possível listar todos os projetos do {{site.data.keyword.Bluemix_notm}} em um espaço.

Execute o comando a seguir para listar seus projetos:

```
ibmcloud dev list
```
{: codeblock}


<!--
## edit
{: #edit}

You can edit a project, such as changing the name, pattern or starter type, or adding services to your project. Run the following command:

```
ibmcloud dev edit
```
{: codeblock}
-->


## execução
{: #run}

É possível executar seu aplicativo por meio do comando `run`. Uma construção deve primeiro ser concluída em relação ao projeto usando o comando `build`. Quando você chama o comando `run`, o contêiner de execução é iniciado e expõe as portas, como definido pelo parâmetro `container-port-map`. O parâmetro `run-cmd` poderá ser usado para chamar o aplicativo se o Dockerfile do contêiner de execução não contiver um ponto de entrada para concluir essa etapa.

Para executar com múltiplos contêineres, seu projeto deve conter um arquivo do [Compose](https://docs.docker.com/compose/overview/) especificado no `cli-config.yml` ou é possível usar o parâmetro de comando `dockerfile-run` para fornecer um. Consulte [Editar arquivo](/docs/apps/projects/compose_file.html) para obter mais informações.

Primeiro, compile seu projeto:

```
ibmcloud dev build
```
{: codeblock}

Execute o comando a seguir no diretório de projeto atual para iniciar seu aplicativo:

```
ibmcloud dev run
```
{: codeblock}

Para sair da sessão, use `CTRL-C`.


### Parâmetros de comando de execução
{: #run-parameters}

Os parâmetros a seguir são exclusivos para o comando `run` e
ajudam no gerenciamento do aplicativo dentro do contêiner de execução.
Há [parâmetros adicionais](#command-parameters) compartilhados com outros comandos.

#### `container-name-run`
{: #container-name-run2}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev run--container-name-run [<projectName>]`

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
* Se você pretende executar com múltiplos contêineres, esse deve ser um arquivo do Compose.
* Para usar múltiplos arquivos do Compose, circunde uma lista delimitada por vírgulas dos nomes de arquivos com aspas duplas.
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

É possível abrir o shell dentro do contêiner de execução ou de ferramentas com o comando `shell`.

Basta executar este comando

```
Ibmcloud dev shell
```

A CLI do {{site.data.keyword.dev_cli_short}} abrirá um shell interativo no contêiner do
docker do aplicativo. O contêiner de destino padrão para o comando shell é definido pelo valor `container-shell-target` no arquivo `cli-config.yml`, em que os valores válidos são `run` ou `tools`. Se esse valor não for definido ou um valor inválido for especificado, o comando `shell` direcionará para o contêiner `tools` por padrão. O comando shell abre o contêiner no diretório especificado pela instrução `WORKDIR` no Dockerfile correspondente. Se `WORKDIR` não estiver listado no Dockerfile, a raiz do contêiner será usada como o diretório ativo. Veja [esta referência](https://docs.docker.com/engine/reference/builder/#workdir) para obter mais informações.

Como alternativa, é possível decidir passar `run` ou `tools` como um argumento para o comando e esse contêiner será trazido para cima e o shell será aberto para esse contêiner. De forma semelhante, é possível usar o parâmetro `container-name` para passar o nome do contêiner no qual você deseja executar o shell. No entanto, essa sinalização deve ser reservada para quando nenhum contêiner está em execução. Os argumentos `run` e `tools` são mais flexíveis e permitem que você alterne entre contêineres no momento em que um está em execução. Por exemplo, se o contêiner de ferramentas estiver em execução e você executar `ibmcloud dev shell run`, o contêiner `tools` será interrompido e o contêiner `run` será iniciado e vice-versa.

Se o contêiner `run` ou `tools` de destino ainda não estiver em execução quando você executar o comando `shell`, o contêiner de destino será iniciado. No entanto, o padrão `Cmd` ou `Entrypoint` padrão no Dockerfile será substituído para ativar diretamente no shell em vez de iniciar o processo do servidor. Isso permite iniciar o contêiner `run` ou `tools` e iniciar manualmente o servidor com seus próprios comandos arbitrários ou customizados.


Também é possível especificar o executável do shell que você deseja abrir usando o parâmetro `container-shell`. Por padrão, `/bin/sh` é usado. Se você preferir usar o shell bash, especifique o valor `container-shell` para `/bin/bash`; entretanto, tenha em mente que o bash não está automaticamente disponível em todas as variantes do Linux.

Quaisquer argumentos adicionais que você passar para o comando além das sinalizações serão analisados como o comando a ser executado quando o shell for aberto. Se você fornecer um comando para ser executado, o shell dentro do contêiner sairá após a execução do comando e retornará para o seu terminal.

Por exemplo, é possível executar o comando `ls` do Linux dentro do shell do contêiner de ferramentas, chamando `ibmcloud dev shell tools ls`.   Também é possível especificar sinalizações adicionais a serem passadas para a execução do comando shell, agrupando os argumentos entre aspas, como `ibmcloud dev shell "ls -la"`.

### Parâmetros de comando shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nome do contêiner no qual você deseja executar o shell.
* Uso: `ibmcloud dev shell -- container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Especifica qual shell deve ser executado dentro do contêiner (o padrão é /bin/sh)
* Uso: `ibmcloud dev shell -- container-shell [ path/to/shell ]`


## status
{: #status}

É possível consultar o status dos contêineres que são usados pela CLI do
{{site.data.keyword.dev_cli_short}}, conforme definido por `container-name-run` e
por `container-name-tools`.

Execute o comando a seguir no diretório de projeto atual para verificar o status do contêiner:

```
Ibmcloud dev status
```
{: codeblock}


[Parâmetros do comando de status](#command-parameters)


## stop
{: #stop}

É possível parar seus contêineres por meio do comando `stop`.

Para parar as ferramentas e executar os contêineres, conforme definido em seu arquivo `cli-config.yml`, execute:

```
Ibmcloud dev stop
```
{: codeblock}

Para parar um contêiner que não é definido no arquivo `cli-config.yml`, é possível especificar um parâmetro extra da linha de comandos para sobrescrevê-lo.  Se nenhum contêiner for especificado no arquivo `cli-config.yml` ou na linha de comandos, o comando stop simplesmente será retornado.

### Parâmetros de comando de parada
{: #stop-parameters}

Os parâmetros a seguir são usados para o comando `stop`. Há [parâmetros adicionais](#command-parameters) compartilhados com outros comandos.

#### `container-name-run`
{: #container-name-run}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev stop--container-name-run [<projectName>]`

#### `container-name-tools`
{: #container-name-tools}

* O nome do contêiner para o contêiner de ferramentas.
* Uso: `ibmcloud dev stop--container-name-tools [<projectName>]`



## test
{: #test}

É possível testar o aplicativo por meio do comando `test`. Uma construção deve primeiro ser concluída com relação ao projeto usando o comando `build --debug`. O contêiner de ferramentas é então usado para chamar o `test-cmd` para o aplicativo.

Primeiro, compile seu projeto:

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

O parâmetro a seguir é exclusivo para o comando `test`.  Há [parâmetros adicionais](#command-parameters) compartilhados com outros comandos.

#### `test-cmd`
{: #test-cmd}

* O parâmetro que é usado para especificar um comando para testar códigos no contêiner de ferramentas.
* Uso: `ibmcloud dev test -- test-cmd /the/test/command`


## view
{: #view}

É possível visualizar a URL na qual seu aplicativo é implementado por meio do comando `view`. Execute esse comando no diretório-raiz do aplicativo que você deseja visualizar. O comando `view` também abrirá a URL em seu navegador padrão.

Para aplicativos implementados no Cloud Foundry, a URL consiste no nome do host do aplicativo e no domínio do aplicativo.

Para aplicativos implementados no Kubernetes, a URL consiste no endereço IP do nó no qual ele é implementado e na porta pública. Se o comando determinar que o app foi implementado no Kubernetes, a ferramenta CLI solicitará confirmação. Se você especificar que o aplicativo não foi, na realidade, implementado noo Kubernetes, a URL do Cloud Foundry será mostrada. Se você esperava que o comando mostrasse a URL para um aplicativo implementado pelo Kubernetes e isso não aconteceu, assegure-se que o `cli-config.yml` contenha uma entrada para `chart-path` ou forneça isso por meio da linha de comandos, como mostrado [aqui](#chart-path).

Execute o comando a seguir para visualizar seu aplicativo:

```
Visualização ibmcloud dev
```
{: codeblock}

### Parâmetros de comando de visualização
{: #view-parameters}

Os parâmetros a seguir são exclusivos para o comando `view`.

#### `deploy-target`

* O parâmetro usado opcionalmente para indicar o tipo de implementação a efetuar bypass do prompt
* Uso `dev ibmcloud visualização -t | -- target buildpack|container`


#### `no-open`
{: #no-open}

* O parâmetro que é usado para especificar para não abrir o navegador.
* Uso: `ibmcloud dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* A raiz do projeto para anexar à URL do app Kubernetes
* Uso: `ibmcloud dev view--web-app-root [ root ]`


#### `ibm-cluster`
{: #ibm-cluster2}

* O parâmetro usado opcionalmente para definir o nome do cluster do Kubernetes ao direcionar para uma implementação do contêiner
* Uso `ibmcloud dev view -- ibm-cluster [ cluster-name ]`


## Comandos compostos
{: #compound}

É possível executar múltiplos comandos em uma instrução de linha de comandos, separando os comandos do IDT com o delimitador `/`. As sinalizações de linha de comandos adicionais podem ser especificadas após você especificar os comandos compostos.  Os comandos a seguir são exemplos de como é possível usar comandos compostos:

```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Todas as sinalizações deverão rastrear o comando final e serão aplicadas a todos os comandos aos quais essa sinalização estiver associada. No exemplo acima, a sinalização `--trace` é aplicável a todos os 3 comandos, mas o `-t` é aplicável somente aos 2 comandos finais e, portanto, não será aplicado ao comando `build`.

Estes são os comandos que podem ser usados com esse recurso:
`build, debug, deploy, get-credentials, run, stop, test, view`

Se um comando falhar por qualquer motivo, os comandos subsequentes não serão executados. Se quaisquer comandos seguirem `debug` ou `run`, a execução continuará somente se `debug` ou `run` for finalizado por um meio diferente do encerramento do processo na janela do terminal atual. `CTRL+C` encerrará o processo e não executará os comandos subsequentes. Por exemplo, é possível executar `ibmcloud dev stop` de outra janela do terminal para parar o contêiner em execução e continuar a execução para o próximo comando.


## Parâmetros para construir, depurar, executar e testar
{: #command-parameters}

Os parâmetros a seguir podem ser usados com os comandos `build|debug|run|test` ou atualizando o arquivo `cli-config.yml` do projeto diretamente. Parâmetros extras estão disponíveis para os comandos [`debug`](#debug-parameters) e [`run`](#run-parameters).

**Nota**: os parâmetros de comando que são inseridos na linha de comandos têm precedência sobre a configuração `cli-config.yml`.

#### `config-file`  
{: #config-file}

* Especifique um arquivo cli-config.yml para ser usado para um comando.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev <run|status|stop> --container-name-run [<projectName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* O nome do contêiner para o contêiner de ferramentas.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<projectName>]`

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
* Como uma melhor prática e para evitar resultados inesperados, é necessário construir e executar usando as mesmas configurações de montagem.
* Uso: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Use essa opção para definir montagens entre o sistema host e o contêiner de ferramentas.
* Os valores `host-path-tools` e `container-path-tools` são inseridos no início desta lista.* Como uma melhor prática e para evitar resultados inesperados, é necessário construir e depurar usando as mesmas configurações de montagem.
* Uso: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parâmetro que é usado para especificar um comando para construir códigos para todos os usos, exceto DEBUG.
* Uso: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `rastreamento`
{: #trace}

* Use esse parâmetro para fornecer saída detalhada.
* Uso: `ibmcloud dev <build|debug|run|test> --trace`
