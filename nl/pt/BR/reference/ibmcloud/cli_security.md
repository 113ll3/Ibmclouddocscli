---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Segurança

As chaves SSH permitem acesso a um dispositivo sem usar uma senha de clientes correspondentes para cada
chave pública que é implementada no dispositivo. Ao incluir uma chave SSH em um dispositivo, o dispositivo que foi fornecido com a chave SSH acessa o dispositivo da chave correspondente sem o uso de senha.

Certificados SSL são ativados por websites como uma medida de segurança para proteger o usuário. Geralmente, eles
são usados quando você é solicitado a transmitir informações confidenciais para um website.

Use os comandos a seguir para gerenciar as chaves SSH e os certificados de infraestrutura do {{site.data.keyword.Bluemix}}.
{: shortdesc}

<table summary="Comandos de segurança de infraestrutura do {{site.data.keyword.Bluemix_notm}} ordenados alfabeticamente com os links para as informações adicionais do comando">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl security sshkey-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_add)</td>
  <td>[Ibmcloud sl security sshkey-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_edit)</td>
  <td>[Ibmcloud sl security sshkey-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_list)</td>
  <td>[Ibmcloud sl security sshkey-print](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_print)</td>
  <td>[Ibmcloud sl security sshkey-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[Ibmcloud sl security cert-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_add)</td>
  <td>[Ibmcloud sl security cert-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_edit)</td>
  <td>[Ibmcloud sl security cert-download](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_download)</td>
  <td>[Ibmcloud sl security cert-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_list)</td>
  <td>[Ibmcloud sl security cert-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

Incluir uma nova chave SSH.
```
Ibmcloud sl security sshkey-add LABEL [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --in-file</dt>
<dd>O arquivo id_rsa.pub a ser importado para essa chave.</dd>
<dt>-k, --key</dt>
<dd>A chave SSH real.</dd>
<dt>--note</dt>
<dd>Nota extra que será associada à chave.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
Esse comando inclui uma chave SSH por meio do arquivo: ~/.ssh/id_rsa.pub with a note "mykey".

## Ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

Editar uma chave SSH.
```
Ibmcloud sl security sshkey-edit IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--label</dt>
<dd>O novo rótulo para a chave.</dd>
<dt>--note</dt>
<dd>Novas notas para a chave.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security sshkey-edit 12345678 --label ibmcloud --note testing
```
Esse comando atualiza a chave SSH com o ID 12345678 e configura o rótulo para "ibmcloud" e a nota para "teste".

## Ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

Listar chaves SSH em sua conta.
```
Ibmcloud sl security sshkey-list [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, label, fingerprint, notes.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl security sshkey-list -- sortby label
```
Esse comando lista todas as chaves SSH na conta atual e as classifica pela etiqueta.

## Ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Imprime uma chave SSH na tela.
```
Ibmcloud sl security sshkey-print IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>A chave SSH pública será gravada neste arquivo.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
Esse comando mostra o ID, o rótulo e as notas da chave SSH com ID 12345678 e grava a chave pública no arquivo: ~/mykey.pub.

## Ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Remove permanentemente uma chave SSH.
```
Ibmcloud sl security sshkey-remove IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl security sshkey-remove 12345678 -f
```
Esse comando remove a chave SSH com ID 12345678 sem solicitar confirmação.

## Ibmcloud sl security cert-add
{: #sl_security_cert_add}

Incluir e fazer upload de detalhes do certificado SSL.
```
Ibmcloud sl security cert-add [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--crt</dt>
<dd>Arquivo de certificado.</dd>
<dt>--csr</dt>
<dd>Arquivo de solicitação de assinatura de certificado.</dd>
<dt>--icc</dt>
<dd>Arquivo de certificado intermediário.</dd>
<dt>--key</dt>
<dd>Arquivo de chave privado.</dd>
<dt>--notes</dt>
<dd>Notas adicionais.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
Esse comando inclui o arquivo de certificado: ~/ibm.com.cert e o arquivo de chave privado ~/ibm.com.key para o domínio ibm.com.

## Ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

Editar certificado SSL.
```
Ibmcloud sl security cert-edit IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--crt</dt>
<dd>Arquivo de certificado.</dd>
<dt>--csr</dt>
<dd>Arquivo de solicitação de assinatura de certificado.</dd>
<dt>--icc</dt>
<dd>Arquivo de certificado intermediário.</dd>
<dt>--key</dt>
<dd>Arquivo de chave privado.</dd>
<dt>--notes</dt>
<dd>Notas adicionais.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
Esse comando edita o certificado com ID 12345678 e atualiza a sua chave privada com o arquivo: ~/ibm.com.key.

## Ibmcloud sl security cert-download
{: #sl_security_cert_download}

Fazer download do certificado SSL e dos arquivos-chave.
```
Ibmcloud sl security cert-download IDENTIFIER
```


**Exemplos**:
```
Ibmcloud sl security cert-download 12345678
```
Esse comando faz download de 4 arquivos no diretório atual para o certificado com ID 12345678. Os 4 arquivos são: arquivo de certificado, arquivo de solicitação de assinatura de certificado, arquivo de certificado intermediário e arquivo de chave privado.

## Ibmcloud sl security cert-list
{: #sl_security_cert_list}

Listar certificados SSL em sua conta.
```
Ibmcloud sl security cert-list [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--status</dt>
<dd>Mostrar certificados com este status, o padrão é: all, as opções são: all, valid, expired.</dd>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, common_name, days_until_expire, notes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
Esse comando lista todos os certificados válidos na conta atual e os classifica pelos dias de validade.

## Ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

Remover certificado SSL.
```
Ibmcloud sl security cert-remove IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl security cert-remove 12345678
```
Esse comando remove o certificado com ID 12345678.
