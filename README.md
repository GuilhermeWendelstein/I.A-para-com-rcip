# Sistema Inteligente de Recomendação de Produtos

## Descrição do Problema

Atualmente, muitas lojas virtuais exibem os mesmos produtos para todos os clientes, sem considerar seus interesses, preferências ou histórico de compras. Essa abordagem reduz a personalização da experiência de compra, dificultando que os consumidores encontrem produtos relevantes de forma rápida e eficiente.

Como consequência, muitos clientes deixam de adquirir produtos que poderiam ser de seu interesse, aumentando a taxa de abandono da plataforma e reduzindo as vendas do comércio eletrônico. Esse problema afeta principalmente pequenas e médias lojas, que muitas vezes não possuem ferramentas inteligentes para personalizar as recomendações oferecidas aos seus usuários.

O projeto propõe o desenvolvimento de um sistema de recomendação de produtos utilizando Inteligência Artificial. A solução será capaz de analisar dados de compras e comportamento dos clientes para identificar padrões de consumo e sugerir produtos personalizados.

## Público / Contexto

O projeto é voltado para lojas virtuais de pequeno e médio porte que desejam oferecer recomendações personalizadas aos seus clientes.

O sistema será utilizado durante a navegação dos consumidores na plataforma de vendas, apresentando sugestões de produtos com base no histórico de compras ou em padrões identificados no comportamento de clientes semelhantes.

## Por que é tratável com IA?

O problema é adequado para a aplicação de Inteligência Artificial porque envolve a identificação de padrões em dados de compras e comportamento dos clientes. Esses padrões podem ser difíceis de identificar manualmente, principalmente quando existe uma grande quantidade de produtos e clientes.

Algoritmos de recomendação podem analisar esses dados para identificar quais produtos costumam ser adquiridos em conjunto e quais clientes apresentam comportamentos semelhantes. Com isso, o sistema poderá utilizar essas informações para gerar recomendações de produtos mais relevantes.

No Google Colab são utilizadas bibliotecas de Python para analisar os dados e desenvolver o modelo de recomendação. O sistema utiliza dados públicos, sem utilizar informações pessoais reais dos usuários.

## Tipo de Problema

O projeto se encaixa principalmente no tipo de **recomendação**, pois seu objetivo é sugerir produtos que podem ser relevantes para cada cliente.

O sistema poderá analisar informações sobre histórico de compras e comportamento dos usuários para encontrar padrões e gerar recomendações personalizadas.

## Entradas e Saídas Esperadas

**Entradas:**

- Histórico de compras dos clientes;
- Produtos comprados;
- Código dos produtos;
- Descrição dos produtos;
- Quantidade comprada;
- Data da compra;
- Preço unitário;
- País do cliente.

**Saídas:**

- Lista de produtos recomendados;
- Ranking dos produtos mais relevantes para cada cliente.

**Exemplo:** Entrada: histórico de compras de um cliente. Saída: uma lista de produtos que podem ser interessantes para esse cliente.

## Soluções Disponíveis

**Amazon**

A Amazon utiliza sistemas de recomendação para apresentar produtos de acordo com os interesses e o comportamento dos clientes. A proposta é semelhante por também utilizar informações dos usuários para oferecer sugestões personalizadas.

**Recombee**

A Recombee oferece soluções de recomendação utilizando Inteligência Artificial e dados de comportamento dos usuários para gerar sugestões personalizadas. A diferença é que o projeto será desenvolvido como um protótipo acadêmico utilizando Python e Google Colab.

## Limitações Iniciais

Uma das principais limitações pode ser a qualidade e quantidade dos dados disponíveis. Caso o conjunto de dados possua informações incompletas ou poucos registros de determinados clientes ou produtos, as recomendações podem ser menos precisas.

Outra limitação é o caso de novos usuários ou produtos. Quando ainda não existem dados suficientes sobre eles, pode ser difícil identificar quais produtos são mais adequados para recomendação.

## Abordagens de IA

### Tabela Comparativa

