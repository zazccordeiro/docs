![ZAZ Conecta](https://www.acate.com.br/wp-content/uploads/2021/12/zaz-conecta-anuncio-1200x600px-2.png)

# Guia de schemas 

Esta documentação tem como objetivo ser um facilitador e propor autonomia para o melhor aproveitamento do cubo de dados.

<!-- START graphql-markdown -->

<details>
  <summary><strong>Campos e Requisições</strong></summary>

  * [Informações de medidas](#informações-de-medidas)
  * [Medidas de valores](#medidas-de-valores)
    * [Cobrança](#cobrança)
    * [Período](#período)
  * [Dimensões](#dimensões)
    * [Dimensão cliente](#dimensão-cliente)
    * [Dimensão Plataforma](#dimensão-plataforma)
    * [Dimensão Estabelecimento](#dimensão-estabelecimento)
</details>

## Informações de medidas

As informações abaixo estão catalogadas e descritas de acordo com cada grupo de dados.

## Medidas de valores

### Cobrança

Detalhes de valores de cobrança do cliente.

<table>
<tbody>
<tr>
<th valign="center">Campo</th>
<th valign="center">Tipo</th>
<th valign="center">Descrição</th>
</tr>
<tr>
<td valign="center"><strong>quantidadeTotalPedido</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign= "center"> Essa informação é referente a quantidade total de pedidos, no caso uma contagem que não se refere à valores monetários.

<tr>
<td valign="center"><strong>valorTotalPedido</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign= "center">Esse dado se refere ao valor total dos itens pedidos + valor da taxa de entrega.

</td>
</tr>
<tr>
<td valign="center"><strong>valorTotalItens</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Essa informação é referente ao valor total dos itens solicitados.

</td>
</tr>
<tr>
<td valign="center"><strong>valorTaxaEntrega</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Esse dado se refere a taxa de entrega.

</td>
</tr>
<tr>
<td valign="center"><strong>valorBeneficioIfood</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Valor do subsídio financeiro do iFood no pedido.

</td>
</tr>
<tr>
<td valign="center"><strong>valorBeneficioMerchant</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Valor do subsídio financeiro do parceiro no pedido.

</td>
</tr>
<tr>
<td valign="center"><strong>valorComissao</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Valor total da comissão.

</td>
</tr>
<tr>
<td valign="center"><strong>valorTaxaAdquirente</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Valor da taxa cobrada pelo adquirente referente ao pedido.

</td>
</tr>
<tr>
<td valign="center"><strong>valorComissaoCobrada</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Valor da comissão cobrada quando o modelo de negócio é <strong>ON_DEMAND</strong>, <strong>HYBRID</strong> ou <strong>HYBRID_REGION</strong>.

</td>
</tr>
<tr>
<td valign="center"><strong>valorComissaoPedido</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Percentual de comissão cobrado para o pedido.

</td>
</tr>
<tr>
<td valign="center"><strong>taxaPercentualAdquirente</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Percentual de taxa cobrada pelo adquirente referente ao pedido.

</td>
</tr>
<tr>
<td valign="center"><strong>valorPagoIfood</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Valor pago para o ifood referente às taxas.

</td>
</tr>
<tr>
<td valign="center"><strong>valorPagoMerchant</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Valor pago ao merchant (subtraído o valor total pago ao Ifood).

</td>
</tr>
<tr>
<td valign="center"><strong>valorTaxaAntecipacao</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Valor da taxa de antecipação cobrado referente ao pedido.

</td>
</tr>
<tr>
<td valign="center"><strong>valorTaxaAntecipacaoPercentual</strong></td>
<td valign="center"><a href="#Double">Double</a></td>
<td valign="center"> Percentual da taxa de antecipação cobrado referente a ao pedido.
</td>
</tr>
</tbody>
</table>

## Período

Informações referente a data das ocorrencias ligadas a pedidos e pagamentos.

<table>
<tbody>
<tr>
<th valign="center">Campo</th>
<th valign="center">Tipo</th>
<th valign="center">Descrição</th>
</tr>
<tr>
<td valign="center"><strong>dataPrevistaPagamento</strong></td>
<td valign="center"><a href="#Datetime">Datetime</a></td>
<td valign="center"> Data esperada para o pagamento ao merchant.

</td>
</tr>
<tr>
<td valign="center"><strong>dataCancelamento</strong></td>
<td valign="center"><a href="Datetime">Datetime</a></td>
<td valign="center"> Data do cancelamento no formato YYYY-MM-DD

</td>
</tr>
<tr>
<td valign="center"><strong>dataPedido</strong></td>
<td valign="center"><a href="Datetime">Datetime</a></td>
<td valign="center"> Data e hora de criação do pedido.

</td>
</tr>
<tr>
<td valign="center"><strong>dataOcorrencia</strong></td>
<td valign="center"><a href="Datetime">Datetime</a></td>
<td valign="center"> Data e hora em que foi realizada a transação, ou seja, que houve a ocorrência.

</td>
</tr>
<tr>
<td valign="center"><strong>ultimaDataProcessamento</strong></td>
<td valign="center"><a href="Datetime">Datetime</a></td>
<td valign="center"> Referente a data/hora do último processamento do pedido.
</td>
</tr>
</tbody>
</table>


# Dimensões

Abaixo segue o detalhamento das dimensões disponibilizadas e utilizadas.

## Dimensão cliente

Nesta dimensão é possível fazer a leitura de informações para endereçamento do cliente.

<table>
<tbody>
<tr>
<th valign="center">Campo</th>
<th valign="center">Tipo</th>
<th valign="center">Descrição</th>
</tr>
<tr>
<td valign="center"><strong>clienteId</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td valign="center"> Código de identificação único do cliente.

</td>
</tr>
<tr>
<td valign="center"><strong>numeroDocumentoCliente</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td valign="center"> Número do documento do cliente (CPF) que deve ser utilizado somente para emissão de documento fiscal quando o cliente solicitar,
pois o campo é opcional.

</td>
</tr>
<tr>
<td valign="center"><strong>nomeCliente</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td valign="center"> Nome cliente.

</td>
</tr>
<tr>
<td valign="center"><strong>numeroTelefoneCliente</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td valign="center"> Número de telefone do cliente ou do 0800 fornecido pelo iFood.
</td>
</tr>
</tbody>
</table>

## Dimensão Status

Situação e período da informação.

<table>
<tbody>
<tr>
<th valign="center">Campo</th>
<th valign="center">Tipo</th>
<th valign="center">Descrição</th>
</tr>
<tr>
<td valign="center"><strong>statusIfood</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td> 
<p> Código que se refere a situação da informação.</p>
<p> 1 = Vendas  </p>
<p> 2 = Ocorrências </p>
<p> 3 = Cancelamentos </p>
</td>
</tr>
</tbody>
</table>

## Dimensão Plataforma

Informação de qual plataforma utilizada.

<table>
<tbody>
<tr>
<th valign="center">Campo</th>
<th valign="center">Tipo</th>
<th valign="center">Descrição</th>
</tr>
<tr>
<td valign="center"><strong>plataforma</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td> 
<p> Código que se refere a plataforma de delivery.</p>
<p> <strong>0</strong> = NULL  </p>
<p> <strong>1</strong> = Ifood </p>
</td>
</tr>
</tbody>
</table>

## Dimensão Estabelecimento

Esta dimensão contém informações refere.

<table>
<tbody>
<tr>
<th valign="center">Campo</th>
<th valign="center">Tipo</th>
<th valign="center">Descrição</th>
</tr>
<tr>
<td valign="center"><strong>clienteId</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td> Código de identificação único do cliente. 

</td>
</tr>
<tr>
<td valign="center"><strong>codigoEstabelecimento</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td valign="center"> Este campo se refere ao código do estabelecimento na plataforma.

</td>
</tr>
<tr>
<td valign="center"><strong>razaoSocialEstabelecimento</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td valign="center"> Este campo informa a razão social do estabelecimento.

</td>
</tr>
<tr>
<td valign="center"><strong>nomeEstabelecimento</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td valign="center"> Este campo informa a razão social do estabelecimento.

</td>
</tr>
</tbody>
</table>

## Dimensão Estabelecimento

Esta dimensão contém informações refere.

<table>
<tbody>
<tr>
<th valign="center">Campo</th>
<th valign="center">Tipo</th>
<th valign="center">Descrição</th>
</tr>
<tr>
<td valign="center"><strong>clienteId</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td> Código de identificação único do cliente. 

</td>
</tr>
<tr>
<td valign="center"><strong>codigoEstabelecimento</strong></td>
<td valign="center"><a href="#String">String</a></td>
<td valign="center"> Este campo se refere ao código do estabelecimento na plataforma.


<!-- END graphql-markdown -->
