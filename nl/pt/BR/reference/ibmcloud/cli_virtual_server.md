---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gerenciando o Virtual Server de infraestrutura do {{site.data.keyword.Bluemix_notm}}

<table summary="Comandos de infraestrutura geral do {{site.data.keyword.Bluemix_notm}} ordenados alfabeticamente com links que trazem mais informações do comando">

<caption>Tabela 1. {{site.data.keyword.Bluemix_notm}}  comandos do servidor virtual de infraestrutura</caption>
 <thead>
 <th colspan="6">Comandos do servidor virtual de infraestrutura {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[Ibmcloud sl vs cancel](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_cancel)</td>
 <td>[Sl vs capture ibmcloud](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_capture)</td>
 <td>[Ibmcloud sl vs create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_create)</td>
 <td>[ibmcloud sl vs options
](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_options)</td>
 <td>[Sl vs ibmcloud credenciais](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_credentials)</td>
 <td>[Sl vs detail ibmcloud](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_detail)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs dns-sync](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_dns_sync)</td>
 <td>[Sl vs edit ibmcloud](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_edit)</td>
 <td>[ibmcloud sl vs host-create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_create)</td>
 <td>[ibmcloud sl vs host-list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_list)</td>
 <td>[Sl vs list ibmcloud](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_list)</td>
 <td>[Ibmcloud sl vs pause](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_pause)</td>
 </tr>
 <tr>
 <td>[Ibmcloud sl vs power-off](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_off)</td>
 <td>[Sl vs power-ibmcloud](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_on)
 <td>[Sl vs ibmcloud pronto](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_ready)</td>
 <td>[Ibmcloud sl vs reboot](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reboot)</td>
 <td>[Sl vs reload ibmcloud](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reload)</td>
 <td>[Sl vs rescue ibmcloud](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_rescue)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs resume](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_resume)</td>
 <td>[Ibmcloud sl vs upgrade](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_upgrade)</td>
