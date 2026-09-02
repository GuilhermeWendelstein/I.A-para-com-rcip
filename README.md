# SmartShop AI

## Sistema Inteligente de Recomendação de Produtos

## Sobre o projeto

O SmartShop AI é um projeto de Inteligência Artificial voltado para a recomendação de produtos em ambientes de comércio eletrônico.

O objetivo é utilizar padrões presentes no histórico de compras para gerar recomendações mais relevantes para os clientes.

## Problema

Muitas lojas virtuais apresentam produtos de forma pouco personalizada, dificultando que o cliente encontre itens relacionados aos seus interesses e ao seu histórico de compras.

O projeto busca utilizar dados de transações para identificar padrões de comportamento e apoiar recomendações personalizadas.

## Tipo de problema

**Recomendação de produtos.**

### Entradas

- CustomerID
- StockCode
- Description
- Quantity
- InvoiceDate
- UnitPrice
- Country

### Saída esperada

Uma lista ou ranking de produtos que podem ser relevantes para cada cliente.

## Abordagem

A abordagem planejada utiliza padrões de compra e relações de similaridade entre produtos e clientes.

Como alternativa, poderiam ser utilizadas regras fixas, como:

> "Clientes que compraram X também recebem Y."

Porém, regras fixas possuem menor capacidade de adaptação aos diferentes padrões encontrados nos dados.

A abordagem baseada em dados permite identificar relações presentes no histórico de compras e utilizá-las para gerar recomendações.

**Importante:** nesta etapa do projeto, nenhum modelo foi treinado ainda.

## Base de dados

O projeto utiliza o dataset real **Online Retail**, disponibilizado pelo **UCI Machine Learning Repository**.

- Registros: 541.909
- Colunas no DataFrame: 8
- Licença: CC BY 4.0
- Período: 01/12/2010 a 09/12/2011

Fonte:
https://archive.ics.uci.edu/dataset/352/online+retail

## Documentação

### Dados e dicionário

[Dados.md](Dados.md)

Contém a origem da base, dicionário de dados, variáveis de entrada e saída e primeira exploração.

### Diagnóstico da qualidade

[diagnóstico_qualidade.md](diagnóstico_qualidade.md)

Contém os problemas encontrados, gravidade, tratamentos previstos e possíveis vieses.

### Notebook

[Notebook do projeto](COLOQUE_AQUI_O_LINK_DO_SEU_COLAB)

O notebook contém o código utilizado para carregar e analisar a base, incluindo os resultados da primeira exploração e o diagnóstico inicial.

### Apresentação AP1

[AP1 - Apresentação](AP1_SeuNome.pdf)

## Primeira análise

A análise inicial identificou:

- 5.268 duplicatas exatas;
- 135.080 registros sem CustomerID;
- 1.454 registros sem Description;
- 10.624 registros com Quantity <= 0;
- 2.517 registros com UnitPrice <= 0;
- 9.288 cancelamentos.

Esses problemas serão tratados nas próximas etapas do projeto.

## Próximos passos

1. Tratamento e limpeza dos dados;
2. Análise exploratória mais aprofundada;
3. Preparação dos dados para recomendação;
4. Desenvolvimento da abordagem de recomendação;
5. Treinamento e testes;
6. Avaliação dos resultados.

## Uso de Inteligência Artificial Generativa

Ferramentas de Inteligência Artificial Generativa foram utilizadas como apoio na organização dos conteúdos, revisão textual e preparação da apresentação.

As decisões técnicas, análise dos dados e conteúdo apresentado foram revisados e compreendidos pelo autor.
