![ZAZ Conecta](https://www.acate.com.br/wp-content/uploads/2021/12/zaz-conecta-anuncio-1200x600px-2.png)

# Sumário
  
  * [Descricao](#descrição) 
  * [RPAs](#rpas)
    * [FormGo](#formgo)
      * [Flow ID](#flow-id-formgo)
      * [Parametros](#parametros-formgo)
      * [cURL](#curl-formgo)
    * [SafraPay](#safrapay)
      * [Flow ID](#flow-id-safrapay)
      * [Parametros](#parametros-safrapay)
      * [cURL](#curl-safrapay)
    * [GetNet](#getnet)
      * [Flow ID](#flow-id-getnet)
      * [Parametros](#parametros-getnet)
      * [cURL](#curl-getnet)


# Descrição
Esta documentação tem como objetivo ser um facilitador e propor autonomia para o melhor aproveitamento do cubo de dados.

# RPAs
## FormGo
### Flow ID (FormGo)
"version_group_id": "c3779958-5649-4fe8-ab74-5615c2260130"

### Parametros (FormGo)
<table>
  <thead>
    <tr>
      <th valign="center">Campo</th>
      <th valign="center">Exemplo</th>
      <th valign="center">Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr valign="center">
      <td><strong>userId</strong></td>
      <td valign= "center">111222222</td>
      <td valign= "center">Esse será usado para definir o id_extemo que será usado no callback</td>
    </tr>
    <tr valign="center">
      <td><strong>ambiente</strong></td>
      <td valign= "center">dev</td>
      <td valign= "center">
        O ambiente que será retornado o callback
        <ul><li>dev</li><li>prd</li></ul>
      </td>
    </tr>
    <tr valign="center">
      <td><strong>origem</strong></td>
      <td valign= "center">camunda</td>
      <td valign= "center">
        Caso seja enviado Nulo não será enviado callback
        <ul><li>camunda</li><li>bot</li></ul>
      </td>
    </tr>
    <tr valign="center">
      <td><strong>callback</strong></td>
      <td valign= "center">msg_callback</td>
      <td valign= "center">Msg para o camunda ou Bloco para o Bot</td>
    </tr>
    <tr valign="center">
      <td><strong>listaCadastro</strong></td>
      <td valign= "center">[
            {
                "nome": "Ramires Regina da Silva",
                "cnpj": "245.130.390.001-70",
                "email": "tamires.reginasilva@yahoo.com",
                "celular": "21964433428"
            }
        ]</td>
      <td valign= "center">Lista de dados de cadastro </td>
    </tr>    
  </tbody>
</table>

### cURL (FormGo)

<pre>
curl --location --request POST 'http://10.0.41.231:4200/' \
--header 'Accept-Encoding: gzip, deflate, br' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'Connection: keep-alive' \
--header 'DNT: 1' \
--header 'Origin: http://10.0.41.231:4200/' \
--data-raw '{"query":"mutation ($parameters: JSON) {\r\n  create_flow_run(input: { \r\n  version_group_id: \"c3779958-5649-4fe8-ab74-5615c2260130\", \r\n  parameters: $parameters\r\n  }) {\r\n    id\r\n  }\r\n}\r\n","variables":{"parameters":{"userId":"asd","ambiente":"dev","callback":"asd","origem":"camunda","listaCadastro":[{"nome":"Ramires Regina da Silva","cnpj":"245.130.390.001-70","email":"tamires.reginasilva@yahoo.com","celular":"21964433428"}]}}}'
</pre>

## SafraPay

### Flow ID (SafraPay)
"version_group_id": "f97a9018-cf0b-414d-b8b0-8f8c74a80d62"

### Parametros (SafraPay)
<table>
  <thead>
    <tr>
      <th valign="center">Campo</th>
      <th valign="center">Exemplo</th>
      <th valign="center">Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr valign="center">
      <td><strong>usuario</strong></td>
      <td valign= "center">zaz@zaz.vc</td>
      <td valign= "center">Usúario usado para realizar o login no portal, se não for informado, será usado um usuário default gravado no sistema</td>
    </tr>
    <tr valign="center">
      <td><strong>senha</strong></td>
      <td valign= "center">zaz@zaz</td>
      <td valign= "center">Senha usada para realizar o login no portal, se não for informado, será usada uma senha default gravado no sistema</td>
    </tr>
    <tr valign="center">
      <td><strong>userId</strong></td>
      <td valign= "center">111222222</td>
      <td valign= "center">Esse será usado para definir o id_extemo que será usado no callback</td>
    </tr>
    <tr valign="center">
      <td><strong>ambiente</strong></td>
      <td valign= "center">dev</td>
      <td valign= "center">
        O ambiente que será retornado o callback
        <ul><li>dev</li><li>prd</li></ul>
      </td>
    </tr>
    <tr valign="center">
      <td><strong>origem</strong></td>
      <td valign= "center">camunda</td>
      <td valign= "center">
        Caso seja enviado Nulo não será enviado callback
        <ul><li>camunda</li><li>bot</li></ul>
      </td>
    </tr>
    <tr valign="center">
      <td><strong>callback</strong></td>
      <td valign= "center">msg_callback</td>
      <td valign= "center">Msg para o camunda ou Bloco para o Bot</td>
    </tr>
    <tr valign="center">
      <td><strong>listaCadastro</strong></td>
      <td valign= "center">
        [{
          "celular": "21985300445",
          "cnpj": "28179633000128",
          "cpf": "78804655704",
          "nome": "Delci Souza Oliveira",
          "email": "delcisouza.ds@gmail.com",
          "data_nascimento": "1964-03-02T03:00:00.000Z",
          "faturamento": 14630,
          "renda_mensal": "5000",
          "patrimonio": "30000",
          "nome_mae": "MARIA SOUZA OLIVEIRA",
          "pessoa_exposta": "N",
          "possui_socio": "N",
          "participacao": 100,
          "orgao_publico": "N",
          "cep": "25903587",
          "logradouro": "Avenida Automóvel Clube",
          "numero": "61",
          "complemento": "",
          "bairro": "Fragoso",
          "cidade": "Magé",
          "uf": "RJ",
          "maquina": "SafraPay Pro",
          "modalidade": "Aluguel",
          "recebimento": "1 Dia",
          "banco": "Safra",
          "forma_pagamento": "Boleto"
      }]
    </td>
      <td valign= "center">Lista de dados para cadastro </td>
    </tr>    
  </tbody>
</table>

### cURL (SafraPay)

<pre>
curl --location --request POST 'http://10.0.41.231:4200/' \
--header 'Accept-Encoding: gzip, deflate, br' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'Connection: keep-alive' \
--header 'DNT: 1' \
--header 'Origin: http://localhost:4200' \
--data-raw '{"query":"mutation ($parameters: JSON) {\r\n  create_flow_run(input: { \r\n  version_group_id: \"f97a9018-cf0b-414d-b8b0-8f8c74a80d62\", \r\n  parameters: $parameters\r\n  }) {\r\n    id\r\n  }\r\n}\r\n","variables":{"parameters":{"usuario":"46155169837","senha":"270512","userId":"","ambiente":"dev","callback":"","origem":"","listaCadastro":[{"celular":"21985300445","cnpj":"28179633000128","cpf":"78804655704","nome":"Delci Souza Oliveira","email":"delcisouza.ds@gmail.com","data_nascimento":"1964-03-02T03:00:00.000Z","faturamento":14630,"renda_mensal":"5000","patrimonio":"30000","nome_mae":"MARIA SOUZA OLIVEIRA","pessoa_exposta":"N","possui_socio":"N","participacao":100,"orgao_publico":"N","cep":"25903587","logradouro":"Avenida Automóvel Clube","numero":"61","complemento":"","bairro":"Fragoso","cidade":"Magé","uf":"RJ","maquina":"SafraPay Pro","modalidade":"Aluguel","recebimento":"1 Dia","banco":"Safra","forma_pagamento":"Boleto"}]}}}'
</pre>

## GetNet

### Flow ID (GetNet)
"version_group_id": "65c34f8b-8a2c-485f-a6a0-193a1ef929ff"

### Parametros (GetNet)
<table>
  <thead>
    <tr>
      <th valign="center">Campo</th>
      <th valign="center">Exemplo</th>
      <th valign="center">Descrição</th>
    </tr>
  </thead>
  <tbody>
   <tr valign="center">
      <td><strong>usuario</strong></td>
      <td valign= "center">zaz@zaz.vc</td>
      <td valign= "center">Usúario usado para realizar o login no portal, se não for informado, será usado um usuário default gravado no sistema</td>
    </tr>
    <tr valign="center">
      <td><strong>senha</strong></td>
      <td valign= "center">zaz@zaz</td>
      <td valign= "center">Senha usada para realizar o login no portal, se não for informado, será usada uma senha default gravado no sistema</td>
    </tr>
    <tr valign="center">
      <td><strong>userId</strong></td>
      <td valign= "center">111222222</td>
      <td valign= "center">Esse será usado para definir o id_extemo que será usado no callback</td>
    </tr>
    <tr valign="center">
      <td><strong>ambiente</strong></td>
      <td valign= "center">dev</td>
      <td valign= "center">
        O ambiente que será retornado o callback
        <ul><li>dev</li><li>prd</li></ul>
      </td>
    </tr>
    <tr valign="center">
      <td><strong>origem</strong></td>
      <td valign= "center">camunda</td>
      <td valign= "center">
        Caso seja enviado Nulo não será enviado callback
        <ul><li>camunda</li><li>bot</li></ul>
      </td>
    </tr>
    <tr valign="center">
      <td><strong>callback</strong></td>
      <td valign= "center">SP</td>
      <td valign= "center">Msg para o camunda ou Bloco para o Bot</td>
    </tr>
    <tr valign="center">
      <td><strong>listaCadastro</strong></td>
      <td valign= "center">[
            {
                "nome": "Ramires Regina da Silva",
                "cnpj": "245.130.390.001-70",
                "email": "tamires.reginasilva@yahoo.com",
                "celular": "21964433428"
            }
        ]</td>
      <td valign= "center">Lista de dados de cadastro </td>
    </tr>    
  </tbody>
</table>

### cURL (GetNet)

<pre>
curl --location --request POST 'http://10.0.41.231:4200/' \
--header 'Accept-Encoding: gzip, deflate, br' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'Connection: keep-alive' \
--header 'DNT: 1' \
--header 'Origin: http://localhost:4200' \
--data-raw '{"query":"mutation ($parameters: JSON) {\r\n  create_flow_run(input: { \r\n  version_group_id: \"65c34f8b-8a2c-485f-a6a0-193a1ef929ff\",\r\n  parameters: $parameters\r\n  }) {\r\n    id\r\n  }\r\n}\r\n","variables":{"parameters":{"usuario":"128.292.647-03","senha":"daniel08","userId":"","callback":"","origem":"","listaCadastro":[{"cnpj":"22487386000140","antecipacao":"S","maquina":"POS 3G + Wi-Fi com Antecipação Automática","qtde_maquina":1,"taxa_debito":-0.1,"taxa_credito":-0.2,"taxa_parcelado_6":-0.3,"taxa_parcelado_12":-0.4,"faturamento_anual":"1000000,00","faturamento":"10000,00","valor_patrimonio":"10000,00","fone_fixo":"1833333333","nome":"Ivan Augusto de Azevedo","cpf":"33289776867","tipo_documento":"RG","numero_documento":"421717026","orgao_emissor":"SSP","estado_emissor":"SP","data_emissao":"2020-09-14T00:00:00.000Z","data_nascimento":"1985-11-25T00:00:00.000Z","celular":"18999969000","email":"ivan.azevedo@zaz.vc","pais":"Brasil","patrimonio_pessoal":"10000,00","renda_mensal":"10000,00","nome_mae":"Solange Ap Azevedo","cep":"09280510","logradouro":"Rua Arací","numero":"251","complemento":"Apto 8","bairro":"Vila Curuçá","cidade":"Santo André","uf":"SP","ponto_referencia":"aa","sem_numero":"N","opcao_entrega":"normal","mesmo_end_cobranca":"S","banco":"001","tipo_conta":"Conta Poupança","agencia":"0310","conta":"11666","conta_digito":"9"}]}}}'
</pre>

<!-- END graphql-markdown -->
