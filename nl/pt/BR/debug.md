---

copyright:
  years: 2015, 2018
lastupdated: "2018-01-17"

---



{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}


# Depurando
{: #debugging}

Se você tiver problemas com o {{site.data.keyword.Bluemix}}, será possível visualizar os arquivos de log para investigar os problemas e depurar os erros.
{:shortdesc}

Os logs fornecem informações, tais como se uma tarefa é executada com sucesso ou se ela falha. Eles também fornecem informações relevantes que podem ser usadas para depurar e determinar a causa de um problema.

Os logs estão em um formato fixo. Para logs detalhados, é possível filtrar os logs ou usar os hosts de criação de log externa para armazenar e processar os logs. Para obter mais informações sobre formatos de log, visualização e filtragem de logs e configuração de criação de log externa, consulte [Criação de log para aplicativos em execução no Cloud Foundry ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/monitor_log/logging.html#logging){: new_window}.


## Depurando erros de preparação
{: #debugging-staging-errors}
Você poderá ter problemas ao preparar seus aplicativos no {{site.data.keyword.Bluemix_notm}}. Se o seu aplicativo falhar na preparação, será possível procurar e revisar os logs de preparação (STG)
para determinar o que aconteceu durante a implementação do aplicativo e recuperar-se do problema. Para obter mais informações sobre os métodos de visualização de logs para aplicativos {{site.data.keyword.Bluemix}}, consulte [Visualizando logs ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana){: new_window}.  

Para entender por que o seu aplicativo pode estar falhando no {{site.data.keyword.Bluemix_notm}}, é necessário saber como um aplicativo é implementado no
{{site.data.keyword.Bluemix_notm}} e executado nele. Para obter informações detalhadas, consulte [Implementação do aplicativo ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/cfapps/depapps.html#appdeploy){: new_window}.


O procedimento a seguir mostra como você pode usar o comando `cf logs` para depurar os erros de preparação. Antes de executar as etapas a seguir, assegure-se de que tenha instalado a interface de linha de comandos cf. Para obter mais informações sobre como instalar a interface da linha de comandos cf, consulte [Instalando a interface da linha de comandos cf ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](/docs/starters/install_cli.html){: new_window}.

  1. Conecte-se ao {{site.data.keyword.Bluemix_notm}} inserindo o código a seguir na interface de linha de comandos:
     ```
	 cf api https://api.stage1.ng.bluemix.net
	 ```

  2. Efetue login no {{site.data.keyword.Bluemix_notm}} inserindo `cf login`.

  3. Recupere os logs recentes inserindo `cf logs appname --recent`. Se desejar filtrar um log detalhado, use a opção `grep`. Por exemplo, é possível inserir o código a seguir para exibir somente os logs [STG] :
    ```
	cf logs appname --recent | grep '\[STG\]'
	```
  4. Visualize o primeiro erro exibido no log.

Se você usar o plug-in do IBM Eclipse tools for {{site.data.keyword.Bluemix_notm}} para implementar aplicativos, na guia **Console** da ferramenta Eclipse, será possível ver os logs semelhantes à saída cf logs. Também é possível abrir uma janela Eclipse separada para controlar `os logs` ao implementar o aplicativo.

Além do comando `cf logs`, no {{site.data.keyword.Bluemix_notm}} também é possível usar o serviço Monitoring and Analytics para coletar os detalhes do log. Além disso, o serviço Monitoring and Analytics monitora o desempenho, o funcionamento e a disponibilidade de seus aplicativos. Ele também fornece análise de log para aplicativos de tempo de execução Node.js e Liberty.  

### Depurando erros de preparação para um aplicativo Node.js

O exemplo a seguir mostra um log exibido após a inserção de `cf logs appname --recent`. O exemplo assume que os erros de preparação ocorreram para o aplicativo Node.js:
```
2014-08-11T14:19:36.17+0100 [API] OUT Atualizado o app com guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({name"=>"SampleExpressApp"}
2014-08-11T14:20:44.17+0100 [API] OUT Atualizado o app com guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STOPPED"})
2014-08-11T14:20:44.19+0100 [App/0] ERR
2014-08-11T14:20:44.43+0100 [DEA] OUT Parando a instância de app (índice 0) com guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:44.44+0100 [DEA] OUT Interrompida a instância de app (índice 0) com guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:48.97+0100 [DEA] OUT Obtida a solicitação de preparação para o app com id 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:50.94+0100 [API] OUT Atualizado o app com guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STARTED"})
2014-08-11T14:20:51.66+0100 [STG] OUT -----> Fazer download do pacote de app (4,1 M)
2014-08-11T14:20:51.90+0100 [STG] OUT -----> Fazer download do cache de buildpack do app (1,1 M)
2014-08-11T14:20:52.78+0100 [STG] OUT -----> Versão do buildpack: v1.1-20140717-1447
2014-08-11T14:20:52.78+0100 [STG] ERR Erro de análise: Esperado outro par de valores de chave na linha 18, coluna 3
2014-08-11T14:20:52.79+0100 [STG] OUT 0 informações de que funcionou se terminar com ok
```
{: screen}


O primeiro erro no log mostra o motivo de falha da preparação. No exemplo, o primeiro erro é uma saída do componente DEA durante a fase de preparação.
```
2014-08-11T14:20:52.78+0100 [STG]   ERR parse error: expected another key-value pair at line 18, column 3
```
{: screen}


Para um aplicativo Node.js, o DEA usa as informações no arquivo `package.json` para fazer download dos módulos. A partir deste erro, é possível ver
que o erro ocorre para o módulo. Portanto, talvez seja necessário revisar a 18ª linha do arquivo `package.json`.

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*",
18   }
```
{: screen}


É possível ver que uma vírgula foi colocada no final da linha 17, portanto, espera-se um par chave-valor na linha 18. Para corrigir o problema, remova a vírgula:

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*"
18   }
```
{: screen}


## Depurando erros de tempo de execução
{: #debugging-runtime-errors}
Se você tiver problemas com seu aplicativo no tempo de execução, os logs do aplicativo poderão ajudar a identificar a causa do erro e recuperar-se desse problema.

Especificamente, a criação de log para saída padrão e erro padrão pode ser ativada. Para obter mais informações sobre como configurar os arquivos de log para aplicativos que são implementados usando os buildpacks integrados do {{site.data.keyword.Bluemix_notm}}, consulte a lista a seguir:

  * Para aplicativos Liberty for Java™, veja [Perfil Liberty: Criação de log e rastreio ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://www-01.ibm.com/support/knowledgecenter/was_beta_liberty/com.ibm.websphere.wlp.nd.multiplatform.doc/ae/rwlp_logging.html){: new_window}.
  * Para aplicativos Node.js, veja [Como registrar no node.js ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://docs.nodejitsu.com/articles/intermediate/how-to-log){: new_window}.
  * Para aplicativos PHP, veja [error_log ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://php.net/manual/en/function.error-log.php){: new_window}.
  * Para aplicativos Python, veja [Registrando HOWTO ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](https://docs.python.org/2/howto/logging.html){: new_window}.
  * Para aplicativos Ruby on Rails, veja [O criador de logs ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://guides.rubyonrails.org/debugging_rails_applications.html#the-logger){: new_window}.
  * Para aplicativos Ruby Sinatra, veja [Registrando ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](http://www.sinatrarb.com/intro.html#Logging){: new_window}.

Ao inserir `cf logs appname --recent` na interface da linha de comandos cf, somente os logs mais recentes são exibidos. Para visualizar os logs com relação a erros que ocorreram anteriormente, deve-se recuperar todos os logs e procurar pelos erros. Para recuperar todos os logs do seu aplicativo, use um dos métodos a seguir:
<dl>
<dt><strong>Serviço Monitoring and Analytics do {{site.data.keyword.Bluemix_notm}}</strong></dt>
<dd>A procura de arquivos de log integrados e os recursos de análise do serviço Monitoring and Analytics pode ajudá-lo a identificar erros com rapidez. Para obter mais informações, consulte <a href="../services/monana/index.html#gettingstartedtemplate" target="_blank">Monitoring and
Analytics</a>.</dd>
<dt><strong>Ferramentas de terceiros </strong></dt>
<dd>É possível coletar e exportar os logs do seu aplicativo para um host de log externo. Para obter mais informações, consulte <a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">Configurando a criação de log externa</a>.</dd>
<dt><strong>Scripts para coletar e exportar os logs  </strong></dt>
<dd>Para usar um script para coletar e exportar os logs automaticamente para um arquivo externo, deve-se conectar ao console do {{site.data.keyword.Bluemix_notm}} por meio do computador e ter espaço suficiente no computador para fazer download dos logs. Para obter mais informações, consulte <a href="/docs/get-support/quicktickresp.html#collecting-diagnostic-information" target="_blank">Coletando informações de diagnóstico</a>. </dd>
</dl>

Os arquivos `stdout.log` e `stderr.log` eram acessíveis anteriormente, por padrão, por meio da visualização do aplicativo no console do {{site.data.keyword.Bluemix_notm}} em **Arquivos** > **logs**. No entanto, a criação de log desse aplicativo não está mais disponível na versão atual do Cloud Foundry, em que o {{site.data.keyword.Bluemix_notm}} está hospedado. Para manter a criação de log do aplicativo de saída padrão e erro padrão acessível por meio do console do {{site.data.keyword.Bluemix_notm}} em **Arquivos** > **logs**, será possível redirecionar a criação de log para outros arquivos no sistema de arquivos {{site.data.keyword.Bluemix_notm}}, dependendo do tempo de execução que estiver sendo usado.

  * Para aplicativos Liberty for Java, a saída direcionada para saída padrão e erro padrão já está contida no arquivo `messages.log` no diretório de logs. Consulte as entradas prefixadas com SystemOut e SystemErr, respectivamente.
  * Para aplicativos Node.js, é possível substituir a função console.log para gravar explicitamente em um arquivo no diretório de logs.
  * Para aplicativos PHP, é possível usar a função error_log para gravar em um arquivo no diretório de logs.
  * Para aplicativos Python, o criador de logs pode gravar em um arquivo no diretório de logs: `logging.basicConfig(filename='/docs/logs/example.log',level=logging.DEBUG)`
  * Para aplicativos Ruby, o criador de logs pode gravar em um arquivo no diretório de logs.


### Depurando mudanças de código
{: #debug_code_changes}

Se você estiver fazendo mudanças de código em um app que já está implementado e funcionando, as mudanças de código ainda não estarão sendo refletidas no {{site.data.keyword.Bluemix_notm}}; será possível depurar usando os logs. Se o seu aplicativo estiver em execução ou não, é possível verificar os logs que são gerados durante a implementação ou o tempo de execução do aplicativo para depurar por que o novo código não está funcionando.

Dependendo da forma como o novo código é implementado, escolha um dos métodos a seguir para depurar as mudanças de código:

  * Para novo código implementado da linha de comandos cf, verifique a saída do comando *cf push*. Além disso, é possível usar o comando *cf logs* para localizar mais pistas para resolver o problema. Para obter mais informações sobre como usar o comando *cf logs*, consulte [visualizando logs da interface da linha de comandos](/docs/services/CloudLogAnalysis/manage_logs.html#manage_logs).

  * Para novo código implementado de uma GUI, como o console do {{site.data.keyword.Bluemix_notm}}, o DevOps Delivery Pipeline ou o Travis-CI, é possível verificar os logs da interface. Por exemplo, se você implementar o novo código do console do {{site.data.keyword.Bluemix_notm}}, será possível ir para Painel, localizar o seu aplicativo e, em seguida, visualizar os logs para obter pistas.   Para obter mais informações sobre como visualizar logs do console do {{site.data.keyword.Bluemix_notm}}, consulte [Visualizando logs do Painel do {{site.data.keyword.Bluemix}}](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana).  


