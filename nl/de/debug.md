---

copyright:
  years: 2015, 2018
lastupdated: "2018-05-29"

---



{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}


# Fehlerbehebung
{: #debugging}

Wenn Probleme mit {{site.data.keyword.Bluemix}} auftreten, können Sie die Protokolldateien anzeigen, um die Probleme zu untersuchen und die Fehler zu beheben.
{:shortdesc}

In Protokollen sind z. B. Informationen darüber enthalten, ob ein Job erfolgreich ausgeführt wird oder ob er fehlschlägt. Sie enthalten auch relevante Informationen, die für Debugzwecke und zum Feststellen der Ursache eines Problems verwendet werden können.

Protokolle haben ein festes Format. Bei ausführlichen Protokollen ist eine Filterung möglich; Sie können auch externe Protokollierungshosts zum Speichern und Verarbeiten der Protokolle verwenden. Weitere Informationen zu Protokollformaten, zum Anzeigen und Filtern von Protokollen sowie zur Konfiguration einer externen Protokollierung finden Sie im Abschnitt zur [Protokollierung für Apps, die in Cloud Foundry ausgeführt werden ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](/docs/monitor_log/logging.html#logging){: new_window}.


## Staging-Fehler beheben
{: #debugging-staging-errors}
Beim Durchführen des Stagings für die Anwendungen unter Verwendung von {{site.data.keyword.Bluemix_notm}} können Fehler auftreten. Wenn die Durchführung des Stagings für eine App fehlschlägt, können Sie die STG-Protokolle durchsuchen und prüfen, um den während der Bereitstellung der App aufgetretenen Fehler zu ermitteln und das Problem zu beheben. Weitere Informationen zum Anzeigen von Protokollen für {{site.data.keyword.Bluemix}}-Apps finden Sie unter [Protokolle anzeigen ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana){: new_window}.  

Um zu verstehen, warum in einer App unter {{site.data.keyword.Bluemix_notm}} ein Fehler auftritt, müssen Sie wissen, wie eine App unter {{site.data.keyword.Bluemix_notm}} bereitgestellt und ausgeführt wird. Detaillierte Informationen hierzu finden Sie in [Anwendungsbereitstellung ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](/docs/cfapps/depapps.html#appdeploy){: new_window}.


Anhand der folgenden Prozedur wird veranschaulicht, wie Sie mit dem Befehl `cf logs` Staging-Fehler beheben können. Stellen Sie vor der Ausführung der folgenden Schritte sicher, dass Sie die Befehlszeilenschnittstelle 'cf' installiert haben. Weitere Informationen zum Installieren der Befehlszeilenschnittstelle 'cf' finden Sie unter [Befehlszeilenschnittstelle 'cf' installieren ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](/docs/starters/install_cli.html){: new_window}.

  1. Stellen Sie durch Eingeben des folgenden Codes in der Befehlszeilenschnittstelle 'cf' eine Verbindung zu {{site.data.keyword.Bluemix_notm}} her:
     ```
	 cf api https://api.stage1.ng.bluemix.net
	 ```

  2. Melden Sie sich bei {{site.data.keyword.Bluemix_notm}} durch Eingabe von `cf login` an.

  3. Rufen Sie die neuesten Protokolle durch Eingabe von `cf logs appname --recent` ab. Wenn Sie ein ausführliches Protokoll filtern möchten, verwenden Sie die Option `grep`. Sie können zum Beispiel den folgenden Code eingeben, um nur Protokolle des Typs [STG] anzuzeigen:
    ```
	cf logs appname --recent | grep '\[STG\]'
	```
  4. Zeigen Sie den ersten Fehler an, der im Protokoll aufgeführt ist.

Wenn Sie das IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}-Plug-in zum Bereitstellen von Anwendungen verwenden, werden in der Registerkarte **Console** des Eclipse-Tools Protokolle angezeigt, die der Ausgabe des Befehls 'cf logs' ähneln. Sie können auch ein separates Eclipse-Fenster zum Verfolgen der `Protokolle` öffnen, wenn Sie die Anwendung bereitstellen.

Zusätzlich zum Befehl `cf logs` können Sie in {{site.data.keyword.Bluemix_notm}} auch den {{site.data.keyword.loganalysisshort}}-Service zum Erfassen der Protokolldetails verwenden. 

### Staging-Fehler für eine Node.js-Anwendung beheben

Im folgenden Beispiel wird ein Protokoll dargestellt, das nach Eingabe des Befehls `cf logs appname --recent` angezeigt wird. In dem Beispiel wird davon ausgegangen, dass für eine Node.js-Anwendung Staging-Fehler aufgetreten sind:
```
2014-08-11T14:19:36.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({name"=>"SampleExpressApp"}
2014-08-11T14:20:44.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STOPPED"})
2014-08-11T14:20:44.19+0100 [App/0]   ERR
2014-08-11T14:20:44.43+0100 [DEA]     OUT Stopping app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:44.44+0100 [DEA]     OUT Stopped app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:48.97+0100 [DEA]     OUT Got staging request for app with id 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:50.94+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STARTED"})
2014-08-11T14:20:51.66+0100 [STG]     OUT -----> Download app package (4.1M)
2014-08-11T14:20:51.90+0100 [STG]     OUT -----> Download app buildpack cache (1.1M)
2014-08-11T14:20:52.78+0100 [STG]     OUT -----> Buildpack Version: v1.1-20140717-1447
2014-08-11T14:20:52.78+0100 [STG]     ERR parse error: Expected another key-value pair at line 18, column 3
2014-08-11T14:20:52.79+0100 [STG]     OUT 0 info it worked if it ends with ok
```
{: screen}


Aus dem ersten Fehler im Protokoll geht hervor, warum das Staging fehlgeschlagen ist. Im Beispiel wird der erste Fehler durch eine Ausgabe der Komponente 'Droplet Execution Agent' (DEA) während der Staging-Phase verursacht.
```
2014-08-11T14:20:52.78+0100 [STG]   ERR parse error: expected another key-value pair at line 18, column 3
```
{: screen}


Bei einer Node.js-Anwendung werden die Informationen in der Datei `package.json` von der Komponente DEA zum Herunterladen der Module verwendet. Aus diesem Fehler lässt sich erkennen, dass der Fehler für das Modul aufgetreten ist. Somit ist es sinnvoll, den Inhalt der 18. Zeile in der Datei `package.json` zu überprüfen.

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*",
18   }
```
{: screen}


Da Zeile 17 mit einem Komma endet, wird in Zeile 18 ein Schlüssel/Wert-Paar erwartet. Entfernen Sie zum Beheben des Problems das Komma:

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*"
18   }
```
{: screen}


## Laufzeitfehler beheben
{: #debugging-runtime-errors}
Wenn während der Laufzeit der Anwendung Probleme auftreten, können Anwendungsprotokolle bei der Ermittlung der Fehlerursache und der Behebung des Problems hilfreich sein.

Insbesondere die Protokollierung der Standardausgabe (stdout) und Standardfehler (stderr) kann aktiviert sein. Weitere Informationen zum Konfigurieren der Protokolldateien für Anwendungen, die mit den integrierten {{site.data.keyword.Bluemix_notm}}-Buildpacks bereitgestellt wurden, finden Sie in der folgenden Liste:

  * Informationen zu Liberty for Java™-Anwendungen finden Sie in [Liberty: Protokollierung und Traceerstellung ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/support/knowledgecenter/en/SSEQTP_liberty/com.ibm.websphere.wlp.doc/ae/rwlp_logging.html){: new_window}.
  * Beachten Sie bei Node.js-Anwendungen die Informationen in [Node.js debugging starts with better logging! ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/blogs/bluemix/2015/03/node-js-better-logging/){: new_window}.
  * Beachten Sie für PHP-Anwendungen die Informationen in [error_log ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://php.net/manual/en/function.error-log.php){: new_window}.
  * Beachten Sie für Python-Anwendungen die Informationen in [Logging HOWTO ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](https://docs.python.org/2/howto/logging.html){: new_window}.
  * Beachten Sie für zu Ruby on Rails-Anwendungen die Informationen im Abschnitt [The Logger ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://guides.rubyonrails.org/debugging_rails_applications.html#the-logger){: new_window}.
  * Beachten Sie für Ruby Sinatra-Anwendungen die Informationen in [Logging ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")](http://www.sinatrarb.com/intro.html#Logging){: new_window}.

Wenn Sie `cf logs appname --recent` in die Befehlszeilenschnittstelle 'cf' eingeben, werden nur die neuesten Protokolle angezeigt. Wenn Sie Protokolle für Fehler anzeigen möchten, die früher aufgetreten sind, müssen Sie alle Protokolle abrufen und in ihnen nach den Fehlern suchen. Verwenden Sie zum Abrufen aller Protokolle für Ihre Anwendung eine der folgenden Methoden:
<dl>
<dt><strong>{{site.data.keyword.loganalysisshort}}</strong></dt>
<dd>Die Funktionen für die integrierte Protokolldateisuche und -analyse des {{site.data.keyword.loganalysisshort}}-Service können Ihnen dabei helfen, Fehler schnell zu finden. Weitere Informationen finden Sie unter <a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">{{site.data.keyword.loganalysisfull}}</a>.</dd>
<dt><strong>Tools von Drittanbietern</strong></dt>
<dd>Sie können die Protokolle aus Ihrer Anwendung erfassen und in einen externen Protokollhost exportieren. Weitere Informationen finden Sie unter <a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">Externe Protokollierung konfigurieren</a>.</dd>
<dt><strong>Scripts zum Erfassen und Exportieren der Protokolle</strong></dt>
<dd>Wenn Sie ein Script verwenden möchten, um die Protokolle automatisch zu erfassen und in eine externe Datei zu exportieren, müssen Sie von Ihrem Computer eine Verbindung zur {{site.data.keyword.Bluemix_notm}}-Konsole herstellen und auf Ihrem Computer muss ausreichend Speicherplatz zum Herunterladen der Protokolle vorhanden sein. Weitere Informationen hierzu finden Sie unter <a href="/docs/get-support/quicktickresp.html#collecting-diagnostic-information" target="_blank">Diagnoseinformationen erfassen</a>. </dd>
</dl>

Auf die Dateien `stdout.log` und `stderr.log` konnte früher standardmäßig in der {{site.data.keyword.Bluemix_notm}}-Konsole über die Anwendungssicht unter **Dateien** > **Protokolle** zugegriffen werden. Diese Anwendungsprotokollierung ist jedoch mit der aktuellen Version von Cloud Foundry nicht mehr verfügbar, von der {{site.data.keyword.Bluemix_notm}} per Hosting bereitgestellt wird. Wenn Sie weiterhin über die {{site.data.keyword.Bluemix_notm}}-Konsole unter **Dateien** > **Protokolle** mit 'stdout' und 'stderr' auf die Anwendungsprotokollierung zugreifen möchten, können Sie die Protokollierung abhängig von der jeweils verwendeten Laufzeit in andere Dateien im {{site.data.keyword.Bluemix_notm}}-Dateisystem umleiten.

  * Bei Liberty for Java-Anwendungen ist die an 'stdout' und 'stderr' übertragene Ausgabe bereits in der Datei `messages.log` im Protokollverzeichnis enthalten. Suchen Sie nach Einträgen mit dem Präfix 'SystemOut' bzw. 'SystemErr'.
  * Bei Node.js-Anwendungen können Sie die 'console.log'-Funktion überschreiben, damit explizit in eine Datei im Protokollverzeichnis geschrieben wird.
  * Bei PHP-Anwendungen können Sie die Funktion 'error_log' verwenden, um in eine Datei im Protokollverzeichnis zu schreiben.
  * Bei Python-Anwendungen können Sie konfigurieren, dass von der Protokollfunktion in eine Datei im Protokollverzeichnis geschrieben wird: `logging.basicConfig(filename='/docs/logs/example.log',level=logging.DEBUG)`
  * Bei Ruby-Anwendungen können Sie konfigurieren, dass von der Protokollfunktion in eine Datei im Protokollverzeichnis geschrieben wird.


### Debugging von Codeänderungen
{: #debug_code_changes}

Wenn Sie Codeänderungen an einer App vornehmen, die schon bereitgestellt wurde und aktiv ist, und Ihre Codeänderungen nicht in {{site.data.keyword.Bluemix_notm}} übernommen werden, können Sie mithilfe der Protokolle ein Debugging durchführen. Unabhängig davon, ob die App aktiv ist, können Sie die Protokolle prüfen, die während der Bereitstellung oder Laufzeit der App generiert wurden, um festzustellen, warum der neue Code nicht funktioniert.

Je nachdem, wie der neue Code bereitgestellt wurde, können Sie für das Debugging der Codeänderungen eine der folgenden Methoden verwenden:

  * Wenn der neue Code über die Befehlszeilenschnittstelle 'cf' bereitgestellt wurde, überprüfen Sie die Ausgabe des Befehls *cf push*. Darüber hinaus können Sie mit dem Befehl *cf push* weitere Hinweise zur Lösung des Problems erhalten. Weitere Informationen zur Verwendung des Befehls *cf logs* finden Sie in [Protokolle über die Befehlszeilenschnittstelle anzeigen](/docs/services/CloudLogAnalysis/manage_logs.html#manage_logs).

  * Wenn der neue Code über eine GUI wie z. B. die {{site.data.keyword.Bluemix_notm}}-Konsole, DevOps Delivery Pipeline oder Travis-CI bereitgestellt wird, können Sie die Protokolle über die Schnittstelle überprüfen. Wenn der neue Code beispielsweise über die {{site.data.keyword.Bluemix_notm}}-Konsole bereitgestellt wird, können Sie zum Dashboard wechseln, Ihre App suchen und die Protokolle auf Suchhinweisbegriffe überprüfen.   Weitere Informationen zum Anzeigen von Protokollen über die {{site.data.keyword.Bluemix_notm}}-Konsole finden Sie in [Protokolle über das {{site.data.keyword.Bluemix}}-Dashboard anzeigen](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana).
