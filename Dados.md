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

Nesta primeira análise foram observadas algumas informações básicas da base, como:

- Quantidade de registros;
- Quantidade de produtos;
- Quantidade de clientes;
- Produtos mais frequentes;
- Valores de quantidade;
- Valores dos preços.

Também foram calculadas medidas estatísticas das variáveis numéricas:

- Média;
- Desvio padrão;
- Valor mínimo;
- Valor máximo.

Para as variáveis categóricas foram observadas as frequências dos valores mais comuns.

## Medidas Estatísticas

A primeira análise da base apresentou os seguintes resultados:

| Variável | Média | Desvio padrão | Mínimo | Máximo |
|---|---:|---:|---:|---:|
| Quantity | 9,55 | 218,08 | -80.995 | 80.995 |
| UnitPrice | 4,61 | 96,76 | -11.062,06 | 38.970 |

Os resultados mostram uma grande variação na quantidade de produtos e nos preços. A presença de valores negativos também chama atenção, principalmente em `Quantity` e `UnitPrice`, indicando que existem registros que precisam ser analisados nas próximas etapas.

## Visualização Inicial

Foi utilizado um **gráfico de barras** mostrando os produtos que aparecem com maior frequência na base.

O gráfico ajuda a visualizar quais produtos possuem maior quantidade de registros e permite observar quais itens aparecem com mais frequência nas compras.

**Interpretação:** o gráfico mostra que alguns produtos aparecem muito mais vezes que outros na base. Esses produtos mais frequentes podem indicar itens com maior procura ou recorrência de compra. Essa informação pode ser útil para o SmartShop AI, pois os produtos mais frequentes podem aparecer com maior relevância nas análises e nas futuras recomendações.

## Primeiras Observações sobre a Base

Durante a análise inicial foram identificados alguns pontos que precisam de atenção:

- Existem valores negativos em `Quantity`;
- Existem valores negativos em `UnitPrice`;
- Algumas informações podem estar ausentes, principalmente relacionadas aos clientes;
- Alguns produtos aparecem com muito mais frequência que outros;
- Os dados ainda não passaram por uma limpeza completa.

Esses pontos serão analisados e tratados nas próximas etapas do projeto, antes do desenvolvimento do modelo de recomendação.

## Dicionário e Análise

O dicionário de dados e a análise inicial foram documentados neste arquivo.

O código utilizado para a exploração, as medidas estatísticas e a visualização está disponível no notebook do projeto no **Google Colab**.

## Fonte dos Dados

A base utilizada no projeto é o dataset **Online Retail**, disponibilizado pelo **UCI Machine Learning Repository**:

[Online Retail - UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail)
