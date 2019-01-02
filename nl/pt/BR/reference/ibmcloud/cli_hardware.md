---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Criando e trabalhando com servidores bare metal

Os {{site.data.keyword.baremetal_long}} são servidores físicos de locatário único que fornecem desempenho e controle com
acesso de baixo nível aos recursos de hardware. Os servidores bare metal fornecem a potência que você procura para suas cargas de trabalho intensivas de processador e de E/S de disco. Estes servidores vêm com o mais completo pacote de recursos e serviços padrão.

Use os comandos a seguir para gerenciar servidores de hardware bare metal da infraestrutura clássica do {{site.data.keyword.Bluemix}}.
{: shortdesc}

<table summary="Alphabetically ordered  {{site.data.keyword.Bluemix_notm}} classic infrastructure Bare-metal server commands that have links that bring you to more info for the command">
 <tbody>
 <tr>
 <td>[ibmcloud sl hardware cancel](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_cancel)</td>
 <td>[ibmcloud sl hardware cancel-reasons
](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_cancel_reasons)</td>
 <td>[ibmcloud sl hardware create](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_create)</td>
 <td>[ibmcloud sl hardware create-options
](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_create_options)</td>
 <td>[ibmcloud sl hardware credentials](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_credentials)</td>
 <td>[ibmcloud sl hardware detail](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_detail)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware edit](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_edit)</td>
 <td>[ibmcloud sl hardware list](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_list)</td>
 <td>[ibmcloud sl hardware power-cycle](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_cycle)</td>
 <td>[ibmcloud sl hardware power-off](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_off)</td>
 <td>[ibmcloud sl hardware power-on](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_power_on)</td>
 <td>[ibmcloud sl hardware reboot](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_reboot)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware reload](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_reload)</td>
 <td>[ibmcloud sl hardware rescue](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_rescue)</td>
 <td>[ibmcloud sl hardware update-firmware](/docs/cli/reference/ibmcloud/cli_hardware.html#sl_hardware_update_firmware)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

Cancelar um servidor de hardware.
```
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-i, --immediate</dt>
<dd>Cancela o servidor imediatamente (em vez de no aniversário do faturamento).</dd>
<dt>-r, --reason</dt>
<dd>Uma razão de cancelamento opcional. Consulte 'ibmcloud sl hardware cancel-reasons' para uma lista de opções disponíveis.</dd>
<dt>-c, --comment</dt>
<dd>Um comentário opcional para incluir no chamado de cancelamento.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

Exibir uma lista de razões de cancelamento.
```
ibmcloud sl hardware cancel-reasons
```

## ibmcloud sl hardware create
{: #sl_hardware_create}

Pedir/criar um servidor de hardware.
```
ibmcloud sl hardware create [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Parte de host do FQDN, necessário.</dd>
<dt>-D, --domain</dt>
<dd>Parte de domínio do FQDN, necessário.</dd>
<dt>-s, --size</dt>
<dd>Tamanho do hardware, necessário.</dd>
<dt>-o, --os</dt>
<dd>Código de instalação do S.O., necessário.</dd>
<dt>-d, --datacenter</dt>
<dd>Nome abreviado do datacenter, necessário.</dd>
<dt>-p, --port-speed</dt>
<dd>Velocidade da porta, necessária.</dd>
<dt>-b, --billing</dt>
<dd>Taxa de faturamento, por hora ou mensal; o padrão será por hora se não especificado.</dd>
<dt>-i, --post-install</dt>
<dd>Script de pós-instalação para download.</dd>
<dt>-k, --key</dt>
<dd>Chaves SSH para incluir no usuário raiz, múltiplas ocorrências permitidas.</dd>
<dt>-n, --no-public</dt>
<dd>Somente Rede privada.</dd>
<dt>-e, --extra</dt>
<dd>Opções extras, múltiplas ocorrências permitidas.</dd>
<dt>-t, --test</dt>
<dd>Não criar realmente o servidor virtual.</dd>
<dt>-m, --template</dt>
<dd>Um arquivo de modelo que padroniza as opções da linha de comandos.</dd>
<dt>-x, --export</dt>
<dd>Exporta opções para um arquivo de modelo.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

Opções de pedido do servidor para um determinado chassi.
```
ibmcloud sl hardware create-options
```

## ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

Listar credenciais do servidor de hardware.
```
ibmcloud sl hardware credentials IDENTIFIER
```

## ibmcloud sl hardware detail
{: #sl_hardware_detail}

Obter detalhes para um servidor de hardware.
```
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-p, --passwords</dt>
<dd>Mostrar senhas (verifique se tem alguém olhando!).</dd>
<dt>-c, --price</dt>
<dd>Mostrar preços associados.</dd>
</dl>

## ibmcloud sl hardware edit
{: #sl_hardware_edit}

Editar detalhes do servidor de hardware.
```
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Parte de host do FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Parte de domínio do FQDN.</dd>
<dt>-g, --tag</dt>
<dd>Tags para configurar ou sequência de caracteres vazia para remover todos.</dd>
<dt>-F, --userfile</dt>
<dd>Leia os dados do usuário do arquivo.</dd>
<dt>-u, --userdata</dt>
<dd>Sequência de metadados definidos pelo usuário.</dd>
<dt>-p, --public-speed</dt>
<dd>Velocidade da porta pública, as opções são: 0, 10, 100, 1000, 10000.</dd>
<dt>-v, --private-speed</dt>
<dd>Velocidade da porta privada, as opções são: 0, 10, 100, 1000, 10000.</dd>
</dl>

## ibmcloud sl hardware list
{: #sl_hardware_list}

Listar servidores de hardware.
```
ibmcloud sl hardware list [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Filtre por número de núcleos da CPU.</dd>
<dt>-D, --domain</dt>
<dd>Filtrar por domínio.</dd>
<dt>-H, --hostname</dt>
<dd>Filtrar por nome do host.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar por data center.</dd>
<dt>-m, --memory</dt>
<dd>Filtrar por memória em gigabytes.</dd>
<dt>-n, --network</dt>
<dd>Filtrar por velocidade de porta de rede em Mbps.</dd>
<dt>-g, --tag</dt>
<dd>Filtrar por tags, múltiplas ocorrências permitidas.</dd>
<dt>-p, --public-ip</dt>
<dd>Filtrar por endereços IP públicos.</dd>
<dt>-v, --private-ip</dt>
<dd>Filtrar por endereços IP privados.</dd>
<dt>-o, --order</dt>
<dd>Filtrar por ID da ordem que comprou o servidor de hardware.</dd>
<dt>--owner</dt>
<dd>Filtrar por ID do proprietário.</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, padrão: hostname,
opção: id, guid, hostname, domain, public_ip, private_ip, datacenter, status, ipmi_ip, created, created_by.</dd>
<dt>--columns</dt>
<dd>Colunas para exibição, padrão: id, hostname, domain, public_ip, private_ip, datacenter, status; opções: guid, cpu, memory,
os, ipmi_ip, created, created_by, tags.</dd>
</dl>

## ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

Ciclo de energia de um servidor.
```
ibmcloud sl hardware power-cycle IDENTIFIER
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

Desligamento de um servidor ativo.
```
ibmcloud sl hardware power-off IDENTIFIER
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

Ligar um servidor.
```
ibmcloud sl hardware power-on IDENTIFIER
```

## ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

Reinicializar um servidor ativo.
```
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
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

## ibmcloud sl hardware reload
{: #sl_hardware_reload}

Recarregar o sistema operacional em um servidor.
```
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Script de pós-instalação para download, apenas HTTPS é executado, HTTP deixa arquivos em /root.</dd>
<dt>-k, --key</dt>
<dd>IDs da chave SSH para incluir no usuário raiz; múltiplas ocorrências permitidas.</dd>
<dt>-b, --upgrade-bios</dt>
<dd>Atualizar a BIOS.</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>Atualizar o firmware de todos os discos rígidos.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

Reinicializar o servidor em uma imagem de resgate.
```
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

Atualizar o firmware do servidor.
```
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>
