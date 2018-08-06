---

copyright:
  years: 2015, 2018
lastupdated: "2018-07-17"

---



{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}


# Depurando aplicativos cf para o {{site.data.keyword.Bluemix_notm}}
{: #debugging}

Se você tiver problemas com o {{site.data.keyword.Bluemix}}, será possível visualizar os arquivos de log para investigar os problemas e depurar os erros.
{:shortdesc}

Os logs fornecem informações, tais como se uma tarefa é executada com sucesso ou se ela falha. Eles também fornecem informações relevantes que podem ser usadas para depurar e determinar a causa de um problema.

Os logs estão em um formato fixo. Para logs detalhados, é possível filtrar os logs ou usar os hosts de criação de log externa para armazenar e processar os logs. Para obter mais informações sobre formatos de log, visualização e filtragem de logs e configuração de criação de log externa, consulte [Criando log para apps que estão em execução no Cloud Foundry ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/monitor_log/logging.html#logging){: new_window}.


## Depurando erros de preparação
{: #debugging-staging-errors}
Você poderá ter problemas ao preparar seus aplicativos no {{site.data.keyword.Bluemix_notm}}. Se o seu aplicativo falhar na preparação, será possível procurar e revisar os logs de preparação (STG) para determinar o que aconteceu durante a implementação do aplicativo e recuperar-se do problema. Para obter mais informações sobre os métodos de visualização de logs para aplicativos {{site.data.keyword.Bluemix}}, consulte [Visualizando logs ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana){: new_window}.  

Para entender por que o seu aplicativo pode estar falhando no {{site.data.keyword.Bluemix_notm}}, é necessário saber como um aplicativo é implementado no {{site.data.keyword.Bluemix_notm}} e executado nele. Para obter mais informações, consulte [Implementação do aplicativo ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/cfapps/depapps.html#appdeploy){: new_window}.


O procedimento a seguir mostra como é possível usar o comando `cf logs` para depurar erros. Antes de executar as etapas a seguir, assegure-se de que você tenha instalado a interface da linha de comandos do Cloud Foundry. Para obter mais informações sobre como instalar a interface da linha de comandos do Cloud Foundry, veja [Instalando a interface da linha de comandos do Cloud Foundry ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/starters/install_cli.html){: new_window}.

  1. Conecte-se ao {{site.data.keyword.Bluemix_notm}} inserindo o código a seguir na interface da linha de comandos do Cloud Foundry:
     ```
	 cf api https://api.ng.bluemix.net
	 ```

  2. Efetue login no {{site.data.keyword.Bluemix_notm}} inserindo `cf login`.

  3. Recupere os logs recentes inserindo `cf logs appname --recent`. Se você desejar filtrar um log detalhado, use a opção `grep`. Por exemplo, é possível inserir o código a seguir para exibir somente os logs [STG]:
    ```
	cf logs appname --recent | grep '\[STG\]'
	```
  4. Visualize o primeiro erro que foi exibido no log.

Se você usar as ferramentas IBM Eclipse para o plug-in do {{site.data.keyword.Bluemix_notm}} para implementar aplicativos, na guia **Console** da ferramenta Eclipse, será possível ver logs que são semelhantes à saída de logs de cf. É possível também abrir uma janela do Eclipse separada para controlar `os logs` ao implementar o aplicativo.

Além do comando `cf logs`, no {{site.data.keyword.Bluemix_notm}} também é possível usar o serviço {{site.data.keyword.loganalysisshort}} para coletar os detalhes do log.

### Depurando erros de preparação para um aplicativo Node.js

O exemplo a seguir mostra um log que é exibido após a inserção de `cf logs appname --recent`. O exemplo presume que ocorreram erros para um aplicativo Node.js:
```
2014-08-11T14:19:36.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({name"=>"SampleExpressApp"}
2014-08-11T14:20:44.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STOPPED"})
2014-08-11T14:20:44.19+0100 [App/0]   ERR
2014-08-11T14:20:44.43+0100 [DEA]     OUT Stopping app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:44.44+0100 [DEA]     OUT Stopped app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:48.97+0100 [DEA]     OUT Got request for app with id 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:50.94+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STARTED"})
2014-08-11T14:20:51.66+0100 [STG]     OUT -----> Download app package (4.1M)
2014-08-11T14:20:51.90+0100 [STG]     OUT -----> Download app buildpack cache (1.1M)
2014-08-11T14:20:52.78+0100 [STG]     OUT -----> Buildpack Version: v1.1-20140717-1447
2014-08-11T14:20:52.78+0100 [STG]     ERR parse error: Expected another key-value pair at line 18, column 3
2014-08-11T14:20:52.79+0100 [STG]     OUT 0 info it worked if it ends with ok
```
{: screen}


O primeiro erro no log mostra o motivo  porquê a preparação falha. No exemplo, o primeiro erro é uma saída do componente DEA durante a fase de preparação.
```
2014-08-11T14:20:52.78+0100 [STG]   ERR parse error: expected another key-value pair at line 18, column 3
```
{: screen}


Para um aplicativo Node.js, o DEA usa as informações no arquivo `package.json` para fazer download dos módulos. A partir deste erro, é possível ver que o erro ocorre para o módulo. Portanto, poderá ser necessário revisar a 18º linha do arquivo `package.json`.

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*",
18   }
```
{: screen}


É possível ver que uma vírgula é colocada no final da linha 17, portanto, um par chave-valor que está na linha 18 é esperado. Para corrigir o problema, remova a vírgula:

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*"
18   }
```
{: screen}


## Depurando erros de tempo de execução
{: #debugging-runtime-errors}
Se você tiver problemas com seu aplicativo no tempo de execução, os logs do aplicativo poderão ajudar a identificar a causa do erro e recuperar desse problema.

Especificamente, a criação de log para saída padrão e erro padrão pode ser ativada. Para obter mais informações sobre como configurar os arquivos de log para aplicativos que são implementados usando os buildpacks integrados do {{site.data.keyword.Bluemix_notm}}, consulte a lista a seguir:

  * Para aplicativos Liberty for Java™, consulte [Liberty: criação de log e rastreio ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/en/SSEQTP_liberty/com.ibm.websphere.wlp.doc/ae/rwlp_logging.html){: new_window}.
  * Para aplicativos Node.js, consulte [A depuração de Node.js começa com a melhor criação de log! ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/blogs/bluemix/2015/03/node-js-better-logging/){: new_window}.
  * Para aplicativos PHP, consulte [error_log ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://php.net/manual/en/function.error-log.php){: new_window}.
  * Para aplicativos Python, consulte [Instruções de criação de log ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://docs.python.org/2/howto/logging.html){: new_window}.
  * Para aplicativos Ruby on Rails, consulte [O criador de log ![Ícone de link externo](../icons/launch-glyph.svg "Icone de link externo")](http://guides.rubyonrails.org/debugging_rails_applications.html#the-logger){: new_window}.
  * Para aplicativos Ruby Sinatra, consulte [Criação de log ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://www.sinatrarb.com/intro.html#Logging){: new_window}.

Quando você insere `cf logs appname --recent` na interface da linha de comandos do Cloud Foundry, somente os logs mais recentes são exibidos. Para visualizar os logs com relação a erros que ocorreram anteriormente, deve-se recuperar todos os logs e procurar pelos erros. Para recuperar todos os logs do seu aplicativo, use um dos métodos a seguir:
<dl>
<dt><strong>{{site.data.keyword.loganalysisshort}}</strong></dt>
<dd>Os recursos de procura e análise de arquivo de log integrado do serviço do {{site.data.keyword.loganalysisshort}} podem ajudá-lo a identificar erros com rapidez. Para obter mais informações, consulte <a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">{{site.data.keyword.loganalysisfull}}</a>.</dd>
<dt><strong>Ferramentas de terceiros </strong></dt>
<dd>É possível coletar e exportar os logs do seu aplicativo para um host de log externo. Para obter mais informações, consulte <a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">Configurando a criação de log externa</a>.</dd>
<dt><strong>Scripts para coletar e exportar os logs  </strong></dt>
<dd>Para usar um script para coletar e exportar automaticamente os logs para um arquivo externo, deve-se conectar ao console do {{site.data.keyword.Bluemix_notm}} de seu computador e deve-se ter espaço suficiente no computador para fazer download dos logs. Para obter mais informações, consulte <a href="/docs/get-support/quicktickresp.html#collecting-diagnostic-information" target="_blank">Coletando informações de diagnóstico</a>. </dd>
</dl>

Os arquivos `stdout.log` e `stderr.log` eram anteriormente acessíveis, por padrão, por meio da visualização do aplicativo no console do {{site.data.keyword.Bluemix_notm}} em **Arquivos** > **logs**. No entanto, a criação de log desse aplicativo não está mais disponível na versão atual do Cloud Foundry, em que o {{site.data.keyword.Bluemix_notm}} está hospedado. Para manter criação de log de aplicativo de saída padrão e erro padrão acessíveis por meio do console do {{site.data.keyword.Bluemix_notm}} em **Arquivos** > **logs**, é possível redirecionar a criação de log para outros arquivos no sistema de arquivos {{site.data.keyword.Bluemix_notm}}, dependendo do tempo de execução que você está usando.

  * Para aplicativos Liberty for Java, a saída direcionada para saída padrão e erro padrão já está contida no arquivo `messages.log` no diretório de logs. Procure entradas com os prefixos SystemOut e SystemErr.
  * Para aplicativos Node.js, é possível substituir a função console.log para gravar explicitamente em um arquivo no diretório de logs.
  * Para aplicativos PHP, é possível fazer a função error_log gravar em um arquivo no diretório de logs.
  * Para aplicativos Python, é possível fazer o criador de logs gravar em um arquivo no diretório de logs: `logging.basicConfig(filename='/docs/logs/example.log',level=logging.DEBUG)`
  * Para aplicativos Ruby, é possível fazer o criador de logs gravar em um arquivo no diretório de logs.


### Depurando mudanças de código
{: #debug_code_changes}

Se você estiver fazendo mudanças de código para um aplicativo que já está implementado e funcionando, mas as alterações de código não estiverem sendo refletidas no {{site.data.keyword.Bluemix_notm}}, será possível depurar usando os logs. Se o seu aplicativo estiver em execução ou não, é possível verificar os logs que são gerados durante a implementação ou o tempo de execução do aplicativo para depurar por que o novo código não está funcionando.

Dependendo da forma como o novo código é implementado, escolha um dos métodos a seguir para depurar as mudanças de código:

  * Para o novo código que é implementado a partir da linha de comandos cf, verifique a saída do comando *cf push*. Além disso, é possível usar o comando *cf logs* para localizar mais pistas para resolver o problema. Para obter mais informações sobre como usar o comando *cf logs*, consulte [visualizando logs a partir da interface da linha de comandos](/docs/services/CloudLogAnalysis/manage_logs.html#manage_logs).

  * Para o novo código que é implementado a partir de uma GUI, como o console do {{site.data.keyword.Bluemix_notm}}, o DevOps Delivery Pipeline ou o Travis-CI, é possível verificar os logs a partir da interface. Por exemplo, se você implementar o novo código do console do {{site.data.keyword.Bluemix_notm}}, será possível ir para Painel, localizar o seu aplicativo e, em seguida, visualizar os logs para obter pistas.   Para obter mais informações sobre como visualizar logs por meio do console do {{site.data.keyword.Bluemix_notm}}, consulte [Visualizando logs por meio do painel do {{site.data.keyword.Bluemix}}](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana).
