---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl image, manage compute images, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Datenverarbeitungsimages erstellen, bearbeiten und löschen
{: #sl-manage-compute-images}

Verwenden Sie die folgenden Befehle, um {{site.data.keyword.cloud}}-Datenverarbeitungsimages zu verwalten.
{: shortdesc}

## ibmcloud sl image delete
{: #sl_image_delete}

Image löschen.
```
ibmcloud sl image delete IDENTIFIER
```

**Beispiele**:
```
ibmcloud sl image delete 12345678
```

Dieser Befehl löscht das Image mit der ID `12345678`.

## ibmcloud sl image detail
{: #sl_image_detail}

Details zu einem Image abrufen.
```
ibmcloud sl image detail IDENTIFIER
```

**Beispiele**:
```
 ibmcloud sl image detail 12345678
```

Dieser Befehl ruft Details zu dem Image mit der ID `12345678` ab.

## ibmcloud sl image edit
{: #sl_image_edit}

Details zu einem Image bearbeiten.
```
ibmcloud sl image edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--name</dt>
<dd>Name des Images.</dd>
<dt>--note</dt>
<dd>Zusätzliche Anmerkung für das Image.</dd>
<dt>--tag</dt>
<dd>Tags für das Image.</dd>
</dl>

*Beispiele**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```

Dieser Befehl bearbeitet ein Image mit der ID `12345678` und legt den Namen auf `ubuntu16`, die Anmerkung auf `testing` und den Tag auf `staging` fest.

## ibmcloud sl image list
{: #sl_image_list}

Alle Images für eigenes Konto auflisten.
```
ibmcloud sl image list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--name</dt>
<dd>Nach Imagename filtern.</dd>
<dt>--public</dt>
<dd>Nur öffentliche Images anzeigen.</dd>
<dt>--private</dt>
<dd>Nur private Images anzeigen.</dd>
</dl>
