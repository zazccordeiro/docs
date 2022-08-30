<div class="sidebar">
  <a class="active" href="https://zazccordeiro.github.io/schema/"> -Início</a>
  <a href="https://zazccordeiro.github.io/schema/docFatoFluxo.html"> -Tabela Fato Fluxo</a>
  <a href="https://zazccordeiro.github.io/schema/docTabelaAuxiliar.html"> -Tabelas Auxiliares</a>
</div>

![ZAZ Conecta](img/logoZaz.png)


# Arquivo Processado

  <summary><strong>Sumário</strong></summary>
  
  * [Atributos](#atributos) 
    * [Adquirente](#adquirente)
    * [Tempo](#tempo)
    * [Arquivo Processado](#fluxo)
  * [Métricas](#métricas)
    * [Arquivo Processado](#adquirente-fluxo-1)


# Atributos

## Adquirente

Neste atributo deverá ser descrito a informação de **adquirente** do usuário.

  Campo     | Descrição
----------- | ------------------
codigoAdquirente | Codígo identificador da adquirente.
nomeAdquirente | Nome da adquirente.


_Para facilitar em sua consulta utilize o guia de [adquirentes](docTabelaAuxiliar.md#tabela-de-adquirentes)._


## Tempo

Neste atributo é possível enxergar as diversas informações de tempo do cubo.

A dimensão tempo pode ser dividida em duas categorias:

  Dimensão  | Descrição
  --------- | ----------------------------------------------------
  TempoProcessamento | Dimensão voltada para uma análise temporal dos processamentos dos arquivos.
  PeriodoInicial | Dimensão voltada para uma análise temporal do movimento inicial.
  PeriodoFinal | Dimensão voltada para uma análise temporal do movimento final.

Os atirbutos abaixos são utilizados para compor a analise estabelecida anteriormente (Venda ou pagamento).

  Campo     | Descrição
----------- | ------------------
diaData | Data informada no formato AAAA/MM/DD  
nomeDia | Nome do dia da semana.
numeroDoAno | Número do ano.
dataCompleta | Data completa no formato DD/MM/AAAA
numeroDiaDaSemana | Número do dia da semana. (Exemplo: Segunda-feira = Day 1 e Sexta-feira = Day 5)
nomeMes | Nome do mês.
numeroMes | Número do mês.
nomeDaSemanaDoMes | Nome da semana do mês.
nomeTrimestreDoAno | Nome do trimestre do ano.
nomeSemana | Nome da semana.
nomeTrimestre | Nome do trimestre.
codigoSemana | Código da semana.


## Arquivo Processado (Atributos da fato)

Abaixo seguem os atributos e suas respectivas descrições para melhor leitura do arquivo processado.


Campo     |    Descrição
--------- | ---------------------------------------------
nomeArquivoEdi | Nome identificador do arquivo.
estabelecimentoMatriz |  Número do estabelecimento matriz de extrato eletrônico.
sequencia | Número sequencial do arquivo. Nos casos de retroativo, este dado será enviado como 9999999.
opcaoExtrato | Categoria do tipo de extrato.
transmissao | Tipo de transmissão do arquivo (se refere a adquirente)
caixaPostal | Caixa postal.
versaoLayout | Constante “014”.

# Métricas

## Arquivo Processado

Abaixo seguem os descritivos das métricas da tabela de adquirente fluxo.

Campo     |    Descrição
--------- | --------------------------------
totalRegistro | Total registro.
numeroTransacoesCanceladas | Número de transações canceladas.
numeroTransacoesPagas | Número de transações pagas.
numeroCancelamentosDescontados | Número de cancelamentos descontados.
numeroChargebacks | Número de contestações.
numeroEstornosChargeback | Número de estornos de contestações.

_Ir para a [documentação de introdução](index.md)._
 
 <!-- END graphql-markdown -->