| Abordagem | Como funcionaria no projeto | Vantagens | Desvantagens | Viabilidade no semestre |
|---|---|---|---|---|
| Aprendizado de Máquina | Analisa os dados de compras e comportamento dos clientes para identificar padrões e gerar recomendações. | Consegue encontrar padrões nos dados e gerar recomendações personalizadas. | Depende da quantidade e qualidade dos dados disponíveis. | Alta, utilizando Python e Google Colab. |
| Sistemas Especialistas | Utiliza regras definidas manualmente para recomendar produtos. | Simples de entender, desenvolver e testar. | Exige a criação manual de muitas regras e possui menor flexibilidade. | Alta, porém com um sistema mais limitado. |

## Abordagem Escolhida

A abordagem escolhida para o projeto é o **Aprendizado de Máquina**.

Essa escolha foi feita porque o principal problema do projeto é encontrar padrões nos dados de compras e comportamento dos clientes para gerar recomendações.

Em vez de criar manualmente uma regra para cada combinação de produtos, o modelo poderá analisar os dados e identificar quais produtos costumam aparecer relacionados nas compras.

Além disso, o uso de Python e Google Colab torna essa abordagem viável dentro do prazo do semestre.

## Regras suficientes?

Uma solução baseada somente em regras seria possível, mas não seria suficiente para atender completamente ao objetivo do projeto.

Por exemplo, seria possível criar uma regra como "se o cliente comprar um celular, recomendar uma capinha". Porém, conforme aumenta a quantidade de produtos e clientes, seria necessário criar e atualizar muitas regras manualmente.

Por isso, o Aprendizado de Máquina é adequado ao projeto, pois pode encontrar padrões nos dados sem que todas as relações precisem ser cadastradas manualmente.

# Base de Dados

A base utilizada é a **Online Retail**, disponibilizada pelo UCI Machine Learning Repository.

A base possui inicialmente:

- 541.909 registros;
- 8 colunas;
- Período de 01/12/2010 a 09/12/2011;
- 4.070 produtos;
- 4.372 clientes;
- 38 países.

Fonte oficial:

https://archive.ics.uci.edu/dataset/352/online+retail

DOI:

https://doi.org/10.24432/C5BW33

## Diagnóstico da Base

Durante o diagnóstico foram identificados:

- 135.080 valores ausentes em `CustomerID`;
- 1.454 valores ausentes em `Description`;
- 5.268 linhas totalmente duplicadas;
- 10.624 registros com `Quantity <= 0`;
- 2.517 registros com `UnitPrice <= 0`;
- 9.288 registros de cancelamento;
- 4.070 produtos diferentes;
- 4.372 clientes diferentes;
- 38 países diferentes.

A repetição de `InvoiceNo` não foi considerada duplicação automaticamente, pois uma mesma compra pode possuir vários produtos.

## Limpeza e Preparação

A etapa de limpeza e preparação foi realizada com base nos problemas identificados durante o diagnóstico.

Foram realizadas as seguintes ações:

- remoção de registros sem `CustomerID`;
- remoção de duplicatas exatas;
- conversão de `InvoiceDate` para o tipo de data;
- remoção de registros de cancelamento;
- tratamento de registros com `Quantity` ou `UnitPrice` não positivos;
- verificação de valores ausentes após o tratamento;
- verificação de duplicatas após o tratamento;
- salvamento da base tratada separadamente.

A base original foi preservada e as transformações foram realizadas sobre uma cópia dos dados.

## Resultado da Limpeza

A base original possuía:

- **541.909 linhas**
- **8 colunas**

Após a limpeza e preparação:

- **392.692 linhas**
- **8 colunas**

A base final não apresenta valores ausentes nas colunas verificadas e não apresenta duplicatas restantes.

## Tabela de Decisões