</tr>
   </tbody>
 </table>

 ## Ibmcloud sl vs cancel
{: #sl_vs_cancel}

Cancelar a instância de servidor virtual.
```
Ibmcloud sl vs cancel IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs cancel 12345678
```
Esse comando cancela a instância de servidor virtual com ID de 12345678.

## Sl vs capture ibmcloud
{: #sl_vs_capture}

Capturar a instância do servidor virtual em uma imagem.
```
Ibmcloud sl vs capture IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Requerido. Nome da imagem.</dd>
<dt>--all</dt>
<dd>Capturar todos os discos pertencentes ao VS.</dd>
<dt>--note</dt>
<dd>Incluir uma nota a ser associada à imagem.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
Esse comando captura a instância de servidor virtual com ID de 12345678 com todos os discos em uma imagem chamada "mycloud" com a
nota "teste".

## Ibmcloud sl vs create
{: #sl_vs_create}

Criar instância de servidor virtual.
```
Ibmcloud sl vs create [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Requerido. Parte de host do FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Requerido. Parte de domínio do FQDN.</dd>
<dt>-c, --cpu</dt>
<dd>Requerido. Número de núcleos da CPU.</dd>
<dt>-m, --memory</dt>
<dd>Requerido. Memória em megabytes.</dd>
<dt>--flavor</dt>
<dd>Nome da chave do tipo do Virtual Server público.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center.</dd>
<dt>-o, --os</dt>
<dd>Código de instalação do OS. Dica: é possível especificar <OS>_LATEST.</dd>
<dt>--image</dt>
<dd>ID da imagem. Veja: 'ibmcloud sl image list' para referência.</dd>
<dt>--billing</dt>
<dd>Taxa de faturamento. O padrão é: de hora em hora. As opções são: hourly, monthly.</dd>
<dt>--dedicated</dt>
<dd>Criar um Virtual Server dedicado (Nó privado).</dd>
<dt>--host-id</dt>
<dd>ID do host no qual provisionar um Virtual Server dedicado.</dd>
<dt>--san</dt>
<dd>Usar o armazenamento SAN, em vez de disco local.</dd>
<dt>--test</dt>
<dd>Não criar realmente o servidor virtual.</dd>
<dt>--export</dt>
<dd>Exporta opções para um arquivo de modelo.</dd>
<dt>-i, --postinstall</dt>
<dd>Script de pós-instalação para download.</dd>
<dt>-k, --key</dt>
<dd>Os IDs das chaves SSH a serem incluídas para o usuário raiz (múltiplas ocorrências permitidas).</dd>
<dt>--disk</dt>
<dd>Tamanhos do disco (múltiplas ocorrências permitidas).</dd>
<dt>--private</dt>
<dd>Força o servidor virtual a ter acesso somente à rede privada.</dd>
<dt>--like</dt>
<dd>Usar a configuração de um servidor virtual existente.</dd>
<dt>-n, --network</dt>
<dd>Velocidade da porta de rede em Mbps.</dd>
<dt>-g, --tag</dt>
<dd>Tags a serem incluídas na instância (múltiplas ocorrências permitidas).</dd>
<dt>-t, --template</dt>
<dd>Um arquivo de modelo que padroniza as opções da linha de comandos.</dd>
<dt>-u, --userdata</dt>
<dd>Sequência de metadados definidos pelo usuário.</dd>
<dt>-F, --userfile</dt>
<dd>Leia os dados do usuário do arquivo.</dd>
<dt>--vlan-public</dt>
<dd>O ID da VLAN pública na qual você deseja colocar o servidor virtual.</dd>
<dt>--vlan-private</dt>
<dd>O ID da VLAN privada na qual você deseja colocar o servidor virtual.</dd>
<dt>-S, --public-security-group</dt>
<dd>ID do grupo de segurança para associar com a interface pública (múltiplas ocorrências permitidas).</dd>
<dt>-s, --private-security-group</dt>
<dd>ID do grupo de segurança a ser associado à interface privada (múltiplas ocorrências permitidas).</dd>
<dt>--wait</dt>
<dd>Aguarde até que o servidor virtual conclua o fornecimento por até X segundos antes de retornar.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Esse comando pede uma instância de servidor virtual cujo nome do host é myvsi, o domínio é ibm.com, com 4 núcleos de CPU e 4096M de
memória, localizada no data center: dal10,

## ibmcloud sl vs options
{: #sl_vs_options}

Listar opções para criar a instância de servidor virtual.
```
As opções ibmcloud sl vs [ OPTIONS ]
```


**Exemplos**:
```
ibmcloud sl vs options
```
Esse comando lista todas as opções para criar uma instância de servidor virtual, por exemplo, data centers, CPU, memória, sistema operacional, disco, velocidade de rede, etc.

## Sl vs ibmcloud credenciais
{: #sl_vs_credentials}

Listar credenciais da instância de servidor virtual.
```
Ibmcloud sl vs credentials IDENTIFIER [ OPTIONS ]
```


**Exemplos**:
```
As credenciais sl vs ibmcloud 12345678
```
Esse comando lista todos os pares de nome de usuário e senha de instância de servidor virtual com ID 12345678.

## Sl vs detail ibmcloud
{: #sl_vs_detail}

Obter detalhes para uma instância de servidor virtual.
```
Ibmcloud sl vs detail IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--passwords</dt>
<dd>Mostrar senhas (verifique se tem alguém olhando!).</dd>
<dt>--price</dt>
<dd>Mostrar preços associados.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs details 12345678
```
Esse comando lista informações detalhadas sobre a instância de servidor virtual com ID 12345678.

## ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

Sincronizar registros DNS para uma instância de servidor virtual.
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>Sincronizar o registro A para o host.</dd>
<dt>--aaaa-record</dt>
<dd>Sincronizar o registro AAAA para o host.</dd>
<dt>--ptr</dt>
<dd>Sincronizar o registro PTR para o host.</dd>
<dt>--ttl</dt>
<dd>Configura o TTL para os registros A e/ou PTR, o padrão é: 7200.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
Esse comando sincroniza o registro A (endereço IP V4) da instância de servidor virtual com ID 12345678 para o servidor DNS e configura ttl desse registro A como 3.600.

## Sl vs edit ibmcloud
{: #sl_vs_edit}

Editar detalhes de uma instância de servidor virtual.
```
Sl vs edit IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>Parte de domínio do FQDN.</dd>
<dt>-H, --hostname</dt>
<dd>Parte de host do FQDN. Exemplo: servidor.</dd>
<dt>-g, --tag</dt>
<dd>Tags para configurar ou sequência de caracteres vazia para remover todos.</dd>
<dt>-u, --userdata</dt>
<dd>Sequência de metadados definidos pelo usuário.</dd>
<dt>-F, --userfile</dt>
<dd>Leia os dados do usuário do arquivo.</dd>
<dt>--public-speed</dt>
<dd>Velocidade da porta pública, as opções são: 0, 10, 100, 1000, 10000.</dd>
<dt>--private-speed</dt>
<dd>Velocidade da porta privada, as opções são: 0, 10, 100, 1000, 10000.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
Esse comando atualiza a instância de servidor virtual com o ID 12345678 e configura o seu domínio como "ibm.com", o nome do host como
"myapp" e a tag como "testcli",

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

Crie um host para servidores virtuais dedicados.
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Requerido. Parte de host do FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Requerido. Parte de domínio do FQDN.</dd>
<dt>-d, --datacenter</dt>
<dd>Requerido. Nome abreviado do data center.</dd>
<dt>-s, --size</dt>
<dd>Tamanho do host dedicado; atualmente apenas um tamanho está disponível: 56_CORES_X_242_RAM_X_1_4_TB.</dd>
<dt>-b, --billing</dt>
<dd>Taxa de faturamento. O padrão é: de hora em hora. As opções são: hourly, monthly.</dd>
<dt>-v, --vlan-private</dt>
<dd>O ID da VLAN privada na qual você deseja que o host dedicado seja colocado. Consulte: 'ibmcloud sl vlan list' para referência.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

Listar hosts dedicados em sua conta.
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>Opções de comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Filtrar por nome do host dedicado.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar por data center do host dedicado.</dd>
<dt>--owner</dt>
<dd>Filtrar pelo proprietário do host dedicado.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou esse host dedicado.</dd>
</dl>

## Sl vs list ibmcloud
{: #sl_vs_list}

Listar instâncias de servidor virtual em sua conta.
```
Sl vs list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Filtre por número de núcleos da CPU.</dd>
<dt>-D, --domain</dt>
<dd>Filtrar por parte do domínio do FQDN.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>-H, --hostname</dt>
<dd>Filtrar por parte do host do FQDN.</dd>
<dt>-m, --memory</dt>
<dd>Filtrar por memória em megabytes.</dd>
<dt>-n, --network</dt>
<dd>Filtre por velocidade de porta de rede em Mbps.</dd>
<dt>-P, --public-ip</dt>
<dd>Filtrar por endereços IP públicos.</dd>
<dt>-p, --private-ip</dt>
<dd>Filtre por endereços IP privados.</dd>
<dt>--hourly</dt>
<dd>Mostrar apenas instâncias de hora em hora.</dd>
<dt>--monthly</dt>
<dd>Mostrar apenas instâncias mensais.</dd>
<dt>-g, --tag</dt>
<dd>Filtrar por tags (múltiplas ocorrências permitidas).</dd>
<dt>-o, --order</dt>
<dd>Filtrar pelo ID da ordem que comprou essa instância.</dd>
<dt>--owner</dt>
<dd>Filtrado pelo ID do usuário que possui as instâncias.</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar; o padrão é: hostname, as opções são: id, hostname, domain, datacenter, cpu, memory, public_ip, private_ip.</dd>
<dt>--columns</dt>
<dd>Colunas para exibição; o padrão é: id, hostname, public_ip, private_ip, datacenter, action, as opções são:
guid, power_state, created_by, tags.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
Esse comando lista todas as instâncias de servidor virtual de faturamento por hora na conta atual filtrando o domínio igual a
"ibm.com" e as classifica pela memória.

## Ibmcloud sl vs pause
{: #sl_vs_pause}

Pausar uma instância de servidor virtual ativa.
```
Sl vs pause IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs pause 12345678 -f
```
Esse comando pausa a instância de servidor virtual com ID 12345678 sem solicitar confirmação.

## Ibmcloud sl vs power-off
{: #sl_vs_power_off}

Desligar uma instância de servidor virtual ativa.
```
Ibmcloud sl vs power-off IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--hard</dt>
<dd>Executar um encerramento forçado.</dd>
<dt>--soft</dt>
<dd>Executar um encerramento normal.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs power-off 12345678 -- soft
```
Esse comando executa um desligamento normal da instância de servidor virtual com ID 12345678.

## Sl vs power-ibmcloud
{: #sl_vs_power_on}

Ligar uma instância de servidor virtual.
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs power-on 12345678
```
Esse comando executa uma ligação da instância de servidor virtual com ID 12345678.

## Sl vs ibmcloud pronto
{: #sl_vs_ready}

Verificar se uma instância de servidor virtual está pronta para uso.
```
Ibmcloud sl vs ready IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--wait</dt>
<dd>Aguarde até que o servidor virtual conclua o fornecimento por até X segundos antes de retornar.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
Esse comando verifica a instância de servidor virtual com o status de ID 12345678 para ver se está pronto para ser usado continuamente e aguarda até 30 segundos.

## Ibmcloud sl vs reboot
{: #sl_vs_reboot}

Reinicializar uma instância de servidor virtual ativa.
```
Ibmcloud sl vs reboot IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--hard</dt>
<dd>Execute uma reinicialização forçada.</dd>
<dt>--soft</dt>
<dd>Executa uma reinicialização normal.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs reboot 12345678 -- hard
```
Esse comando executa uma reinicialização permanente da instância de servidor virtual com ID 12345678.

## Sl vs reload ibmcloud
{: #sl_vs_reload}

Recarregar o sistema operacional em uma instância de servidor virtual.
```
Sl vs reload IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Script de pós-instalação para download.</dd>
<dt>--image</dt>
<dd>ID da imagem. O padrão é usar o sistema operacional atual.</dd>
<dt>Veja:</dt>
<dd>" Ibmcloud sl image list ' para referência.</dd>
<dt>-k, --key</dt>
<dd>Os IDs das chaves SSH a serem incluídas para o usuário raiz (múltiplas ocorrências permitidas).</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs reload 12345678
```
Esse comando recarrega o sistema operacional atual para a instância de servidor virtual com ID 12345678.

## Sl vs rescue ibmcloud
{: #sl_vs_rescue}

Reinicializar uma instância de servidor virtual em uma imagem de resgate.
```
Sl vs rescue IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs rescue 12345678
```
Esse comando reinicializa a instância de servidor virtual com ID 12345678 em uma imagem de resgate.

## ibmcloud sl vs resume
{: #sl_vs_resume}

Continuar uma instância de servidor virtual pausada.
```
Ibmcloud sl vs resume IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vs resume 12345678
```
Esse comando continua a instância de servidor virtual com ID 12345678.

## Ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Fazer upgrade de uma instância de servidor virtual.
```
Ibmcloud sl vs upgrade IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Número de núcleos da CPU.</dd>
<dt>--private</dt>
<dd>O núcleo da CPU ficará em um servidor host dedicado.</dd>
<dt>-m, --memory</dt>
<dd>Memória em megabytes.</dd>
<dt>--network</dt>
<dd>Velocidade da porta de rede em Mbps.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Esse comando faz upgrade da instância de servidor virtual com ID 12345678 e configura o número de núcleos da CPU como 8, a memória como 8.192 M, a velocidade da porta de rede como 1.000 Mbps.
