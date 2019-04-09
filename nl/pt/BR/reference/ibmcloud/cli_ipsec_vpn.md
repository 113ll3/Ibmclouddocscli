---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ipsec, vpn, ibmcloud sl ipsec, tunnel, vpn access, datacenter, encryption

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gerenciando túneis VPN IPSec
{: #sl-manage-ipsec-vpn-tunnels}

O acesso à VPN do {{site.data.keyword.cloud}} permite que os usuários gerenciem todos os servidores remotamente e de forma segura por meio da rede privada do {{site.data.keyword.cloud_notm}}. Uma conexão de VPN de sua localização para a rede privada fornece a capacidade de gerenciamento fora da banda e de resgate do servidor por meio de um túnel VPN criptografado.

Use os comandos a seguir para gerenciar os túneis VPN IPSec no serviço de VPN IPSec da infraestrutura clássica do {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## Sl ipsec cancel ibmcloud
{: #sl_ipsec_cancel}

Cancelar um contexto do túnel VPN IPSec.
```
Ibmcloud sl ipsec cancel CONTEXT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--immediate</dt>
<dd>Cancelar o IPSec imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## Ibmcloud sl ipsec config
{: #sl_ipsec_config}

Solicitar configuração de um contexto de túnel.
```
Sl ipsec config CONTEXT_ID ibmcloud [ OPTIONS ]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

Listar detalhes de contexto do túnel VPN IPSec.
```
Ibmcloud sl ipsec detail CONTEXT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-i, --include</dt>
<dd>Incluir recursos adicionais, as opções são: at, is, rs, sr, ss.</dd>
</dl>

## Sl ipsec list ibmcloud
{: #sl_ipsec_list}

Listar contextos do túnel VPN IPSec.
```
Sl ipsec list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou o IPSEC.</dd>
</dl>

## Sl ipsec order ibmcloud
{: #sl_ipsec_order}

Pedir um túnel VPN IPSec.
```
Sl ipsec order ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center para o IPSEC, por exemplo, dal09.</dd>
</dl>

## Sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Incluir uma sub-rede em um contexto do túnel IPSec.
```
Ibmcloud sl ipsec subnet-add CONTEXT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>Identificador de sub-rede a ser incluído, necessário.</dd>
<dt>-t, --subnet-type</dt>
<dd>Tipo de sub-rede a ser incluído, necessário, as opções são: internal, remote, service.</dd>
<dt>-n, --network</dt>
<dd>O identificador de rede da sub-rede a ser criado.</dd>
</dl>

## Ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Remover uma sub-rede de um contexto do túnel IPSec.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

## Sl ipsec translation-add
{: #sl_ipsec_translation_add}

Incluir uma conversão de endereço em um túnel IPSec.
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Endereço IP estático, necessário.</dd>
<dt>-r, --remote-ip</dt>
<dd>Endereço IP remoto, necessário.</dd>
<dt>-n, --note</dt>
<dd>Nota.</dd>
</dl>

## Ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Remover uma entrada de conversão de um IPSec.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

## Ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Atualizar uma conversão de endereço para um IPSec.
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Endereço IP estático, necessário.</dd>
<dt>-r, --remote-ip</dt>
<dd>Endereço IP remoto, necessário.</dd>
<dt>-n, --note</dt>
<dd>Nota.</dd>
</dl>

## Sl ipsec update ibmcloud
{: #sl_ipsec_update}

Atualizar propriedades de contexto de túnel.
```
Sl ipsec update ibmcloud CONTEXT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Nome fácil.</dd>
<dt>-r, --remote-peer</dt>
<dd>Endereço IP peer remoto.</dd>
<dt>-k, --preshared-key</dt>
<dd>Chave pré-compartilhada.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Autenticação fase 1, as opções são: MD5, SHA1, SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Criptografia fase 1, as opções são: DES, 3DES, AES128, AES192, AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Grupo diffie hellman fase 1, as opções são: 0, 1, 2, 5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Duração da chave fase 1, o intervalo é 120 - 172.800.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Autenticação fase 2, as opções são: MD5, SHA1, SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Criptografia fase 2, as opções são: DES, 3DES, AES128, AES192, AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Grupo diffie hellman fase 2, as opções são: 0, 1, 2, 5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>Segredo de encaminhamento perfeito fase 2, o intervalo é 0 - 1.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Duração da chave fase 2, o intervalo é 120 - 172.800.</dd>
</dl>
