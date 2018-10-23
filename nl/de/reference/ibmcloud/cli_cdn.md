---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CDN (Content Delivery Network)

Vom Service 'Content Delivery Network' (CDN) wird Inhalt an die Positionen verteilt, an denen er benötigt wird. Wenn der Inhalt zum ersten Mal benötigt wird, wird er vom Host-Server in das Netz abgerufen und bleibt dort, damit andere Benutzer auf ihn zugreifen können.

Verwenden Sie die folgenden Befehle, um den CDN-Service (CDN = Content Delivery Network) in der {{site.data.keyword.Bluemix_notm}}-Infrastruktur zu verwalten.
{: shortdesc}

<table summary="Alphabetisch geordnete CDN-Befehle der {{site.data.keyword.Bluemix_notm}}-Infrastruktur mit Links zu weiteren Informationen über den Befehl">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_list)</td>
  <td>[ibmcloud sl cdn load](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_load)</td>
  <td>[ibmcloud sl cdn order](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_order)</td>
  <td>[ibmcloud sl cdn options](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_options)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl cdn origin-add](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_add)</td>
  <td>[ibmcloud sl cdn origin-list](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_list)</td>
  <td>[ibmcloud sl cdn origin-remove](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_remove)</td>
  <td>[ibmcloud sl cdn purge](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_purge)</td>
  </tr>
   </tbody>
 </table>

 ## ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

Abbruch für CDN-Konto.
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud sl cdn detail
{: #sl_cdn_detail}

Details eines CDN-Kontos aufführen.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

## ibmcloud sl cdn list
{: #sl_cdn_list}

Alle CDN-Konten auflisten.
```
ibmcloud sl cdn list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id, name, type, created.</dd>
<dt>--order</dt>
<dd>Nach Bestell-ID filtern.</dd>
</dl>

## ibmcloud sl cdn load
{: #sl_cdn_load}

Zwischenspeicherung von mindestens einer Datei auf allen Edge-Knoten.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

## ibmcloud sl cdn order
{: #sl_cdn_order}

CDN-Konto bestellen.
```
ibmcloud sl cdn order [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>CDN-Bandbreite; Preis für nutzungsabhängige Gebühren wird verwendet, falls keine Angabe vorhanden ist.</dd>
<dt>-s, --storage</dt>
<dd>CDN-Speicher; Preis für nutzungsabhängige Gebühren wird verwendet, falls keine Angabe vorhanden ist.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

Optionen für die Bandbreite und den Speicher bei der Anforderung eines CDN-Kontos.
```
ibmcloud sl cdn options
```

## ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Origin-Pull-Zuordnung erstellen.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-t, --type</dt>
<dd>Der Medientyp für diese Zuordnung (http, flash, wm, ...). Standardwert: http.</dd>
<dt>-c, --cname</dt>
<dd>Ein optionaler CNAME zum Verknüpfen mit der Zuordnung.</dd>
</dl>

## ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Origin-Pull-Zuordnungen auflisten.
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

## ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Origin-Pull-Zuordnung entfernen.
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud sl cdn purge
{: #sl_cdn_purge}

Zwischengespeicherte Dateien aus allen Edge-Knoten löschen.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>
