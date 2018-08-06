---



copyright:

  years: 2015，2017

lastupdated: "2018-05-24"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:prereq: .prereq}
{:download: .download}
{:pre: .pre}
{:app_name: data-hd-keyref="app_name"}
{:app_key: data-hd-keyref="app_key"}
{:app_secret: data-hd-keyref="app_secret"}
{:app_url: data-hd-keyref="app_url"}
{:host: data-hd-keyref="host"}
{:org_name: data-hd-keyref="org_name"}
{:route: data-hd-keyref="route"}
{:space_name: data-hd-keyref="space_name"}
{:service_name: data-hd-keyref="service_name"}
{:service_instance_name: data-hd-keyref="service_instance_name"}
{:user_ID: data-hd-keyref="user_ID"}
{:tip: .tip}

# Cloud Foundry-App über die Befehlszeilenschnittstelle herunterladen, ändern und erneut bereitstellen

Verwenden Sie die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle, um Ihre Cloud Foundry-Anwendungen und -Serviceinstanzen herunterzuladen, zu ändern und erneut bereitzustellen.
{:shortdesc}

Laden Sie zuerst die [Befehlszeilenschnittstelle](/docs/cli/index.html#overview){: new_window} ![Symbol für externen Link](../../../icons/launch-glyph.svg) von {{site.data.keyword.Bluemix_notm}} herunter und installieren Sie sie.


**Einschränkung:** Das Befehlszeilentool wird von Cygwin nicht unterstützt. Verwenden Sie das Tool in einem anderen Befehlszeilenfenster als dem Cygwin-Befehlszeilenfenster.
{:prereq}

Nach der Installation der Befehlszeilenschnittstelle können Sie beginnen:

  1. {: download} Laden Sie den Code für Ihre App in ein neues Verzeichnis herunter, um Ihre Entwicklungsumgebung einzurichten.

    <a class="xref" href="http://bluemix.net" target="_blank" title="(Wird in einer neuen Registerkarte oder in einem neuen Fenster geöffnet)"><img class="image" src="images/btn_starter-code.svg" alt="Anwendungscode herunterladen" /> </a>

      **Hinweis**: Bevor Sie fortfahren, bringen Sie den Versionsstand des Knotens auf Version `8.9.x` oder auf die neueste Version in der Datei `package.json`.

  2. Wechseln Sie in das Verzeichnis, in dem sich Ihr Code befindet.

  <pre class="pre"><code class="hljs">cd <var class="keyword varname">neues_Verzeichnis</var></code></pre>

  3.  Nehmen Sie die gewünschten Änderungen an Ihrem App-Code vor. Beispiel: Wenn Sie eine {{site.data.keyword.Bluemix}}-Beispielanwendung verwenden und Ihre App die Datei `src/main/webapp/index.html` enthält, können Sie sie ändern und den Dankestext für die Erstellung in einen anderen Text ändern. Stellen Sie sicher, dass sich die App lokal ausführen lässt, bevor sie wieder in {{site.data.keyword.Bluemix_notm}} bereitgestellt wird.

    Beachten Sie die Datei `manifest.yml`. Wenn Ihre App wieder in {{site.data.keyword.Bluemix_notm}} bereitgestellt wird, dient diese Datei zum Ermitteln der URL, der Speicherzuordnung, der Anzahl von Instanzen und anderer wichtiger Parameter für Ihre Anwendung. Sie können in der Cloud Foundry-Dokumentation [mehr über die Manifestdatei lesen](https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html){: new_window}.

    Beachten Sie auch die Datei `README.md`, die gegebenenfalls Informationen wie Erstellungsanweisungen enthält.

    Hinweis: Wenn es sich bei Ihrer Anwendung um eine Liberty-App handelt, müssen Sie sie vor der erneuten Bereitstellung erstellen.

  4. Stellen Sie eine Verbindung zu {{site.data.keyword.Bluemix_notm}} her und melden Sie sich an.

  <pre class="pre"><code class="hljs">bluemix api https://api.<span class="keyword" data-hd-keyref="DomainName">Domänenname</span></code></pre>

  <pre class="pre"><code class="hljs">bluemix login -u <var class="keyword varname" data-hd-keyref="user_ID">Benutzername</var> -o <var class="keyword varname" data-hd-keyref="org_name">Organisationsname</var> -s <var class="keyword varname" data-hd-keyref="space_name">Bereichsname</var></code></pre>

  Wenn Sie eine eingebundene ID nutzen, verwenden Sie die Option `-sso`.

  <pre class="pre"><code class="hljs">bluemix login  -o <var class="keyword varname" data-hd-keyref="org_name">Organisationsname</var> -s <var class="keyword varname" data-hd-keyref="space_name">Bereichsname</var> -sso</code></pre>

  **Hinweis**: Wenn der Wert ein Leerzeichen enthält, müssen `username`, `org_name` und `space_name` in einfache oder doppelte Anführungszeichen eingeschlossen werden. Beispiel: `-o "my org"`.

  5. Führen Sie unter <var class="keyword varname">neues_Verzeichnis</var> mit dem Befehl `bluemix app push` ein erneutes Staging Ihrer App in {{site.data.keyword.Bluemix_notm}} durch. Weitere Informationen zum Befehl `bx app push` finden Sie unter [Anwendung hochladen](/docs/starters/upload_app.html).

  <pre class="pre"><code class="hljs">bluemix app push <var class="keyword varname" data-hd-keyref="app_name">App-Name</var></code></pre>

  6. Greifen Sie auf Ihre App zu, indem Sie zu https://<var class="keyword varname" data-hd-keyref="app_url">App-URL</var>.<span class="keyword" data-hd-keyref="APPDomain">App-Domänenname</span> navigieren.