| Transformação | Coluna afetada | Motivo | Impacto | Risco |
|---|---|---|---|---|
| Remoção de valores ausentes | `CustomerID` | Necessário para relacionar as compras aos clientes | Redução do número de registros | Perda de compras que não possuem identificação de cliente |
| Remoção de duplicatas | Todas | Evitar registros exatamente repetidos | Redução do número de registros | Possível remoção de uma repetição legítima, por isso apenas duplicatas exatas foram removidas |
| Conversão de tipo | `InvoiceDate` | Permitir o tratamento correto da data | Sem alteração na quantidade de linhas ou colunas | Datas inválidas poderiam causar problemas no processamento |
| Remoção de cancelamentos | `InvoiceNo` | Trabalhar com compras válidas para as recomendações | Redução do número de registros | Perda de informações sobre cancelamentos |
| Tratamento de valores não positivos | `Quantity` e `UnitPrice` | Evitar que valores incompatíveis com compras normais sejam utilizados no modelo | Redução do número de registros | Alguns valores podem representar devoluções ou ajustes legítimos |
| Padronização de categorias | `Country` / `StockCode` | Não foi identificada necessidade de alteração nesta etapa | Sem alteração | Necessidades futuras poderão ser avaliadas durante a modelagem |
| Codificação | Variáveis categóricas | Será definida de acordo com o modelo escolhido | Sem alteração nesta etapa | Poderá ser necessária posteriormente |
| Escalonamento | Variáveis numéricas | Depende do algoritmo utilizado na modelagem | Sem alteração nesta etapa | Poderá ser necessário posteriormente |

### Comparação Geral da Base

| Situação | Linhas | Colunas |
|---|---:|---:|
| Antes da limpeza | 541.909 | 8 |
| Depois da limpeza | 392.692 | 8 |

## Data Leakage

Foi realizada uma verificação para evitar vazamento de dados.

As transformações realizadas nesta etapa não utilizaram informações do resultado futuro do modelo.

Também não foi realizado ajuste de parâmetros de transformação utilizando um conjunto completo antes da separação entre treino e teste.

As colunas `InvoiceNo` e `CustomerID` não serão utilizadas diretamente como características do modelo. O `CustomerID` permanece na base tratada para permitir o relacionamento entre clientes e compras.

Na etapa de modelagem, qualquer transformação que aprenda parâmetros dos dados, como codificação ou escalonamento quando necessário, deverá ser ajustada utilizando somente os dados de treinamento.

# Artefatos do Projeto

## Caderno da Atividade 8

O notebook foi executado do início ao fim, com as células processadas e os resultados finais verificados.

