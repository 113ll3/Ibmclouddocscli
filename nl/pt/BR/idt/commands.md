---

copyright:
   years: 2017, 2019
lastupdated: "2019-06-10"

keywords: cli, ibmcloud dev commands, ibmcloud dev build, ibmcloud dev run, ibmcloud dev debug, developer plugin cli, dev plugin commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Comandos de plug-in da CLI do {{site.data.keyword.dev_cli_notm}} (ibmcloud dev)
{: #idt-cli}

Versão: 2.1.18
Liberado: 28 de março de 2019

Desde maio de 2018, os comandos da CLI do {{site.data.keyword.cloud}} `bluemix` e `bx` agora são `ibmcloud`. No entanto, ainda é possível usar os comandos da CLI `bluemix` e `bx` até que eles sejam removidos posteriormente.
{: tip}

Use os comandos da CLI do {{site.data.keyword.dev_cli_notm}} (`ibmcloud dev`) para criar um aplicativo, gerenciar, implementar, depurar e testá-lo.

Execute múltiplos comandos em uma única instrução de linha de comandos usando [comandos compostos](#compound).
{: tip}

## compilação
{: #build}

Se você estiver usando o Windows&trade;, deverá estar executando o Windows&trade; 10 Pro ou mais recente.

É possível construir seu app usando o comando `build`. Os comandos `test`, `debug` e `run` esperam localizar um app compilado, portanto, deve-se executar uma operação `build` antecipadamente.

O elemento de configuração `build-cmd-debug` é usado para construir o app para todos os usos, exceto para `run`. Você constrói seu app para depuração especificando a opção da linha de comandos `--debug`. O elemento de configuração `build-cmd-run` é usado quando você está construindo o app para uso com o comando `run`.

Para construir com vários contêineres, seu app deve ter um arquivo [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") especificado em `cli-config.yml` ou é possível usar o parâmetro de comando `dockerfile-tools` para fornecer um.

Execute o comando a seguir em seu diretório de app atual para começar a construir:  
```
Ibmcloud dev build [ --debug ]
```
{: codeblock}

## code
{: #code}

Use o comando `code` para fazer download de um app criado anteriormente com o código de modelo de app e os arquivos de configuração para o {{site.data.keyword.cloud_notm}}. Será possível usar esse comando quando for necessário extrair uma segunda cópia de um app.

Execute o comando a seguir para fazer download do código de um app especificado.
```
ibmcloud dev code <appName>
```
{: codeblock}

## console
{: #console}

Use o comando `console` para abrir um navegador da web para o console da web do app no {{site.data.keyword.cloud_notm}}. É possível executar o comando `ibmcloud dev console` de dentro de sua pasta do app. A CLI tenta localizar um app correspondente no {{site.data.keyword.cloud_notm}} que tenha o mesmo ID do app que o diretório atual. Se o sistema não for capaz de localizar um nome correspondente, ele abrirá o painel **Web e dispositivo móvel** no {{site.data.keyword.cloud_notm}} em vez do app específico.

É possível fornecer um nome de app e a CLI ignorará a correspondência com base no nome da pasta ou do app. Nesse caso, a CLI abre o console do app nomeado em um navegador da web.  

Execute o comando a seguir para abrir um navegador da web no console da web de seu app.
```
ibmcloud dev console [appName]
```
{: codeblock}

## create
{: #create}

Crie um app que solicite todas as informações, incluindo o tipo de recurso, a linguagem, o kit do iniciador e as opções da cadeia de ferramentas do DevOps. Incluindo o IBM Cloud Foundry ou o Cloud Foundry Enterprise Environment e o Kubernetes. O app é criado no diretório atual.

Para criar um app no diretório atual e para associar serviços a ele, execute o comando a seguir:
```
Ibmcloud dev criar
```
{: codeblock}

## depuração
{: #debug}

Se você estiver usando o Windows&trade;, deverá executar o Windows&trade; 10 Pro ou mais recente.

É possível depurar o app por meio do comando `debug`. Uma construção deve primeiro ser concluída no app usando o comando de construção com o argumento `--debug`. Ao iniciar o comando `debug`, um contêiner é iniciado fornecendo uma ou mais
portas de depuração, conforme definido pelo valor de `container-port-map-debug` no
cli-config.yml ou especificado na linha de comandos. Conecte sua ferramenta de depuração favorita à porta ou às portas e o app poderá ser depurado normalmente.

Primeiro, compile seu app:
```
ibmcloud dev build --debug
```
{: codeblock}

Para iniciar, execute o comando a seguir em seu diretório de app atual para começar a depurar:
```
Ibmcloud dev debug
```
{: codeblock}

Para depurar, conecte sua ferramenta de depuração à porta especificada.

Para sair da sessão de depuração, use `CTRL-C`.

### Parâmetros de comando de depuração
{: #debug-parameters}

Os parâmetros a seguir são exclusivos para o comando `debug` e ajudam a depurar um app. Há [mais parâmetros](#command-parameters) que são compartilhados com outros comandos.

#### `container-port-map-debug`
{: #port-map-debug}

* Mapeamentos de porta para a porta de depuração. O primeiro valor é a porta a ser usada no S.O. do host, o segundo é a porta no contêiner [`host-port:container-port`].
* Uso: `ibmcloud dev debug--container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parâmetro que é usado para construir o código para DEBUG.
* Uso: `ibmcloud dev debug--build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parâmetro que é usado para especificar um comando para iniciar a depuração no contêiner de ferramentas. Use esse parâmetro se o `build-cmd-debug` iniciar o app em depuração.
* Uso: `ibmcloud dev debug --debug-cmd /the/debug/command`

## Delete/Excluir
{: #delete}

Use o comando `delete` para remover apps de seu espaço do {{site.data.keyword.cloud_notm}}. É possível executar o comando sem parâmetros para listar os apps disponíveis e selecionar, na lista numerada, o app a ser excluído. O código do app e os diretórios não são removidos do espaço em disco local.

Execute o comando a seguir para excluir o app do {{site.data.keyword.cloud_notm}}:
```
ibmcloud dev delete <appName>
```
{: codeblock}

Os serviços do {{site.data.keyword.cloud_notm}}  não são removidos.
{: note}

## implementar
{: #deploy}

É possível implementar um app como um app do Cloud Foundry ou como um contêiner.

Antes de implementar um app do Cloud Foundry no {{site.data.keyword.cloud_notm}}, um arquivo `manifest.yml` deve estar presente no diretório-raiz do app.

Antes de implementar um app como um contêiner, deve-se instalar localmente o [Kubernetes](https://kubernetes.io/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e o [Helm](https://github.com/helm/helm){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo"). A versão cliente do Helm não deve ser mais recente do que a versão do servidor do Helm. É possível localizar ambos executando `helm version`. Recomenda-se usar a v2.4.2 para a versão cliente.

Para implementar seu app no Kubernetes, deve-se especificar o `deploy-target` como `container` no `cli-config.yml` ou usar o parâmetro `-t container`.

Outros parâmetros necessários para configurar a implementação do Kubernetes também podem ser especificados no `cli-config.yml` usando os argumentos da linha de comandos. Se você não definir esses parâmetros no `cli-config.yml`, deverá implementar com o parâmetro `-t container`. Em seguida, você será solicitado a fornecer todos os outros valores.

```yaml
chart-path: "chart/myapp"

deploy-target: "container"

deploy-image-target: "registry.<IBM Cloud Region>.icr.io/<Container Registry Namespace>/<App-Name>"

ibm-cluster: "mycluster"
```

No `cli-config.yml`, é possível definir o local de um gráfico do Helm na propriedade `chart-path` e configurar o `deploy-image-target`, conforme mostrado no exemplo. O elemento `deploy-image-target` no `cli-config.yml` é usado em vez dos elementos `repository` e `tag` no arquivo `chart/values.yml`. Para implementar no {{site.data.keyword.cloud_notm}} especificamente, configure o elemento de configuração `ibm-cluster` para o nome do cluster Kubernetes que você criou no {{site.data.keyword.cloud_notm}}.

Execute o comando a seguir no seu diretório de aplicativos atual para construir seu app:  
```
ibmcloud dev build
```
{: codeblock}

Execute o comando a seguir em seu diretório de app atual para implementar seu app:
```
ibmcloud dev deploy
```
{: codeblock}

### Implemente no {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment 
{: #deploy-cfee}

É possível implementar em um {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment. Para fazer isso, configure seu ambiente local para esse ambiente usando o `ibmcloud target --cf` e, em seguida, selecione o ambiente correto nessa lista. É possível, então, usar o comando `deploy` como você faria para o {{site.data.keyword.cloud_notm}} Public Cloud Foundry.

### Parâmetros do comando de implementação
{: #deploy-parameters}

Os parâmetros a seguir podem ser usados com o comando `deploy` ou atualizando o arquivo `cli-config.yml` do app diretamente. Há [mais parâmetros](#command-parameters) que são compartilhados com outros comandos.

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

* Parâmetro usado opcionalmente para definir o nome do cluster do Kubernetes para uma implementação de contêiner no {{site.data.keyword.cloud_notm}}
* Uso `ibmcloud dev deploy -- ibm-cluster [ cluster-name ]`

#### `host `
{: #host}

* Parâmetro usado opcionalmente para definir o nome do host do app ao implementar no Cloud Foundry.
* Uso  ` ibmcloud dev deploy -- host [ hostname ] `

#### `domain`
{: #domain}

* Parâmetro usado opcionalmente para definir o domínio do app ao implementar no Cloud Foundry.
* Uso  ` ibmcloud dev deploy --domain [ domain ] `

## diag
{: #diag}

O comando `diag` é usado como um diagnóstico para exibir as informações da versão das dependências instaladas para a CLI do {{site.data.keyword.dev_cli_notm}}. Isso é útil para determinar se quaisquer dependências estão ausentes para você para ajudar a depurar problemas.

Execute o comando a seguir para exibir as versões das dependências instaladas:
```
ibmcloud dev diag
```
{: codeblock}

## editar
{: #edit}

Edite seu app com opções, como conectá-lo a um app já no {{site.data.keyword.cloud_notm}}, gerenciar os serviços do {{site.data.keyword.cloud_notm}} do app e sua cadeia de ferramentas do {{site.data.keyword.cloud_notm}} que é implementada no IBM Cloud Kubernetes, no Cloud Foundry ou no Cloud Foundry Enterprise Environment. Com um app local conectado a um app no {{site.data.keyword.cloud_notm}}, use `edit` para incluir novos serviços, conectar e desconectar serviços existentes ou remover serviços existentes de sua conta. Além disso, é possível criar ou visualizar uma cadeia de ferramentas do {{site.data.keyword.cloud_notm}} para o app. Execute o comando a seguir na raiz do diretório de app:
```
ibmcloud dev edit
```
{: codeblock}

Se não houver serviços existentes em sua conta, esse comando mostrará uma lista de grupos de serviços dos quais é possível selecionar um serviço a ser conectado ao app.

No entanto, se houver serviços existentes em sua conta, esse comando mostrará uma lista desses serviços e se cada serviço está conectado ao app ou não.

* Um serviço conectado fornece opções para desconectar o serviço de seu app ou excluir o serviço de sua conta, que o desconecta de todos os apps.

* Um serviço desconectado fornece opções para conectar esse serviço a seu app ou excluir o serviço de sua conta. Conectar um serviço existente também faz download de arquivos, como credenciais ou código-fonte.

Também é possível incluir um serviço em seu app, no qual você é guiado por meio de prompts de seleção de serviço para fazer download de arquivos, como arquivos de credenciais ou código-fonte.

## enable
{: #enable}

Ative um app existente para implementação do {{site.data.keyword.cloud_notm}}. O comando `enable` tenta detectar automaticamente o idioma de um app existente e, em seguida, solicita informações adicionais necessárias. Os arquivos são gerados para serem usados para contêineres locais do Docker, implementação do Cloud Foundry, implementação do Cloud Foundry Enterprise Environment ou implementação do Contêiner do Kubernetes. Todos os ambientes de implementação podem ser usados por meio de um `deploy` manual ou usando uma cadeia de ferramentas do DevOps.

Enquanto está com login efetuado no {{site.data.keyword.cloud_notm}}, é possível conectar esse app local a um app que já está no {{site.data.keyword.cloud_notm}} ou criar um novo app {{site.data.keyword.cloud_notm}}. Para tirar proveito de recursos do {{site.data.keyword.cloud_notm}}, como serviços e cadeias de ferramentas do DevOps, um app no {{site.data.keyword.cloud_notm}} é necessário. Quando um app do {{site.data.keyword.cloud_notm}} for criado para um app que é clonado de um repositório Git, o app {{site.data.keyword.cloud_notm}} incluirá esse repositório em sua configuração. 

` Ativar `  é um recurso Beta. Se você tiver problemas na nuvem ao ativar seu app, consulte [resolução de problemas](/docs/cli?topic=cloud-cli-troubleshoot). Especificamente, `enable` não é destinado a estruturas ou apps móveis. Para apps complexos que produzem vários ativos implementáveis, cada componente do app deve ser ativado individualmente. 

Execute o comando a seguir para ativar um app existente no diretório atual:
```
Ibmcloud dev enable
```
{: codeblock}

A presença de arquivos necessários fornece a detecção de idioma do app para uma estrutura de projeto válida.  

* A presença de um arquivo `package.json` identifica um app Node.js.
* A presença de um arquivo `package.swift` identifica um app Swift.
* A presença de um arquivo `setup.py` ou `requirements.txt` identifica um app Python.
* A presença de um arquivo `pom.xml` ou `build.gradle` identifica um app Java &trade;.
	* A presença de um `pom.xml` identifica um app Maven.
	* A presença de um `build.gradle` identifica um app Gradle.

Também é possível substituir a linguagem de app detectada usando o argumento `--language`. Somente os apps válidos e completos são suportados. O comando ativar não modifica o seu código-fonte.

### ativar opções de idioma
{: #enable-language-options}

As opções de linguagem incluem:
* node
* swift
* python
* java-ee (interpretado como Java&trade; - Java&trade; EE)
* java-mp (interpretado como Java&trade; - Java&trade; MicroProfile)
* java-spring (interpretado como Java&trade; - Spring Framework)

Os arquivos que são criados usando o comando `ibmcloud dev enable` e têm conflitos de nomes com arquivos existentes na pasta de app são salvos com uma extensão de arquivo `.merge`.  

### Parâmetros de comando de ativação
{: #enable-parameters}

Os parâmetros a seguir podem ser usados com o comando `enable` ou atualizando o arquivo `cli-config.yml` do app diretamente. Há [mais parâmetros](#command-parameters) que são compartilhados com outros comandos.

#### `language`
{: #enable-language}

* Parâmetro usado para especificar o idioma do app a ser ativado.
* Uso `ibmcloud dev enable -l | -- language [ language ]`

#### `force`
{: #enable-force}

* Parâmetro usado para forçar a reativação de um app já ativado.
* Uso `ibmcloud dev enable -f | -- force`

#### `no-create`
{: #enable-no-create}

* Parâmetro para evitar a criação de um app no {{site.data.keyword.cloud_notm}} e cria os arquivos de ativação localmente.
* Uso `ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

Para ativar o uso de serviços conectados, o app exige get-credentials.

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

É possível listar todos os apps do {{site.data.keyword.cloud_notm}} em um grupo de recursos.

Execute o comando a seguir para listar seus apps:
```
ibmcloud dev list
```
{: codeblock}

## execução
{: #run}

Se você estiver usando o Windows&trade;, deverá executar o Windows&trade; 10 Pro ou mais recente.

É possível executar o app por meio do comando `run`. Uma construção deve primeiro ser concluída no app usando o comando `build`. Quando você executa o comando `run`, o contêiner de execução é iniciado e expõe as portas conforme definido pelo parâmetro `container-port-map`. O parâmetro `run-cmd` será usado para chamar o app se o `Dockerfile` do contêiner de execução não contiver um ponto de entrada para concluir esta etapa.

Para executar com vários contêineres, seu app deve conter um arquivo [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") especificado no `cli-config.yml` ou é possível usar o parâmetro de comando `dockerfile-run` para fornecer um.

Primeiro, compile seu app:
```
ibmcloud dev build
```
{: codeblock}

Execute o comando a seguir no seu diretório de aplicativos atual para iniciar seu app:
```
ibmcloud dev run
```
{: codeblock}

Para sair da sessão, use `CTRL-C`.

### Parâmetros de comando de execução
{: #run-parameters}

Os parâmetros a seguir são exclusivos para o comando `run` e
ajudam no gerenciamento de seu app dentro do contêiner de execução. Há [parâmetros](#command-parameters) que são compartilhados com outros comandos.

#### `container-name-run`
{: #container-name-run2}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev run --container-name-run [<appName>]`

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
* Se você pretende executar com vários contêineres, use um arquivo do Compose.
* Para usar múltiplos arquivos editar, coloque uma lista delimitada por vírgula dos nomes de arquivo entre aspas duplas.
* Uso: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* Uso: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Imagem a ser criada de `dockerfile-run`.
* Uso: `ibmcloud dev run--image-name-run [ /path/to/image-name ]`

#### `run-cmd`
{: #run-cmd}

* O parâmetro que é usado para executar o código no contêiner de execução. Use esse parâmetro se a sua imagem iniciar seu app.
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

A CLI do {{site.data.keyword.dev_cli_short}} abre um shell interativo no contêiner do Docker do app. O contêiner de destino padrão para o comando shell é definido pelo valor `container-shell-target` no arquivo `cli-config.yml`, em que os valores válidos são `run` ou `tools`. Se esse valor não estiver definido ou um valor inválido for especificado, então, o comando `shell` direcionará o contêiner `tools` por padrão. O comando shell abre o contêiner no diretório especificado pela instrução `WORKDIR` no Dockerfile correspondente. Se `WORKDIR` não estiver listado no Dockerfile, a raiz do contêiner será usada como o diretório ativo. Consulte [esta referência](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") para obter mais informações.

Como alternativa, é possível decidir passar `run` ou `tools` como um argumento para o comando; esse contêiner é trazido e o shell é aberto para ele. Da mesma forma, é possível usar o parâmetro `container-name` para passar o nome do contêiner no qual você deseja efetuar shell. No entanto, essa sinalização é reservada para quando nenhum contêiner está em execução. Os argumentos `run` e `tools` são mais flexíveis e permitem que você alterne entre os contêineres quando um estiver em execução. Por exemplo, se o contêiner de ferramentas estiver em execução e você executar `ibmcloud dev shell run`, o contêiner `tools` será interrompido e o contêiner `run` será iniciado e vice-versa.

Se o contêiner de destino `run` ou `tools` ainda não estiver em execução quando você executar o comando `shell`, então, o contêiner de destino será iniciado. No entanto, o padrão `Cmd` ou `Entrypoint` no Dockerfile é substituído para ser iniciado diretamente no shell em vez de iniciar o processo do servidor. Isso permite iniciar o contêiner `run` ou `tools` e iniciar manualmente o servidor com seus próprios comandos arbitrários ou customizados.

Também é possível especificar o executável shell que você deseja abrir usando o parâmetro `container-shell`. Por padrão, `/bin/sh` é usado. Se você preferir usar o shell bash, especifique o valor `container-shell` como `/bin/bash`; no entanto, tenha em mente que o bash não está disponível automaticamente em todas as variantes do Linux&trade;.

Quaisquer argumentos adicionais que você passar para o comando além das sinalizações serão analisados como o comando a ser executado quando o shell for aberto. Se você fornecer um comando, o shell dentro do contêiner sairá após executar o comando e retornará você para o seu terminal.

Por exemplo, é possível executar o comando &trade; `ls` do Linux dentro do shell do contêiner de ferramentas, chamando `ibmcloud dev shell tools ls`. Também é possível especificar as sinalizações a serem passadas para a execução do comando shell, agrupando os argumentos entre aspas, como `ibmcloud dev shell "ls -la"`.

### Parâmetros de comando shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nome do contêiner no qual você deseja efetuar shell.
* Uso: `ibmcloud dev shell --container-name [<container-name>]`

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

Execute o comando a seguir em seu diretório de app atual para verificar o status do contêiner:
```
Ibmcloud dev status
```
{: codeblock}

[Parâmetros do comando de status](#command-parameters)

## pare
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

Os parâmetros a seguir são usados para o comando `stop`. Há [parâmetros](#command-parameters) que são compartilhados com outros comandos.

#### `container-name-run`
{: #container-name-run}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev stop --container-name-run [<appName>]`

#### `container-name-tools`
{: #container-name-tools}

* O nome do contêiner para o contêiner de ferramentas.
* Uso: `ibmcloud dev stop --container-name-tools [<appName>]`

## test
{: #test}

Se você estiver usando o Windows&trade;, deverá executar o Windows&trade; 10 Pro ou mais recente.

É possível testar o app por meio do comando `test`. Uma construção deve primeiro ser concluída no app usando o comando `build --debug`. O contêiner de ferramentas é então usado para iniciar o `test-cmd` para o app.

Primeiro, compile seu app:
```
ibmcloud dev build --debug
```
{: codeblock}

Execute o comando a seguir para testar seu app:
```
Teste ibmcloud dev
```
{: codeblock}

### Parâmetros de comando de teste
{: #test-parameters}

O parâmetro a seguir é exclusivo para o comando `test`. Há [parâmetros](#command-parameters) que são compartilhados com outros comandos.

#### `test-cmd`
{: #test-cmd}

* O parâmetro que é usado para especificar um comando para testar códigos no contêiner de ferramentas.
* Uso: `ibmcloud dev test -- test-cmd /the/test/command`

## view
{: #view}

É possível visualizar a URL para a qual seu app é implementado por meio do comando `view`. Execute esse comando no diretório-raiz do app que você deseja visualizar. O comando `view` também abre a URL em seu navegador padrão.

Para apps implementados no Cloud Foundry, a URL consiste no nome do host do app e no domínio do app.

Para apps implementados no Kubernetes, a URL consiste no endereço IP do nó no qual ela é implementada e na porta pública. Se o comando determinar que o app foi implementado no Kubernetes, a ferramenta CLI solicitará confirmação. Se você especificar que o app não foi implementado no Kubernetes, a URL do Cloud Foundry será mostrada. Caso você espere que o comando mostre a URL para um app implementado do Kubernetes, assegure-se de que o `cli-config.yml` contenha uma entrada para `chart-path` ou forneça-a por meio da linha de comandos, conforme mostrado [aqui](#chart-path).

Execute o comando a seguir para visualizar seu app:
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

* Raiz do projeto a ser anexada à URL do app Cloud Foundry e Kubernetes.
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

Todas as sinalizações devem ficar após o comando final e ser aplicadas a todos os comandos aos quais essa sinalização está associada. Usando o `ibmcloud dev build/deploy/view -t container --trace` como um exemplo, a sinalização `--trace` é aplicado a todos os três comandos, mas o `-t` é aplicável somente aos dois comandos finais e não é aplicado ao comando `build`.

Os comandos a seguir podem ser usados com esse recurso:
`build, debug, deploy, get-credentials, run, stop, test, view`

Se um comando falhar por qualquer motivo, os comandos subsequentes não serão executados.

Se algum comando seguir `debug` ou `run`, a execução continuará se `debug` ou `run` for finalizado por meio de outros meios além de eliminar o processo por meio da janela do terminal atual. Insira `CTRL+C` para encerrar o processo e não executar os comandos subsequentes. Por exemplo, é possível executar `ibmcloud dev stop` de outra janela do terminal para parar o contêiner em execução e continuar a execução para o próximo comando.

## Parâmetros para construir, depurar, executar e testar
{: #command-parameters}

Os parâmetros a seguir podem ser usados com os comandos `build|debug|run|test` ou atualizando o arquivo `cli-config.yml` do app diretamente. Parâmetros extras estão disponíveis para os comandos [`debug`](#debug-parameters) e [`run`](#run-parameters).

Os parâmetros de comando que são inseridos na linha de comandos têm precedência sobre a configuração `cli-config.yml`.
{: note}

#### `config-file`  
{: #config-file}

* Especifique um arquivo cli-config.yml para ser usado para um comando.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Nome do contêiner para o contêiner de execução.
* Uso: `ibmcloud dev <run|status|stop> --container-name-run [<appName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* O nome do contêiner para o contêiner de ferramentas.
* Uso: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<appName>]`

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
