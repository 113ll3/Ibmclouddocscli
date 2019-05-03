---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, classic infrastructure, file storage service, ibmcloud sl file, snapshot, file storage, storage, nfs, nas, iops, volume, datacenter, file storage cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Trabalhando com o serviço File Storage
{: #sl-file-storage-service}

O {{site.data.keyword.filestorage_full}} é um {{site.data.keyword.filestorage_short}} baseado em
NFS conectado à rede, persistente rápido e flexível. Nesse ambiente de armazenamento conectado à rede (NAS), você tem controle total sobre sua função de compartilhamentos de arquivo e sobre o desempenho.

Use os comandos a seguir para gerenciar um determinado volume no serviço File Storage da infraestrutura clássica do {{site.data.keyword.cloud_notm}}.
{: shortdesc}
 
## ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

Autorizar hosts a acessar um determinado volume.
```
ibmcloud sl file access-authorize VOLUME_ID [OPTIONS]
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
<dt>-s, --subnet-id</dt>
<dd>Um ID de uma sub-rede a ser autorizada.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```

Esse comando autoriza o servidor virtual com ID `87654321` a acessar o volume com ID `12345678`.

## ibmcloud sl file access-list
{: #sl_file_access_list}

Listar ACLs.
```
ibmcloud sl file access-list VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna para classificação, as opções são: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--column</dt>
<dd>Coluna a exibir; as opções são: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file access-list 12345678 --sortby id
```

Esse comando lista todos os hosts que estão autorizados a acessar o volume com ID `12345678` e os classifica por ID.

## ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

Revogar autorização para hosts que acessam um determinado volume.
```
ibmcloud sl file access-revoke VOLUME_ID [OPTIONS]
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
<dt>-s, --subnet-id</dt>
<dd>Um ID de uma sub-rede a ser revogada.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```

Esse comando revoga o acesso do servidor virtual com o ID `87654321` para o volume com o ID `12345678`.

## ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Efetuar failback de um volume de arquivo da réplica.
```
ibmcloud sl file replica-failback VOLUME_ID
```

**Exemplos**:
```
ibmcloud sl file replica-failback 12345678
```
Esse comando executa a operação de failback para o volume com ID `12345678`.

## ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Efetuar failover de um volume de arquivo no volume de réplica especificado.
```
ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```


**Exemplos**:
```
ibmcloud sl file replica-failover 12345678 87654321
```
Esse comando executa a operação de failover para o volume com ID `12345678` para o volume de réplica com ID `87654321`.

## ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

Listar data centers de replicação adequados para o volume especificado.
```
ibmcloud sl file replica-locations VOLUME_ID
```


**Exemplos**:
```
ibmcloud sl file replica-locations 12345678
```
Esse comando lista os data centers de replicação adequados para o volume de arquivo com ID `12345678`.

## ibmcloud sl file replica-order
{: #sl_file_replica_order}

Pedir um volume de réplica de armazenamento de arquivo.
```
ibmcloud sl file replica-order VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Requerido. Planejamento da captura instantânea a ser usado para replicação, as opções são: HOURLY, DAILY, WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center para a réplica, por exemplo, dal09.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Camada de armazenamento de resistência (IOPS por GB) do volume primário para o qual uma réplica é pedida, as opções são: 0.25, 2, 4, 10. Se nenhuma camada for especificada, a camada do volume original será usada.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100. Se nenhum IOPS for especificado, o IOPS do volume original será usado.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```

Esse comando pede uma réplica para o volume com ID `12345678`, que executa a replicação DAILY, está localizada em `dal09`, o nível de camada é 4.

## ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

Listar volumes replicantes existentes para um volume de arquivo.
```
ibmcloud sl file replica-partners VOLUME_ID [OPTIONS]
```


**Exemplos**:
```
ibmcloud sl file replica-partners 12345678
```

Esse comando lista volumes replicantes existentes para o volume de arquivo com ID `12345678`.

## ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Cancelar o espaço de captura instantânea existente para um determinado volume.
```
ibmcloud sl file snapshot-cancel SNAPSHOT_ID [OPTIONS]
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
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```

Esse comando cancela a captura instantânea com ID `12345678` imediatamente sem solicitar confirmação.

## ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Criar uma captura instantânea em um determinado volume.
```
ibmcloud sl file snapshot-create VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Notas a serem configuradas na nova captura instantânea.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforibmcloud
```
Esse comando cria uma captura instantânea para o volume com ID `12345678` e com nota de adição como `snapshotforibmcloud`.

## ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

Desativar capturas instantâneas no planejamento especificado para um determinado volume.
```
ibmcloud sl file snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Requerido. Planejamento de captura instantânea, as opções são: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```

Esse comando desativa a captura instantânea diária para o volume com ID `12345678`.

## ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

Ativar capturas instantâneas para um determinado volume no planejamento especificado.
```
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONS]
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
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```

Esse comando ativa a captura instantânea para o volume com ID `12345678`. A captura instantânea é obtida semanalmente em cada domingo às 2h e até 5 capturas instantâneas são retidas.

## ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Excluir uma captura instantânea em um determinado volume.
```
ibmcloud sl file snapshot-delete SNAPSHOT_ID
```

**Exemplos**:
```
ibmcloud sl file snapshot-delete 12345678
```

Esse comando exclui a captura instantânea com ID `12345678`.

## ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

Listar capturas instantâneas do armazenamento de arquivo.
```
ibmcloud sl file snapshot-list VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna para classificação, as opções são: id,name,created,size_bytes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```

Esse comando lista todas as capturas instantâneas de volume com ID `12345678` e as classifica por ID.

## ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Pedir espaço de captura instantânea para um volume de armazenamento de arquivo.
```
ibmcloud sl file snapshot-order VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Requerido. Tamanho do espaço de captura instantânea a ser criado em GB.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Camada de armazenamento de resistência (IOPS por GB) do volume de arquivo para o qual o espaço é pedido, as opções são: 0,25, 2, 4, 10.</dd>
<dt>-i, --iops</dt>
<dd>IOPs do armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Sinalização para indicar que a ordem é um upgrade.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
Esse comando pede um espaço de captura instantânea para o volume com ID `12345678`, o tamanho é de 1000 GB, o nível de camada é de 4 IOPS por GB.

## ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Restaurar volume de arquivo usando uma captura instantânea especificada.
```
ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```

**Exemplos**:
```
ibmcloud sl file snapshot-restore 12345678 87654321
```

Esse comando restaura o volume com ID `12345678` da captura instantânea com ID `87654321`.

## ibmcloud sl snapshot-schedule-list
{: #sl_snapshot_schedule_list}

Listar planejamentos de captura instantânea para um determinado volume
```
ibmcloud sl snapshot-schedule-list VOLUME_ID
```

**Exemplos**:
```
ibmcloud sl file snapshot-schedule-list 12345678
```

Esse comando lista planejamentos de captura instantânea para volume com ID `12345678`.

## ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Cancelar um volume de armazenamento de arquivo existente.
```
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Um motivo opcional para cancelamento.</dd>
<dt>--immediate</dt>
<dd>Cancelar o volume de armazenamento de arquivo imediatamente, em vez de no aniversário de faturamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```

Esse comando cancela o volume com ID `12345678` imediatamente e sem solicitar confirmação.

## ibmcloud sl file volume-count
{: #sl_file_volume_count}

Listar o número de volumes de armazenamento de arquivo por data center.
```
ibmcloud sl file volume-count [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
</dl>

## ibmcloud sl file volume-list
{: #sl_file_volume_list}

Listar armazenamento de arquivo.
```
ibmcloud sl file volume-list [OPTIONS]
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
<dd>Filtrar por ID da ordem que comprou o armazenamento de arquivo.</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, mount_addr.</dd>
<dt>--column</dt>
<dd>Coluna a exibir; as opções são: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,mount_addr,notes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```

Esse comando lista todos os volumes do Endurance na conta atual que estão localizados em `dal09` e classifica-os por capacidade.

## ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Exibir detalhes para um volume especificado.
```
ibmcloud sl file volume-detail VOLUME_ID
```


**Exemplos**:
```
ibmcloud sl file volume-detail 12345678
```

Esse comando mostra detalhes do volume com ID `12345678`.

## ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Pedir um volume de arquivo duplicando um volume existente.
```
ibmcloud sl file volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID de uma captura instantânea do volume original a ser usado para duplicação.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Tamanho do volume de arquivo duplicado em GB; se nenhum tamanho for especificado, o tamanho do volume original será usado.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100. Se nenhum IOPS for especificado, o IOPS do volume original será usado.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Camada de armazenamento de resistência, se nenhuma camada for especificada, a camada do volume original será usada.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>O tamanho do espaço de captura instantânea a ser pedido para a duplicata; se nenhum tamanho de espaço de captura instantânea for especificado, o tamanho do espaço de captura instantânea do volume original será usado.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file volume-duplicate 12345678
```

Esse comando mostra a ordem de um novo volume, duplicando o volume com ID `12345678`.

## ibmcloud sl file volume-order
{: #sl_file_volume_order}

Pedir um volume de armazenamento de arquivo.
```
ibmcloud sl file volume-order [OPTIONS]
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
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Parâmetro opcional para pedir espaço de captura instantânea junto ao volume.</dd>
<dt>-b, --billing</dt>
<dd>Parâmetro opcional para Taxa de faturamento (padrão para mensal); as opções são: por hora, mensalmente.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```

Esse comando pede um volume de desempenho com tamanho de 1000 GB, o IOPS é 4000, localizado em `dal09`.

## ibmcloud sl file volume-modify
{: #sl_file_volume_modify}

Modificar um volume de armazenamento de arquivo existente
```
ibmcloud sl file volume-modify VOLUME_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-c, --new-size</dt>
<dd>Novo tamanho do volume de arquivo em GB. ***Se nenhum tamanho for fornecido, o tamanho original do volume será usado.*** Tamanhos potenciais: [20, 40, 80, 100, 250, 500, 1000, 2000, 4000, 8000, 12000] Mínimo: [o tamanho original do volume]</dd>
<dt>-i, --new-iops</dt>
<dd>IOPS de armazenamento de desempenho, entre 100 e 6.000 em múltiplos de 100 [somente para volumes de desempenho] ***Se nenhum valor de IOPS for especificado, o valor de IOPS original do volume será usado.*** Requisitos: [Se o IOPS/GB original para o volume for menor que 0,3, o novo IOPS/GB também deverá ser menor que 0,3. Se o IOPS/GB original do volume for maior ou igual a 0,3, o novo IOPS/GB do volume também deverá ser maior ou igual a 0,3.]</dd>
<dt>-t, --new-tier</dt>
<dd>Camada de armazenamento do Endurance (IOPS por GB) [somente para volumes do Endurance] ***Se nenhuma camada for especificada, a camada original do volume será usada.***
Requisitos: [Se o IOPS/GB original para o volume for 0,25, o novo IOPS/GB para o volume também deverá ser 0,25. Se o IOPS/GB original para o volume for maior que 0,25, o novo IOPS/GB para o volume também deverá ser maior que 0,25.]</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:

```
ibmcloud sl file volume-modify 12345678 --new-size 1000 --new-iops 4000
```

Esse comando modifica um volume `12345678`, em que o tamanho é 1000 GB e IOPS é 4000.

```
ibmcloud sl file volume-modify 12345678 --new-size 500 --new-tier 4
```

Esse comando modifica um volume `12345678`, em que o tamanho é 500 GB e o nível de camada é 4 IOPS por GB.


## ibmcloud sl file volume-options
{: #sl_file_volume_options}

Listar todas as opções para pedir um armazenamento de arquivo.
```
ibmcloud sl file volume-options
```

**Exemplos**:
```
ibmcloud sl file volume-options
```
Esse comando lista todas as opções para criar um volume de armazenamento de arquivo, incluindo o tipo de armazenamento, o tamanho do volume, o IOPS, o nível de camada, o data center e o tamanho da captura instantânea.
