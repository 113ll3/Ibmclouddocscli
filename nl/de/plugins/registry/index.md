---



copyright:

  years: 2017

lastupdated: "2017-05-12"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# {{site.data.keyword.registrylong_notm}}-Befehlszeilenschnittstelle (CLI)
{: #containerregcli}

Die {{site.data.keyword.registrylong}}-Befehlszeilenschnittstelle (CLI) ist ein Plug-in für die Verwaltung der Registry und deren Ressourcen für Ihr Konto.
{: shortdesc}

**Voraussetzungen**
* Melden Sie sich vor der Ausführung von Registry-Befehlen bei {{site.data.keyword.Bluemix_short}} mit dem Befehl `bx login` an, um ein {{site.data.keyword.Bluemix_short}}-Zugriffstoken zu generieren und Ihre Sitzung zu authentifizieren.

Informationen zur Verwendung der {{site.data.keyword.registrylong}}-CLI finden Sie unter [IBM Bluemix Container Registry - Übersicht](https://console.ng.bluemix.net/docs/services/Registry/registry_setup.html#registry_setup).

<table summary="Container-Registry verwalten">
<caption>Tabelle 1. Befehle zur Verwaltung der {{site.data.keyword.registryshort}} in {{site.data.keyword.Bluemix_short}}
</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung der Registry</th>
 </thead>
 <tbody>
 <tr>
 <td>[bx cr api](#bx_cr_api)</td>
 <td>[bx cr info](#bx_cr_info)</td>
 <td>[bx cr image-inspect](#bx_cr_image_inspect)</td>
 <td>[bx cr image-list (bx cr images)](#bx_cr_image_list)</td>
 <td>[bx cr image-rm](#bx_cr_image_rm)</td>
 </tr>
 <tr>
 <td>[bx cr login](#bx_cr_login)</td>
 <td>[bx cr namespace-add](#bx_cr_namespace_add)</td>
 <td>[bx cr namespace-list (bx cr namespaces)](#bx_cr_namespace_list)</td>
 <td>[bx cr namespace-rm](#bx_cr_namespace_rm)</td>
 <td>[bx cr plan](#bx_cr_plan)</td> 
 </tr>
 <tr> 
 <td>[bx cr plan-upgrade](#bx_cr_plan_upgrade)</td>
 <td>[bx cr quota](#bx_cr_quota)</td>
 <td>[bx cr quota-set](#bx_cr_quota_set)</td> 
 <td>[bx cr token-add](#bx_cr_token_add)</td>
 <td>[bx cr token-get](#bx_cr_token_get)</td>

 </tr>
  <tr>
 <td>[bx cr token-list (bx cr tokens)](#bx_cr_token_list)</td>
 <td>[bx cr token-rm](#bx_cr_token_rm)</td>   
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


## bx cr info
Zeigt den Namen und das Konto der Registry an, bei der Sie angemeldet sind.

```
bx cr info
```
{: codeblock}


## bx cr image-inspect
Zeigt Details zu einem bestimmten Image an.

```
bx cr image-inspect [--format FORMAT] IMAGE [IMAGE]
```
{: codeblock}

**Parameter**


<dl>
<dt>--format FORMAT</dt>
<dd>(Optional) Formatiert die Ausgabeelemente unter Verwendung einer Go-Vorlage. 


</dd>
<dt>IMAGE</dt>
<dd>Der vollständige {{site.data.keyword.Bluemix_short}}-Registry-Pfad zu dem Image, das Sie untersuchen möchten (Format: `namespace/image:tag`). Wenn in dem Image-Pfad kein Tag angegeben wird, wird das Image mit dem Tag `latest` untersucht. Sie können mehrere Images untersuchen, indem Sie die einzelnen privaten {{site.data.keyword.Bluemix_short}}-Registry-Pfade in dem Befehl jeweils durch ein Leerzeichen getrennt auflisten.</dd>
</dl>


## bx cr image-list (bx cr images)
Zeigt alle Images in Ihrem {{site.data.keyword.Bluemix_short}}-Konto an.

```
 bx cr image-list [--no-trunc] [-q, --quiet] [--include-ibm] [--format FORMAT]
```
{: codeblock}

**Parameter**
<dl>
<dt>--no-trunc</dt>
<dd>(Optional) Gibt an, die Imageauszüge nicht abzuschneiden.</dd>
<dt>-q, --quiet</dt>
<dd>(Optional) Jedes Image ist in folgendem Format aufgelistet: `repository:tag`.</dd>
<dt>--include-ibm</dt>
<dd>(Optional) Schließt von IBM bereitgestellte öffentliche Images in die Ausgabe ein. Ohne diese Option werden standardmäßig nur private Images aufgelistet.</dd>
<dt>--format FORMAT</dt>
<dd>(Optional) Formatiert die Ausgabeelemente unter Verwendung einer Go-Vorlage. 


</dd>

</dl>


## bx cr image-rm
Löscht ein oder mehrere angegebene Images aus Ihrer Registry.

```
bx cr image-rm IMAGE [IMAGE]
```
{: codeblock}

**Parameter**
<dl>
<dt>IMAGE</dt>
<dd>Der vollständige {{site.data.keyword.Bluemix_short}}-Registry-Pfad zu dem Image, das Sie entfernen möchten (Format: `namespace/image:tag`). Wenn der Image-Pfad nicht mit einem Tag versehen wird, wird standardmäßig das Image mit dem Tag `latest` entfernt. Sie können mehrere Images entfernen, indem Sie die einzelnen privaten {{site.data.keyword.Bluemix_short}}-Registry-Pfade in dem Befehl jeweils durch ein Leerzeichen getrennt auflisten.</dd>
</dl>


## bx cr login
Führt den Befehl `docker login` für die Registry aus. Der Befehl `docker login` ist erforderlich, um die Befehle `docker push` und `docker pull` für die Registry ausführen zu können. Dieser Befehl ist nicht erforderlich, um andere `bx cr`-Befehle auszuführen. Wenn Docker nicht installiert ist, gibt dieser Befehl eine Fehlernachricht zurück.

```
bx cr login
```
{: codeblock}


## bx cr namespace-add
Fügt einen Namensbereich zu Ihrem {{site.data.keyword.Bluemix_short}}-Konto hinzu.

```
bx cr namespace-add NAMESPACE
```
{: codeblock}

**Parameter**
<dl>
<dt>NAMESPACE</dt>
<dd>Der Namensbereich, den Sie hinzufügen wollen. Der Namensbereich muss für alle {{site.data.keyword.Bluemix_short}}-Konten in derselben Region eindeutig sein.</dd>
</dl>


## bx cr namespace-list (bx cr namespaces)
Zeigt alle Namensbereiche an, die Ihrem {{site.data.keyword.Bluemix_short}}-Konto angehören.

```
bx cr namespace-list
```
{: codeblock}


## bx cr namespace-rm
Entfernt einen Namensbereich aus Ihrem {{site.data.keyword.Bluemix_short}}-Konto. Images in dieser Namensbereich werden gelöscht, wenn der Namensbereich entfernt wird.

```
bx cr namespace-rm NAMESPACE
```
{: codeblock}

**Parameter**
<dl>
<dt>NAMESPACE</dt>
<dd>Der Namensbereich, den Sie entfernen wollen.</dd>
</dl>

<!-- audience blue staging only begin comment -->

## bx cr plan
{: #bx_cr_plan}

Zeigt Ihren Preistarif an.

```
bx cr plan
```
{: codeblock}

## bx cr plan-upgrade
{: #bx_cr_plan_upgrade}

Ändert das angegebene Kontingent.

```
bx cr plan-upgrade PLAN
```
{: codeblock}

**Parameter**
<dl>
<dt>PLAN</dt>
<dd> Führt ein Upgrade auf den angegebenen Plan durch. Die folgenden Pläne sind verfügbar:<ul>
<li>Kostenlos</li>
<li>Standard</li>
</ul>
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
bx cr quota-set [--traffic VALUE] [--storage VALUE]
```
{: codeblock}

**Parameter**
<dl>
<dt>--traffic VALUE</dt>
<dd>(Optional) Ändert Ihr Datenverkehrskontingent auf den angegebenen Wert. Die Operation schlägt fehl, wenn Sie nicht berechtigt sind, den Datenverkehr festzulegen, oder wenn Sie einen Wert festlegen, der Ihren aktuellen Preistarif überschreitet.</dd>
<dt>--storage VALUE</dt>
<dd>(Optional) Ändert Ihr Speicherkontingent auf den angegebenen Wert. Die Operation schlägt fehl, wenn Sie nicht berechtigt sind, den Speicherkontingente festzulegen, oder wenn Sie einen Wert festlegen, der Ihren aktuellen Preistarif überschreitet.</dd>
</dl>

<!-- audience blue staging only end comment -->

## bx cr token-add
Fügt ein Token hinzu, das Sie verwenden können, um den Zugriff auf eine Registry zu steuern.

```
bx cr token-add [--description VALUE] [-q, --quiet] [--non-expiring] [--readwrite]
```

{: codeblock}


**Parameter**
<dl>
<dt>--description VALUE</dt>
<dd>(Optional) Gibt den Wert als Beschreibung für das Token an, das beim Ausführen von `bx cr token-list` angezeigt wird. Wenn das Token automatisch vom IBM Bluemix Container-Service erstellt wird, wird als Beschreibung der Kubernetes-Clustername festgelegt. In diesem Fall wird das Token automatisch entfernt, wenn Ihr Cluster entfernt wird.</dd>
<dt>-q, --quiet</dt>
<dd>(Optional) Zeigt nur das Token ohne den umgebenden Text an.</dd>
<dt>--non-expiring</dt>
<dd>(Optional) Erstellt ein Token mit Zugriff, der nicht abläuft. Ist dieser Parameter nicht festgelegt, läuft der Zugriff über ein Token standardmäßig nach 24 Stunden ab.</dd>
<dt>--readwrite</dt>
<dd>(Optional) Erstellt ein Token, das Lese- und Schreibzugriff gewährt. Ohne diese Option ist der Zugriff standardmäßig schreibgeschützt.</dd>
</dl>


## bx cr token-get
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
Zeigt alle Token für Ihr {{site.data.keyword.Bluemix_short}}-Konto an.

```
bx cr token-list --format FORMAT
```
{: codeblock}

**Parameter**
<dl>
<dt>--format FORMAT</dt>
<dd>(Optional) Formatiert die Ausgabeelemente unter Verwendung einer Go-Vorlage. 


</dd>
</dl>


## bx cr token-rm
Entfernt einen oder mehrere angegebene Token.

```
bx cr token-rm TOKEN [TOKEN]
```
{: codeblock}

**Parameter**
<dl>
<dt>TOKEN</dt>
<dd>(Optional) TOKEN kann entweder das Token selbst sein oder die eindeutige ID des Tokens, wie in `bx cr token-list` dargestellt. Es können mehrere Token angegeben sein und sie müssen durch ein Leerzeichen getrennt werden.</dd>
</dl>

## bx cr vulnerability-assessment (bx cr va)
{: #bx_cr_va}

Anzeige einer Schwachstellenanalyse für ein Image.

```
bx cr vulnerability-assessment IMAGE [IMAGE...]
```
{: codeblock}

**Parameter**
<dl>
<dt>IMAGE</dt>
<dd>Der vollständige {{site.data.keyword.Bluemix_short}}-Registry-Pfad zu dem Image, für das ein Bericht abgerufen werden soll, im Format `namespace/image:tag`. Der Bericht informiert Sie darüber, ob das Image bekannte Paketschwachstellen aufweist. Folende Betriebssysteme werden unterstützt:

<ul>
<li>CentOS</li>
<li>Debian</li>
<li>Red Hat Enterprise Linux (RHEL)</li>
<li>Ubuntu</li>
</ul>

</dd>

</dd>
</dl>