[🔗 Abrir Caderno da Atividade 8 no Google Colab](https://colab.research.google.com/drive/10ObqzV4xG1I7mYuFZ3TnwXEO8lgIKQ2_?usp=sharing)

## Base tratada

A base final foi salva separadamente como:

`dados_tratados.csv`

Dimensões da base tratada:

**392.692 linhas × 8 colunas**

O arquivo foi carregado novamente após o salvamento para verificar se a base foi armazenada corretamente.

## Diagnóstico

O diagnóstico da qualidade dos dados foi realizado antes da etapa de limpeza, permitindo identificar os principais problemas da base e definir as transformações necessárias.

# Escopo Atualizado

Até o momento, o projeto possui:

- definição do problema como recomendação;
- definição do Aprendizado de Máquina como abordagem;
- escolha da base Online Retail;
- diagnóstico da qualidade dos dados;
- limpeza e preparação da base;
- verificação dos dados após o tratamento;
- salvamento da base tratada;
- verificação do arquivo salvo;
- registro das decisões de tratamento;
- verificação de possíveis problemas de vazamento de dados;
- definição das características utilizadas no primeiro modelo;
- criação de um alvo para classificação binária;
- separação dos dados em treinamento e teste;
- criação de um baseline;
- treinamento de uma Árvore de Decisão;
- realização de previsões;
- avaliação e comparação dos resultados do modelo com o baseline;
- avaliação das métricas de classificação;
- análise da matriz de confusão;
- análise de possíveis sinais de overfitting;
- verificação de duplicação de clientes;
- verificação de possíveis fontes de vazamento de dados;
- escolha do recall como métrica principal da classe "Comprou novamente";
- preparação dos slides de esboço da Atividade 10.

## Primeiro Modelo de Machine Learning

### Atividade 9

Na etapa de modelagem, foi utilizado o conjunto de dados tratado na Atividade 8.

Para o primeiro modelo, o problema foi estruturado como uma classificação binária. O objetivo é identificar se um cliente realizará uma nova compra em um período futuro.

As características utilizadas foram:

- quantidade total de produtos comprados;
- preço médio das compras;
- quantidade de pedidos realizados;
- país do cliente;
- recência, calculada a partir da última compra do cliente antes da data de corte.

O `CustomerID` não foi utilizado como característica do modelo, sendo mantido apenas para identificar os clientes durante a preparação dos dados.

Foi utilizada uma divisão de 80% dos dados para treinamento e 20% para teste, com `stratify` para manter a proporção das classes. A separação temporal já havia sido realizada na construção do problema, utilizando compras anteriores à data de corte para criar as características e compras posteriores para definir o alvo.

Como baseline, foi utilizada a classe majoritária, que apresentou acurácia de **61,61%**.

O primeiro modelo escolhido foi uma **Árvore de Decisão**, por ser um modelo simples de interpretar e adequado para um primeiro teste de classificação.

A primeira Árvore de Decisão, com profundidade máxima 5, apresentou acurácia de **72,40%**, ficando **10,79 pontos percentuais acima do baseline**.

Também foi testada uma segunda Árvore de Decisão, com profundidade máxima 3, que apresentou acurácia de **72,27%**. Os resultados das duas árvores ficaram próximos.

Além da acurácia, foram analisadas a precisão e o recall da primeira árvore. O modelo apresentou **78,67% de precisão** e **38,56% de recall** para a classe "Comprou novamente".

Durante o desenvolvimento, a variável `Pais` foi agrupada em duas categorias: **Reino Unido** e **Outros**, reduzindo a quantidade de variáveis geradas para o modelo.

A transformação da variável categórica foi realizada somente depois da separação entre treino e teste, evitando utilizar informações do conjunto de teste na preparação do treinamento.

As previsões foram comparadas com os valores reais no notebook, permitindo verificar o comportamento do modelo no conjunto de teste.

### Atividade 10 — Avaliação do modelo

Na Atividade 10, foi realizada uma avaliação mais detalhada da primeira Árvore de Decisão utilizando o conjunto de teste.

Os principais resultados foram:

- **Acurácia no treino:** 72,15%;
- **Acurácia no teste:** 72,40%;
- **Diferença entre treino e teste:** aproximadamente -0,25 ponto percentual;
- **Baseline:** 61,61%;
- **Acurácia da Árvore de Decisão:** 72,40%;
- **Precision da classe "Comprou novamente":** 78,67%;
- **Recall da classe "Comprou novamente":** 38,56%;
- **F1-score da classe "Comprou novamente":** 52%.

O relatório de classificação apresentou os seguintes resultados:

| Classe | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| Não comprou novamente | 71% | 93% | 81% | 491 |
| Comprou novamente | 78,67% | 38,56% | 52% | 306 |

A matriz de confusão apresentou:

| | Predito: Não | Predito: Sim |
|---|---:|---:|
| **Real: Não** | 459 | 32 |
| **Real: Sim** | 188 | 118 |

Os valores representam:

- **459 verdadeiros negativos:** clientes que não compraram novamente e foram classificados corretamente;
- **32 falsos positivos:** clientes classificados como compradores, mas que não realizaram uma nova compra;
- **188 falsos negativos:** clientes que realizaram uma nova compra, mas foram classificados como não compradores;
- **118 verdadeiros positivos:** clientes que realizaram uma nova compra e foram classificados corretamente.

### Métrica principal

A métrica principal escolhida foi o **recall da classe "Comprou novamente"**.

Essa escolha está relacionada ao objetivo de identificar clientes que realmente realizam uma nova compra. Um falso negativo representa um cliente que voltou a comprar, mas não foi identificado pelo modelo, podendo representar uma oportunidade não identificada para uma ação de relacionamento ou marketing.

Por outro lado, um falso positivo representa um cliente classificado como possível comprador, mas que não realizou uma nova compra, podendo resultar em uma ação de marketing desnecessária.

### Teste de overfitting

Foi realizada uma comparação entre o desempenho do modelo nos dados de treino e nos dados de teste.

Os resultados foram:

- **Treino:** 72,15%;
- **Teste:** 72,40%;
- **Diferença:** aproximadamente -0,25 ponto percentual.

Como os desempenhos ficaram muito próximos, não foi observado um sinal evidente de overfitting.

O fato de a acurácia no teste ter ficado ligeiramente acima da acurácia no treino não indica, por si só, um problema de generalização. A diferença é muito pequena e pode ocorrer devido à divisão dos dados.

### Verificação de possíveis vazamentos de dados

Foi verificada a possibilidade de vazamento de dados no modelo.

As características dos clientes foram calculadas utilizando somente as compras realizadas antes da data de corte de novembro de 2011. O alvo foi construído utilizando o período posterior ao corte.

Dessa forma, as informações utilizadas nas características não incluem diretamente a resposta que o modelo precisa prever.

Também foi verificada a existência de clientes duplicados no conjunto utilizado para a modelagem. Foram encontrados **0 clientes duplicados** entre os **3.985 registros**.

A divisão entre treino e teste foi realizada depois da construção das características e do alvo. Como a temporalidade já foi considerada na construção do problema, cada linha representa um cliente com informações do passado e um alvo referente ao futuro. Por isso, foi utilizada uma divisão aleatória estratificada entre treino e teste.

Além disso, a transformação da variável `Pais` foi realizada somente após a divisão entre treino e teste, evitando que as categorias do conjunto de teste fossem utilizadas para definir a transformação do conjunto de treinamento.

Com essas verificações, não foi identificado um problema evidente de vazamento de dados ou duplicação de clientes que explique o resultado obtido.

# Próximos Passos

Para as próximas etapas do projeto, os próximos passos serão:

- analisar possíveis melhorias nas características utilizadas;
- avaliar outras configurações ou modelos de Machine Learning;
- continuar avaliando o comportamento das previsões;
- aprimorar o modelo de recomendação;
- avaliar a qualidade das recomendações;
- documentar os resultados finais;
- desenvolver o algoritmo de recomendação de produtos a partir dos padrões identificados;
- preparar a apresentação final da AP2.

## Riscos

A qualidade das recomendações dependerá da quantidade e qualidade dos dados disponíveis.

Também existe o risco de clientes ou produtos possuírem poucas informações, dificultando a identificação de padrões.

Outro ponto é que a base representa uma empresa específica de varejo online. Portanto, os padrões encontrados podem não representar todos os consumidores de comércio eletrônico.

# Lista de Pendências Atualizada

- [x] Criar o repositório no GitHub.
- [x] Buscar possíveis conjuntos de dados de e-commerce.
- [x] Definir o tipo de problema como recomendação.
- [x] Pesquisar soluções semelhantes.
- [x] Comparar possíveis abordagens de IA.
- [x] Definir o Aprendizado de Máquina como abordagem escolhida.
- [x] Analisar o conjunto de dados escolhido.
- [x] Realizar o tratamento e limpeza dos dados.
- [x] Executar o notebook do início ao fim.
- [x] Verificar os resultados finais da limpeza.
- [x] Salvar a base tratada.
- [x] Verificar a base tratada após o salvamento.
- [x] Registrar as decisões de tratamento.
- [x] Verificar possíveis problemas de vazamento de dados.
- [x] Definir as características utilizadas no primeiro modelo.
- [x] Criar o alvo para classificação binária.
- [x] Separar os dados em treinamento e teste.
- [x] Criar e avaliar o baseline.
- [x] Treinar a primeira Árvore de Decisão.
- [x] Realizar previsões e comparar com os valores reais.
- [x] Comparar o modelo com o baseline.
- [x] Adicionar a variável de recência.
- [x] Agrupar os países em `Reino Unido` e `Outros`.
- [x] Ajustar a transformação das variáveis categóricas para ocorrer após a separação entre treino e teste.
- [x] Testar uma segunda Árvore de Decisão com profundidade diferente.
- [x] Avaliar precisão e recall do modelo principal.
- [x] Avaliar accuracy, precision, recall e F1-score.
- [x] Gerar e interpretar a matriz de confusão.
- [x] Escolher e justificar a métrica principal.
- [x] Avaliar possível overfitting.
- [x] Verificar duplicação de clientes.
- [x] Verificar possíveis fontes de vazamento de dados.
- [x] Preparar o esboço dos slides da Atividade 10.
- [x] Preparar a apresentação dos resultados.
- [ ] Aprimorar o modelo de recomendação.
- [ ] Testar outros modelos de Machine Learning, quando aplicável.
- [ ] Avaliar a qualidade das recomendações.
- [ ] Documentar os resultados finais.
- [ ] Desenvolver o algoritmo de recomendação de produtos.
