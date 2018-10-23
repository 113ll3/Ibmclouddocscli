---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Block Storage

O armazenamento de bloco do {{site.data.keyword.Bluemix}} é um armazenamento iSCSI
de alto desempenho persistente que é fornecido e gerenciado independentemente das instâncias de cálculo. Os LUNs do
Block Storage baseados em iSCSI são conectados aos dispositivos autorizados por meio de conexões redundantes de
E/S de múltiplos caminhos (MPIO). 

Use os comandos a seguir para gerenciar um determinado volume para o serviço Block Storage de infraestrutura do {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Comandos do Block Storage de infraestrutura do {{site.data.keyword.Bluemix_notm}} ordenados alfabeticamente com os links para as informações adicionais do comando">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[Ibmcloud sl block access-authorize](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_authorize)</td>
  <td>[ibmcloud sl block access-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_list)</td>
  <td>[ibmcloud sl block access-password](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_password)</td>
  <td>[Ibmcloud sl block access-revoke](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_revoke)</td>
  <td>[Ibmcloud sl block replica-failback](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failback)</td>
  <td>[Ibmcloud sl block replica-failover](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failover)</td>
 </tr>
 <tr>
  <td>[Ibmcloud sl block replica-locations](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_locations)</td>
  <td>[Ibmcloud sl block replica-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_order)</td>
  <td>[Ibmcloud sl block replica-partners](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_partners)</td>
  <td>[Ibmcloud sl block snapshot-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_cancel)</td>
  <td>[Ibmcloud sl block snapshot-create](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_create)</td>
  <td>[Ibmcloud sl block snapshot-disable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_disable)</td>
</tr>
<tr>
  <td>[ibmcloud sl block snapshot-enable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_enable)</td>
  <td>[Ibmcloud sl block snapshot-delete](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_delete)</td>
  <td>[Ibmcloud sl block snapshot-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_list)</td>
  <td>[Ibmcloud sl block snapshot-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_order)</td>
  <td>[Ibmcloud sl block snapshot-restore](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_restore)</td>
  <td>[Ibmcloud sl block volume-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_cancel)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-count](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_count)</td>    <td>[Ibmcloud sl block volume-detail](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_detail)</td>
   <td>[Ibmcloud sl block volume-duplicate](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_duplicate)</td>
   <td>[Ibmcloud sl block volume-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_list)</td>
   <td>[Ibmcloud sl block volume-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_order)</td>
   <td>[ibmcloud sl block volume-options
](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_options)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-set-lun-id](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_set_lun_id)</td>  
</tr>
</tbody>
</table>

## Ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

Autorizar hosts a acessar um determinado volume.
```
Ibmcloud sl block access-authorize VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>O ID de um servidor de hardware a ser autorizado.</dd>
<dt>-v, --virtual-id</dt>
<dd>O ID de um servidor virtual a ser autorizado.</dd>
<dt>-i, --ip-address-id</dt>
<dd>O ID de um endereço IP a ser autorizado.</dd>
<dt>-p, --ip-address</dt>
<dd>Um endereço IP a ser autorizado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
Esse comando autoriza o servidor virtual com ID 87654321 a acessar o volume com ID 12345678.

## ibmcloud sl block access-list
{: #sl_block_access_list}

Listar ACLs.
```
Ibmcloud sl block access-list VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna para classificação, as opções são: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Colunas para exibição, as opções são: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block access-list 12345678 --sortby id
```
Esse comando lista todos os hosts que estão autorizados a acessar o volume com ID 12345678 e os classifica por ID.

## ibmcloud sl block access-password
{: #sl_block_access_password}

Muda uma senha para o acesso de um volume.
```
ibmcloud sl block access-password ACCESS_ID PASSWORD
```

## Ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

Revogar autorização para hosts que acessam um determinado volume.
```
Ibmcloud sl block access-revoke VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>O ID de um servidor de hardware a ser revogado.</dd>
<dt>-v, --virtual-id</dt>
<dd>O ID de um servidor virtual a ser revogado.</dd>
<dt>-i, --ip-address-id</dt>
<dd>O ID de um endereço IP a ser revogado.</dd>
<dt>-p, --ip-address</dt>
<dd>Um endereço IP a ser revogado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
Esse comando revoga o acesso do servidor virtual com ID 87654321 para o volume com ID 12345678.

## Ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

Efetuar failback de um volume de bloco da réplica.
```
Ibmcloud sl block replica-failback VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl block replica-failback 12345678
```
Esse comando executa a operação de failback para o volume com ID 12345678.

## Ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

