---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gerenciando chamados de infraestrutura clássica
{: #manage-sl-tickets}

Use os comandos a seguir para gerenciar chamados de infraestrutura clássica do {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

Para conectar dispositivos a um chamado:
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--hardware</dt>
<dd>O identificador de hardware a ser anexado.</dd>
<dt>--virtual</dt>
<dd>O identificador de um servidor virtual a ser anexado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

Para criar um chamado de suporte:
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--attachment</dt>
<dd>Número do ID de objeto inicial a ser anexado ao chamado.</dd>
<dt>--rootpwd</dt>
<dd>A senha raiz que está associada ao ID do dispositivo conectado.</dd>
<dt>--subject-id</dt>
<dd>Requerido. O ID do assunto a ser usado para o chamado, emita 'ibmcloudsl ticket subjects' para obter a lista.</dd>
<dt>--title</dt>
<dd>Requerido. O título do chamado.</dd>
<dt>--body</dt>
<dd>O corpo do chamado.</dd>
<dt>--priority</dt>
<dd>Prioridade do chamado [1|2|3|4], de 1 (Crítico) a 4 (Impacto mínimo). Somente configurável com suporte Avançado e Premium. Consulte https://www.ibm.com/cloud/support.</dd>
<dt>--attachment-type</dt>
<dd>Especifique o tipo de conexão com o hardware ou virtual. O padrão é hardware.</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

Para separar dispositivos de um chamado:
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--hardware</dt>
<dd>O identificador de hardware a ser removido.</dd>
<dt>--virtual</dt>
<dd>O identificador de um servidor virtual a ser removido.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail 
{: #sl_ticket_detail} 

Para visualizar detalhes do chamado:
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--count</dt>
<dd>Número de atualizações.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl ticket detail 767676
```
{: codeblock}

```
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list 
{: #sl_ticket_list} 

Para listar chamados:
```
ibmcloud sl ticket list[OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--open</dt>
<dd>Exibir somente chamados abertos.</dd>
<dt>--closed</dt>
<dd>Exibir somente chamados encerrados.</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

Para listar IDs de assunto para criação de chamado:
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

Para visualizar informações de resumo sobre chamados:
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

Para incluir uma atualização em um chamado existente:
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**Exemplos**:
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

Para incluir um anexo em um chamado existente:
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>Opções de comando</strong>:
<dl>
<dt>--name</dt>
<dd>O nome do anexo mostrado no chamado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

