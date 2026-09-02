# Dados - SmartShop AI

## 1. Base de Dados

O SmartShop AI utiliza o dataset **Online Retail**, disponibilizado pelo **UCI Machine Learning Repository**.

A base contém registros de transações de uma empresa de varejo online do Reino Unido, com informações sobre produtos, quantidades, preços, clientes, datas das compras e países.

O dataset possui **541.909 registros** e, no arquivo utilizado no projeto, **8 colunas**.

## 2. Origem da Base

**Nome:** Online Retail

**Fonte:** UCI Machine Learning Repository

**Link:** https://archive.ics.uci.edu/dataset/352/online+retail

**Licença:** CC BY 4.0

**Data de acesso:** 30/08/2026

**Forma de obtenção:** Base disponibilizada pela fonte original e carregada no projeto por meio do Python.

A base contém transações realizadas entre 01/12/2010 e 09/12/2011.

## 3. Dicionário de Dados

| Variável | Descrição | Tipo | Unidade / Valores possíveis | Entrada ou Saída? |
|---|---|---|---|---|
| InvoiceNo | Número da compra/fatura | Categórica nominal | Código da compra | Entrada |
| StockCode | Código do produto | Categórica nominal | Código do produto | Entrada |
| Description | Nome do produto | Categórica nominal | Texto | Entrada |
| Quantity | Quantidade comprada | Numérica discreta | Número de unidades | Entrada |
| InvoiceDate | Data e hora da compra | Temporal | Data e horário | Entrada |
| UnitPrice | Preço unitário | Numérica contínua | Valor em libra (£) | Entrada |
| CustomerID | Identificação do cliente | Categórica nominal | Código do cliente | Entrada |
| Country | País do cliente | Categórica nominal | Nome do país | Entrada |

### Observação sobre InvoiceDate

No carregamento inicial realizado no Python, `InvoiceDate` foi identificado como `object`. Apesar disso, seu significado é de data e hora da compra. A coluna deverá ser convertida para um formato adequado de data/hora durante o tratamento dos dados.

## 4. Entradas e Saída Esperada

O SmartShop AI é um projeto de **recomendação de produtos**.

### Entradas

As principais informações utilizadas serão:

- CustomerID;
- StockCode;
- Description;
- Quantity;
- InvoiceDate;
- UnitPrice;
- Country.

O `InvoiceNo` também poderá ser utilizado para identificar as transações e os cancelamentos.

### Saída esperada

A saída esperada não existe pronta na base original.

O sistema deverá gerar uma **lista ou ranking de produtos recomendados para cada cliente**, utilizando os padrões encontrados no histórico de compras.

### Exemplo

**Entrada:**
Histórico de compras de um cliente.

**Saída:**
Ranking de produtos que podem ser relevantes para esse cliente.

## 5. Primeira Exploração dos Dados

A primeira análise foi realizada utilizando Python e teve como objetivo compreender a estrutura da base e identificar possíveis problemas de qualidade.

Foram analisados:

- quantidade de registros e variáveis;
- valores ausentes;
- registros duplicados;
- quantidade de valores únicos;
- tipos das variáveis;
- quantidade de produtos, clientes e países;
- valores de quantidade e preço;
- produtos mais frequentes.

## 6. Medidas Estatísticas

| Variável | Média | Mediana | Desvio padrão | Mínimo | Máximo |
|---|---:|---:|---:|---:|---:|
| Quantity | 9,55 | 3,00 | 218,08 | -80.995 | 80.995 |
| UnitPrice | 4,61 | 2,08 | 96,76 | -11.062,06 | 38.970 |

Os resultados mostram uma grande variação nos valores de `Quantity` e `UnitPrice`. A diferença entre média e mediana e os valores extremos indicam a presença de registros que precisam ser investigados antes da utilização dos dados no modelo.

## 7. Visualização Inicial

Foi analisada a frequência dos produtos presentes na base.

Os cinco produtos com maior frequência foram:

1. WHITE HANGING HEART T-LIGHT HOLDER — 2.369
2. REGENCY CAKESTAND 3 TIER — 2.200
3. JUMBO BAG RED RETROSPOT — 2.159
4. PARTY BUNTING — 1.727
5. LUNCH BAG RED RETROSPOT — 1.638

A visualização mostra que alguns produtos aparecem com frequência muito maior que outros, indicando concentração das transações em determinados itens. Esse padrão poderá ser considerado posteriormente na construção do sistema de recomendação.

## 8. Primeiras Observações

A análise inicial mostrou:

- 541.909 registros;
- 8 variáveis;
- 4.070 produtos diferentes;
- 4.372 clientes identificados;
- 38 países;
- 5.268 linhas totalmente duplicadas;
- 135.080 registros sem CustomerID;
- 1.454 registros sem Description;
- 10.624 registros com Quantity menor ou igual a zero;
- 2.517 registros com UnitPrice menor ou igual a zero;
- 9.288 registros identificados como cancelamentos.

Esses problemas serão analisados e tratados nas próximas etapas antes da construção do modelo de recomendação.

## 9. Fonte

Chen, D. (2015). **Online Retail**. UCI Machine Learning Repository.

DOI: https://doi.org/10.24432/C5BW33

Fonte oficial:
https://archive.ics.uci.edu/dataset/352/online+retail