Efetuar failover de um volume de bloco no volume de réplica especificado.
```
Ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**Exemplos**:
```
Ibmcloud sl block replica-failover 12345678 87654321
```
Esse comando executa a operação de failover do volume com ID 12345678 para o volume de réplica com ID 87654321.

## Ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

Listar data centers de replicação adequados para o volume especificado.
```
Ibmcloud sl block replica-locations VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl block replica-locations 12345678
```
Esse comando lista os data centers de replicação adequados para o volume de bloco com ID 12345678.

## Ibmcloud sl block replica-order
{: #sl_block_replica_order}

Pedir um volume de réplica de armazenamento de bloco.
```
Ibmcloud sl block replica-order VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Requerido. Planejamento de captura instantânea a ser usada para replicação, as opções são: HOURLY, DAILY, WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center para a réplica, por exemplo, dal09.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Camada de armazenamento de resistência (IOPS por GB) do volume primário para o qual uma réplica é pedida, as opções são: 0.25, 2, 4, 10. Se nenhuma camada for especificada, a camada do volume original será usada.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100. Se nenhum IOPS for especificado, o IOPS do volume original será usado.</dd>
<dt>-o, --os-type</dt>
<dd>Opcional. Tipo de sistema operacional (por exemplo, LINUX) do volume primário para o qual uma réplica é pedida, as opções são: HYPER_V,LINUX, VMWARE, WINDOWS_2008, WINDOWS_GPT, WINDOWS, XEN.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
Esse comando pede uma réplica para o volume com ID 12345678, que executa a replicação DAILY, está localizado em dal09, o nível de camada é 4, o tipo de OS é Linux.

## Ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

Listar volumes replicantes existentes para um volume de bloco.
```
Ibmcloud sl block replica-partners VOLUME_ID [ OPTIONS ]
```


**Exemplos**:
```
Ibmcloud sl block replica-partners 12345678
```
Esse comando lista volumes replicantes existentes para o volume de bloco com ID 12345678.

## Ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Cancelar o espaço de captura instantânea existente para um determinado volume.
```
Ibmcloud sl block snapshot-cancel SNAPSHOT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>--immediate</dt>
<dd>Cancelar o espaço de captura instantânea imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
Esse comando cancela a captura instantânea com ID 12345678 imediatamente sem pedir confirmação.

## Ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

Criar uma captura instantânea em um determinado volume.
```
Ibmcloud sl block snapshot-create VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Notas a serem configuradas na nova captura instantânea.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```
Esse comando cria uma captura instantânea para o volume com o ID 12345678 e com a nota de adição como snapshotforibmcloud.

## Ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

Desativar capturas instantâneas no planejamento especificado para um determinado volume.
```
Ibmcloud sl block snapshot-disable VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Requerido. Planejamento de captura instantânea, as opções são: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
Esse comando desativa a captura instantânea diária para o volume com ID 12345678.

## ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

Ativar capturas instantâneas para um determinado volume no planejamento especificado.
```
Ibmcloud sl block snapshot-enable VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Requerido. Planejamento de captura instantânea, as opções são: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Requerido. Número de capturas instantâneas a serem retidas.</dd>
<dt>-m, --minute</dt>
<dd>Minuto da hora em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 59.</dd>
<dt>-r, --hour</dt>
<dd>Hora do dia em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Dia da semana em que as capturas instantâneas devem ser obtidas, número inteiro entre 0 e 6. 0 significa domingo, 1 significa segunda-feira, 2 significa terça-feira, 3 significa quarta-feira, 4 significa quinta-feira, 5 significa sexta-feira, 6 significa sábado.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Esse comando ativa a captura instantânea para o volume com ID 12345678, a captura instantânea é tomada semanalmente todo domingo às 2h e até cinco capturas instantâneas são retidas.

## Ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

Excluir uma captura instantânea em um determinado volume.
```
Ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**Exemplos**:
```
Ibmcloud sl block snapshot-delete 12345678
```
Esse comando exclui a captura instantânea com ID 12345678.

## Ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

Listar capturas instantâneas de armazenamento de bloco.
```
Ibmcloud sl block snapshot-list VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna para classificação, as opções são: id,name,created,size_bytes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
Esse comando lista todas as capturas instantâneas do volume com ID 12345678 e as classifica por ID.

## Ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

Pedir espaço de captura instantânea para um volume de armazenamento de bloco.
```
Ibmcloud sl block snapshot-order VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Requerido. Tamanho do espaço de captura instantânea a ser criado em GB.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Camada de armazenamento de resistência (IOPS por GB) do volume de bloco para o qual o espaço é pedido, as opções são: 0,25, 2, 4, 10.</dd>
<dt>-i, --iops</dt>
<dd>IOPs do armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Sinalização para indicar que a ordem é um upgrade.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
Esse comando pede o espaço de captura instantânea para o volume com ID 12345678; o tamanho é 1.000 GB, o nível de camada é 4 IOPS por GB.

## Ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

Restaurar volume de bloco usando uma captura instantânea especificada.
```
Ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Exemplos**:
```
Ibmcloud sl block snapshot-restore 12345678 87654321
```
Esse comando restaura o volume com ID 12345678 da captura instantânea com ID 87654321.

## Ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

Cancelar um volume de armazenamento de bloco existente.
```
Ibmcloud sl block volume-cancel VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>--immediate</dt>
<dd>Cancelar o volume de armazenamento de bloco imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
Esse comando cancela o volume com ID 12345678 imediatamente e sem pedir confirmação.

## ibmcloud sl block volume-count
{: #sl_block_volume_count}

Listar o número de volumes de armazenamento de bloco por data center.
```
ibmcloud sl block volume-count [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
</dl>

## Ibmcloud sl block volume-list
{: #sl_block_volume_list}

Listar armazenamento de bloco.
```
Ibmcloud sl block volume-list [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Filtrar pelo nome do usuário do volume.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>-t, --storage-type</dt>
<dd>Filtrar por tipo de volume de armazenamento, as opções são: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Filtrar pelo ID da ordem que comprou o armazenamento de bloco.</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
<dt>--columns</dt>
<dd>Colunas para exibição, as opções são: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
Esse comando lista todos os volumes de resistência na conta atual que estão localizados em dal09 e os classifica por capacidade.

## ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

Configurar o ID de LUN em um volume de armazenamento de bloco existente.
```
ibmcloud sl block volume-set-lun-id VOLUME_ID LUN_ID
```

## Ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

Exibir detalhes para um volume especificado.
```
Ibmcloud sl block volume-detail VOLUME_ID
```


**Exemplos**:
```
Ibmcloud sl block volume-detail 12345678
```
Esse comando mostra os detalhes do volume com ID 12345678.

## Ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

Pedir um volume de bloco duplicando um volume existente.
```
Ibmcloud sl block volume-duplicate VOLUME_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID de uma captura instantânea do volume de origem a ser usado para duplicação.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Tamanho do volume de bloco duplicado em GB; se nenhum tamanho for especificado, o tamanho do volume original será usado.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100. Se nenhum IOPS for especificado, o IOPS do volume original será usado.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Camada de armazenamento de resistência, se nenhuma camada for especificada, a camada do volume original será usada.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>O tamanho do espaço de captura instantânea a ser pedido para a duplicata; se nenhum tamanho de espaço de captura instantânea for especificado, o tamanho do espaço de captura instantânea do volume de origem será usado.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl block volume-duplicate 12345678
```
Esse comando mostra a ordem de um novo volume duplicando o volume com ID 12345678.

## Ibmcloud sl block volume-order
{: #sl_block_volume_order}

Pedir um volume de armazenamento de bloco.
```
Ibmcloud sl block volume-order [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Requerido. Tipo de volume de armazenamento, as opções são: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Requerido. Tamanho do volume de armazenamento em GB.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100 [necessário para desempenho de tipo de armazenamento].</dd>
<dt>-e, --tier</dt>
<dd>Camada de armazenamento de resistência (IOP por GB) [necessária para resistência de tipo de armazenamento], as opções são: 0.25, 2, 4, 10.</dd>
<dt>-o, --os-type</dt>
<dd>Requerido. Sistema operacional, as opções são: HYPER_V, LINUX, VMWARE, WINDOWS_2008, WINDOWS_GPT, WINDOWS,XEN.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Parâmetro opcional para pedir espaço de captura instantânea junto ao armazenamento de bloco de resistência; especifica o tamanho (em GB) do espaço de captura instantânea a ser pedido.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Esse comando pede um volume de desempenho com tamanho 1.000 GB, IOPS 4.000, tipo de OS LINUX, localizado em dal09.

## ibmcloud sl block volume-options
{: #sl_block_volume_options}

Listar todas as opções para pedir um armazenamento de bloco.
```
ibmcloud sl block volume-options
```


**Exemplos**:
```
ibmcloud sl block volume-options
```
Esse comando lista todas as opções para criar um volume de armazenamento de bloco, incluindo tipo de armazenamento, tamanho do volume, tipo de OS, IOPS, nível de camada, data center e tamanho da captura instantânea.
