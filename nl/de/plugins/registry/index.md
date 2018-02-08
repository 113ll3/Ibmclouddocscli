---



copyright:

  years: 2017

lastupdated: "2017-12-08"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.registrylong_notm}}-Befehlszeilenschnittstelle (CLI)
{: #containerregcli}

Die {{site.data.keyword.registrylong}}-Befehlszeilenschnittstelle (CLI) ist ein Plug-in für die Verwaltung der Registry und deren Ressourcen für Ihr {{site.data.keyword.Bluemix_notm}}-Konto.
{: shortdesc}

**Voraussetzungen**
* Melden Sie sich vor der Ausführung von Registry-Befehlen bei {{site.data.keyword.Bluemix_notm}} mit dem Befehl `bx login` an, um ein Zugriffstoken zu generieren und Ihre Sitzung zu authentifizieren.

Informationen zur Verwendung der {{site.data.keyword.registrylong_notm}}-CLI finden Sie in der [Einführung zu {{site.data.keyword.registrylong_notm}}](../../../services/Registry/index.html).

<table summary="{{site.data.keyword.registrylong_notm}} verwalten">
<caption>Tabelle 1. Befehle zur Verwaltung von {{site.data.keyword.registrylong_notm}}
</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung der Registry</th>
 </thead>
 <tbody>
 <tr>
 <td>[bx cr api](#bx_cr_api)</td>
 <td>[bx cr build](#bx_cr_build)</td>
 <td>[bx cr info](#bx_cr_info)</td>
 <td>[bx cr image-inspect](#bx_cr_image_inspect)</td>
 <td>[bx cr image-list (bx cr images)](#bx_cr_image_list)</td>
 </tr>
 <tr>
 <td>[bx cr image-rm](#bx_cr_image_rm)</td>
 <td>[bx cr login](#bx_cr_login)</td>
 <td>[bx cr namespace-add](#bx_cr_namespace_add)</td>
 <td>[bx cr namespace-list (bx cr namespaces)](#bx_cr_namespace_list)</td>
 <td>[bx cr namespace-rm](#bx_cr_namespace_rm)</td>
 </tr>
 <tr>
 <td>[bx cr plan](#bx_cr_plan)</td>
 <td>[bx cr plan-upgrade](#bx_cr_plan_upgrade)</td>
 <td>[bx cr quota](#bx_cr_quota)</td>
 <td>[bx cr quota-set](#bx_cr_quota_set)</td>
 <td>[bx cr region](#bx_cr_region)</td>
 </tr>
 <tr>
 <td>[bx cr region-set](#bx_cr_region_set)</td>
 <td>[bx cr token-add](#bx_cr_token_add)</td>
 <td>[bx cr token-get](#bx_cr_token_get)</td>
 <td>[bx cr token-list (bx cr tokens)](#bx_cr_token_list)</td>
 <td>[bx cr token-rm](#bx_cr_token_rm)</td>
 </tr><tr>
 <td>[bx cr vulnerability-assessment (bx cr va)](#bx_cr_va)</td>
 </tr>
 </tbody></table>



## bx cr api
{: #bx_cr_api}

Gibt die Details zu dem Registry-API-Endpunkt zurück, an dem die Befehle ausgeführt werden.

```
bx cr api
```
{: codeblock}


## bx cr build
{: #bx_cr_build}

Erstellt ein Docker-Image in {{site.data.keyword.registrylong_notm}}.

```
bx cr build [--no-cache] [--pull] [--quiet | -q] [--build-arg KEY=VALUE ...] [--file FILE | -f FILE] --tag TAG DIRECTORY
```
{: codeblock}

**Parameter**
<dl>
<dt>DIRECTORY</dt>
<dd>Die Position Ihres Buildkontextes, der Ihre Dockerfile und die vorausgesetzten Dateien enthält.</dd>
<dt>--no-cache</dt>
<dd>(Optional) Bei Angabe werden im Cache zwischengespeicherte Image-Layer aus vorherigen Builds in diesem Build nicht verwendet.</dd>
<dt>--pull</dt>
<dd>(Optional) Bei Angabe werden die Basisimages auch dann extrahiert, wenn ein Image mit einem übereinstimmenden Tag bereits auf dem Build-Host existiert.</dd>
<dt>--quiet, -q</dt>
<dd>(Optional) Bei Angabe wird die Buildausgabe unterdrückt, es sei denn, es tritt ein Fehler auf.</dd>
<dt> --build-arg KEY=VALUE</dt>
<dd>(Optional) Geben Sie ein zusätzliches Buildargument im Format 'KEY=VALUE' an. Mehrere Buildargumente können angegeben werden, indem Sie diesen Parameter mehrmals einschließen. Der Wert der einzelnen Buildargumente steht als Umgebungsvariable zur Verfügung, wenn Sie eine ARG-Zeile angeben, die mit dem Schlüssel in Ihrer Dockerfile übereinstimmt.</dd>
<dt>--file FILE, -f FILE</dt>
<dd>(Optional) Wenn Sie die gleichen Dateien für mehrere Builds verwenden, können Sie einen Pfad zu einer anderen Dockerfile auswählen. Geben Sie die Position der Dockerfile relativ zum Buildkontext an. Wenn keine Angabe gemacht wird, lautet der Standardwert `PATH/Dockerfile`, wobei PATH das Stammverzeichnis des Buildkontextes ist.</dd>
<dt>--tag TAG, -t TAG</dt>
<dd>Der vollständige Name für das Image, das erstellt werden soll. Dieser Name umfasst die Registry-URL und den Namensbereich.</dd>
</dl>


## bx cr info
{: #bx_cr_info}

Zeigt den Namen und das Konto der Registry an, bei der Sie angemeldet sind.

```
bx cr info
```
{: codeblock}


## bx cr image-inspect
{: #bx_cr_image_inspect}

Zeigt Details zu einem bestimmten Image an.

```
bx cr image-inspect [--format FORMAT] IMAGE [IMAGE...]
```
{: codeblock}

**Parameter**
<dl>
<dt>--format FORMAT</dt>
<dd>(Optional) Formatiert die Ausgabeelemente unter Verwendung einer Go-Vorlage. 

Weitere Informationen finden Sie unter [CLI-Ausgabe für {{site.data.keyword.registrylong_notm}}-Befehle formatieren und filtern](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
<dt>IMAGE</dt>
<dd>Der Name des Images, für das ein Bericht abgerufen werden soll. Sie können mehrere Images untersuchen, indem Sie die einzelnen Images in dem Befehl jeweils durch ein Leerzeichen getrennt auflisten.

<p>Eine Liste mit den Namen Ihrer Images können Sie mit dem Befehl `bx cr image-list` anzeigen. Kombinieren Sie den Inhalt der Spalten für Repository und Tag, um den Imagenamen im Format `repository:tag` zu erstellen. Ist im Imagenamen kein Tag angegeben, wird das Image mit dem Tag `latest` untersucht. </p> 

</dd>
</dl>


## bx cr image-list (bx cr images)
{: #bx_cr_image_list}

Zeigt alle Images in Ihrem {{site.data.keyword.Bluemix_notm}}-Konto an.

<p>**Hinweis:** Der Imagename stellt eine Kombination aus dem Inhalt der Spalten für Repository und Tag im Format `repository:tag` dar. </p> 

```
 bx cr image-list [--no-trunc] [--format FORMAT] [-q, --quiet] [--restrict RESTRICTION] [--include-ibm] 
```
{: codeblock}

**Parameter**
<dl>
<dt>--no-trunc</dt>
<dd>(Optional) Gibt an, die Imageauszüge nicht abzuschneiden.</dd>
<dt>--format FORMAT</dt>
<dd>(Optional) Formatiert die Ausgabeelemente unter Verwendung einer Go-Vorlage. 

Weitere Informationen finden Sie unter [CLI-Ausgabe für {{site.data.keyword.registrylong_notm}}-Befehle formatieren und filtern](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
<dt>-q, --quiet</dt>
<dd>(Optional) Die einzelnen Images werden in folgendem Format aufgelistet: `repository:tag`.</dd>
<dt>--restrict RESTRICTION</dt>
<dd>(Optional) Begrenzen Sie die Ausgabe, um lediglich Images in dem angegebenen Namensbereich bzw. in der Kombination aus Namensbereich und Repository anzuzeigen. </dd>
<dt>--include-ibm</dt>
<dd>(Optional) Schließt von {{site.data.keyword.IBM_notm}} bereitgestellte öffentliche Images in die Ausgabe ein. Ohne diese Option werden standardmäßig nur private Images aufgelistet.</dd>
</dl>



## bx cr image-rm
{: #bx_cr_image_rm}

Löscht ein oder mehrere angegebene Images aus Ihrer Registry.

```
bx cr image-rm IMAGE [IMAGE...]
```
{: codeblock}

**Parameter**
<dl>
<dt>IMAGE</dt>
<dd>Der Name des Images, für das ein Bericht abgerufen werden soll. Sie können mehrere Images gleichzeitig löschen, indem Sie die einzelnen Images in dem Befehl jeweils durch ein Leerzeichen getrennt auflisten.

<p>Eine Liste mit den Namen Ihrer Images können Sie mit dem Befehl `bx cr image-list` anzeigen. Kombinieren Sie den Inhalt der Spalten für Repository und Tag, um den Imagenamen im Format `repository:tag` zu erstellen. Wenn der Imagename ohne Tag angegeben wird, wird standardmäßig das Image mit dem Tag `latest` gelöscht.</p> 

</dd>
</dl>


## bx cr login
{: #bx_cr_login}

Führt den Befehl `docker login` für die Registry aus. Der Befehl `docker login` ist erforderlich, um die Befehle `docker push` und `docker pull` für die Registry ausführen zu können. Dieser Befehl ist nicht erforderlich, um andere `bx cr`-Befehle auszuführen. Wenn Docker nicht installiert ist, gibt dieser Befehl eine Fehlernachricht zurück.

```
bx cr login
```
{: codeblock}


## bx cr namespace-add
{: #bx_cr_namespace_add}

Fügt einen Namensbereich zu Ihrem {{site.data.keyword.Bluemix_notm}}-Konto hinzu.

```
bx cr namespace-add NAMESPACE
```
{: codeblock}

**Parameter**
<dl>
<dt>NAMESPACE</dt>
<dd>Der Namensbereich, den Sie hinzufügen wollen. Der Namensbereich muss für alle {{site.data.keyword.Bluemix_notm}}-Konten in derselben Region eindeutig sein.</dd>
</dl>


## bx cr namespace-list (bx cr namespaces)
{: #bx_cr_namespace_list}

Zeigt alle Namensbereiche an, die Ihrem {{site.data.keyword.Bluemix_notm}}-Konto angehören.

```
bx cr namespace-list
```
{: codeblock}


## bx cr namespace-rm
{: #bx_cr_namespace_rm}

Entfernt einen Namensbereich aus Ihrem {{site.data.keyword.Bluemix_notm}}-Konto. Images in dieser Namensbereich werden gelöscht, wenn der Namensbereich entfernt wird.

```
bx cr namespace-rm NAMESPACE
```
{: codeblock}

**Parameter**
<dl>
<dt>NAMESPACE</dt>
<dd>Der Namensbereich, den Sie entfernen wollen.</dd>
</dl>


## bx cr plan
{: #bx_cr_plan}

Zeigt Ihren Preistarif an.

```
bx cr plan
```
{: codeblock}


## bx cr plan-upgrade
{: #bx_cr_plan_upgrade}

Führt ein Upgrade auf den Standardplan durch.

Weitere Informationen über Pläne finden Sie unter [Registry-Pläne](../../../services/Registry/registry_overview.html#registry_plans).

```
bx cr plan-upgrade [PLAN]
```
{: codeblock}

**Parameter**
<dl>
<dt>PLAN</dt>
<dd>Der Name des Preistarifs, auf den das Upgrade durchgeführt werden soll. Wird für PLAN keine Angabe gemacht, wird standardmäßig der `Standardplan` verwendet.</dd>
</dl>


## bx cr quota
{: #bx_cr_quota}

Zeigt die aktuellen Kontingente für den Datenverkehr und die Speicherung sowie Nutzungsinformationen zu diesen Kontingenten an.

```
bx cr quota
```
{: codeblock}


## bx cr quota-set
{: #bx_cr_quota_set}

Ändert das angegebene Kontingent.

```
bx cr quota-set [--traffic TRAFFIC] [--storage STORAGE]
```
{: codeblock}

**Parameter**
<dl>
<dt>--traffic TRAFFIC</dt>
<dd>(Optional) Ändert Ihr Datenverkehrskontingent auf den angegebenen Wert in Megabyte. Die Operation schlägt fehl, wenn Sie nicht berechtigt sind, den Datenverkehr festzulegen, oder wenn Sie einen Wert festlegen, der Ihren aktuellen Preistarif überschreitet.</dd>
<dt>--storage STORAGE</dt>
<dd>(Optional) Ändert Ihr Speicherkontingent auf den angegebenen Wert in Megabyte. Die Operation schlägt fehl, wenn Sie nicht berechtigt sind, den Speicherkontingente festzulegen, oder wenn Sie einen Wert festlegen, der Ihren aktuellen Preistarif überschreitet.</dd>
</dl>


## bx cr region
{: #bx_cr_region}

Zeigt die Zielregion und die Registry an.

```
bx cr region
```
{: codeblock}

Weitere Informationen finden Sie unter [Regionen](../../../services/Registry/registry_overview.html#registry_regions).


## bx cr region-set
{: #bx_cr_region_set}

Legen Sie eine Zielregion für die {{site.data.keyword.registrylong_notm}}-Befehle fest. Um die verfügbaren Regionen aufzulisten, führen Sie den Befehl ohne Parameter aus.

```
bx cr region-set [REGION]
```
{: codeblock}

**Parameter**
<dl>
<dt>REGION</dt>
<dd>(Optional) Der Name Ihrer Zielregion, z. B. `us-south`. 

Weitere Informationen finden Sie unter [Regionen](../../../services/Registry/registry_overview.html#registry_regions).

</dd>
</dl>


## bx cr token-add
{: #bx_cr_token_add}

Fügt ein Token hinzu, das Sie verwenden können, um den Zugriff auf eine Registry zu steuern.

```
bx cr token-add [--description DESCRIPTION] [-q, --quiet] [--non-expiring] [--readwrite]
```

{: codeblock}


**Parameter**
<dl>
<dt>--description DESCRIPTION</dt>
<dd>(Optional) Gibt den Wert als Beschreibung für das Token an, das beim Ausführen von `bx cr token-list` angezeigt wird. Wenn das Token automatisch vom {{site.data.keyword.containerlong_notm}} erstellt wird, wird als Beschreibung der Kubernetes-Clustername festgelegt. In diesem Fall wird das Token automatisch entfernt, wenn Ihr Cluster entfernt wird.</dd>
<dt>-q, --quiet</dt>
<dd>(Optional) Zeigt nur das Token ohne den umgebenden Text an.</dd>
<dt>--non-expiring</dt>
<dd>(Optional) Erstellt ein Token mit Zugriff, der nicht abläuft. Ist dieser Parameter nicht festgelegt, läuft der Zugriff über ein Token standardmäßig nach 24 Stunden ab.</dd>
<dt>--readwrite</dt>
<dd>(Optional) Erstellt ein Token, das Lese- und Schreibzugriff gewährt. Ohne diese Option ist der Zugriff standardmäßig schreibgeschützt.</dd>
</dl>


## bx cr token-get
{: #bx_cr_token_get}

Ruft das angegebene Token aus der Registry ab.

```
bx cr token-get TOKEN
```

{: codeblock}

**Parameter**
<dl>
<dt>TOKEN</dt>
<dd>(Optional) Die eindeutige ID des Tokens, das Sie abrufen möchten.</dd>
</dl>


## bx cr token-list (bx cr tokens)
{: #bx_cr_token_list}

Zeigt alle Token für Ihr {{site.data.keyword.Bluemix_notm}}-Konto an.

```
bx cr token-list --format FORMAT
```
{: codeblock}

**Parameter**
<dl>
<dt>--format FORMAT</dt>
<dd>(Optional) Formatiert die Ausgabeelemente unter Verwendung einer Go-Vorlage. 

Weitere Informationen finden Sie unter [CLI-Ausgabe für {{site.data.keyword.registrylong_notm}}-Befehle formatieren und filtern](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
</dl>


## bx cr token-rm
{: #bx_cr_token_rm}

Entfernt einen oder mehrere angegebene Token.

```
bx cr token-rm TOKEN [TOKEN...]
```
{: codeblock}

**Parameter**
<dl>
<dt>TOKEN</dt>
<dd>(Optional) TOKEN kann entweder das Token selbst sein oder die eindeutige ID des Tokens, wie in `bx cr token-list` dargestellt. Es können mehrere Token angegeben sein und sie müssen durch ein Leerzeichen getrennt werden.</dd>
</dl>


## bx cr vulnerability-assessment (bx cr va)
{: #bx_cr_va}

Zeigt eine Schwachstellenanalyse für Ihre Images an.

```
bx cr vulnerability-assessment [--extended | -e] [--vulnerabilities | -v] [--configuration-issues | -c] [--output FORMAT | -o FORMAT] IMAGE [IMAGE...] 
```
{: codeblock}

**Parameter**
<dl>
<dt>IMAGE</dt>
<dd>Der Name des Images, für das ein Bericht abgerufen werden soll. Der Bericht informiert Sie darüber, ob das Image bekannte Paketschwachstellen aufweist. Sie können Berichte für mehrere Images gleichzeitig anfordern, indem Sie die einzelnen Images in dem Befehl jeweils durch ein Leerzeichen getrennt auflisten.

<p>Eine Liste mit den Namen Ihrer Images können Sie mit dem Befehl `bx cr image-list` anzeigen. Kombinieren Sie den Inhalt der Spalten für Repository und Tag, um den Imagenamen im Format `repository:tag` zu erstellen. Ist im Imagenamen kein Tag angegeben, wird das Image mit dem Tag `latest` im Bericht beurteilt. </p> 

<p>Folgende Betriebssysteme werden unterstützt:

<ul>

<li>Alpine</li>
<li>CentOS</li>
<li>Debian</li>
<li>Red Hat Enterprise Linux (RHEL)</li>
<li>Ubuntu</li>
</ul>

</p>

Weitere Informationen finden Sie in [Imagesicherheit mit Vulnerability Advisor verwalten](../../../services/va/va_index.html).

</dd>
<dt>--output FORMAT, -o FORMAT</dt>
<dd>(Optional) Die Befehlsausgabe wird im ausgewählten Format ausgegeben. Das Standardformat ist `text`. Folgende Formate werden unterstützt:

<ul>

<li>`text`</li>
<li>`json`</li>
</ul>

</dd>
<dt>--vulnerabilities, -v</dt>
<dd>(Optional) Die Befehlsausgabe ist auf die Anzeige von Schwachstellen begrenzt.</dd>
<dt>--configuration-issues, -c</dt>
<dd>(Optional) Die Befehlsausgabe ist auf die Anzeige von Konfigurationsproblemen begrenzt.</dd>
<dt>--extended, -e </dt>
<dd>(Optional) In der Befehlsausgabe werden zusätzliche Informationen zu Korrekturen für gefährdete Pakete angezeigt.</dd>

</dl>

