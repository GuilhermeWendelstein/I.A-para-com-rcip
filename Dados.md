# Dados - SmartShop AI

## Base de Dados

Para o SmartShop AI será utilizado o dataset **Online Retail**, disponibilizado pelo UCI Machine Learning Repository.

A base possui informações sobre compras realizadas em uma loja de varejo online, incluindo produtos, quantidade comprada, preço, cliente, data da compra e país.

A base será utilizada para analisar padrões de compra que poderão ser utilizados posteriormente no sistema de recomendação de produtos.

## Origem da Base

**Nome:** Online Retail

**Fonte:** UCI Machine Learning Repository

**Link:** [Online Retail - UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail)

**Licença:** CC BY 4.0

**Data de acesso:** 20/08/2026

**Forma de obtenção:** Download da base disponibilizada pela fonte original.

## Dicionário de Dados

| Variável | Descrição | Tipo | Unidade / Valores possíveis | Entrada ou Saída? | Observações |
|---|---|---|---|---|---|
| InvoiceNo | Número da compra/fatura | Categórica nominal | Código da compra | Entrada | Identifica uma transação |
| StockCode | Código do produto | Categórica nominal | Código do produto | Entrada | Identifica o produto |
| Description | Nome do produto | Categórica nominal | Texto | Entrada | Descrição do produto |
| Quantity | Quantidade comprada | Numérica discreta | Número de unidades | Entrada | Quantidade de itens da compra |
| InvoiceDate | Data e hora da compra | Categórica nominal | Data e horário | Entrada | Indica quando a compra aconteceu |
| UnitPrice | Preço unitário | Numérica contínua | Valor em libra (£) | Entrada | Preço de uma unidade |
| CustomerID | Identificação do cliente | Categórica nominal | Código do cliente | Entrada | Identifica o cliente |
| Country | País do cliente | Categórica nominal | Nome do país | Entrada | País relacionado à compra |

## Variáveis de Entrada e Saída

As principais variáveis de entrada utilizadas pelo SmartShop AI serão os dados relacionados aos clientes, produtos e compras.

**Entradas:**
- CustomerID;
- StockCode;
- Description;
- Quantity;
- InvoiceDate;
- UnitPrice;
- Country.

Como o projeto é de **recomendação**, a base não possui uma variável de saída pronta.

**Saída esperada:**

Uma lista de produtos recomendados para cada cliente, baseada nos padrões encontrados no histórico de compras.

**Exemplo:**

Entrada: histórico de compras de um cliente.

Saída: produtos que podem ser interessantes para esse cliente.

## Primeira Exploração dos Dados

Nesta primeira análise serão observadas algumas informações básicas da base, como:

- Quantidade de registros;
- Quantidade de produtos;
- Quantidade de clientes;
- Produtos mais frequentes;
- Valores de quantidade;
- Valores dos preços.

Também serão calculadas algumas medidas estatísticas das variáveis numéricas:

- Média;
- Desvio padrão;
- Valor mínimo;
- Valor máximo.

Para as variáveis categóricas serão observadas as frequências dos valores mais comuns.

## Medidas Estatísticas

A primeira análise da base apresentou os seguintes resultados:

| Variável | Média | Desvio padrão | Mínimo | Máximo |
|---|---:|---:|---:|---:|
| Quantity | 9,55 | 218,08 | -80.995 | 80.995 |
| UnitPrice | 4,61 | 96,76 | -11.062,06 | 38.970 |

Esses valores mostram que existe uma grande variação tanto na quantidade de produtos quanto nos preços. Também existem valores negativos, que deverão ser analisados e tratados nas próximas etapas do projeto.

## Visualização Inicial

Será utilizado um gráfico de barras mostrando os produtos que aparecem com maior frequência na base.

O objetivo do gráfico é facilitar a visualização dos produtos mais presentes nos registros de compras e ajudar a entender melhor o comportamento dos dados.

A visualização permite identificar quais produtos aparecem com maior frequência na base. Esses produtos possuem uma quantidade maior de registros de compra e podem indicar itens com maior procura. Essa informação poderá ser útil posteriormente no SmartShop AI, pois a frequência dos produtos pode ajudar na identificação de padrões e na geração de recomendações para os clientes.

## Observações

Esta é uma primeira exploração da base. Os dados ainda não foram completamente limpos ou tratados.

Nesta atividade, o objetivo é conhecer a base, documentar suas variáveis e realizar uma análise inicial. O tratamento e a limpeza dos dados serão realizados nas próximas etapas do projeto.

Durante a análise inicial, também foram identificados valores negativos nas variáveis **Quantity** e **UnitPrice**. Esses valores precisam ser investigados para verificar se estão relacionados a cancelamentos, devoluções ou outras situações presentes na base.

Também será importante verificar possíveis valores ausentes e registros que não sejam relevantes para o desenvolvimento do sistema de recomendação. Essas verificações serão realizadas durante as próximas etapas de tratamento dos dados.
