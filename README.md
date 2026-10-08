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
- treinamento e avaliação de Árvores de Decisão;
- análise de precisão, recall e F1-score;
- geração e interpretação da matriz de confusão;
- diagnóstico de overfitting;
- verificação de vazamento de dados após a preparação do modelo;
- preparação dos resultados para a apresentação da AP2.

## Primeiro Modelo de Machine Learning

### Atividade 9

Na etapa inicial de modelagem, o problema foi estruturado como uma classificação binária. O objetivo é identificar se um cliente realizará uma nova compra em um período futuro.

As características utilizadas foram:

- quantidade total de produtos comprados;
- preço médio das compras;
- quantidade de pedidos realizados;
- país do cliente;
- recência, calculada a partir da última compra do cliente antes da data de corte.

O `CustomerID` não foi utilizado como característica do modelo, sendo mantido apenas para identificar os clientes durante a preparação dos dados.

Foi utilizada uma separação temporal para construir o problema, utilizando compras anteriores à data de corte para criar as características e compras posteriores para definir o alvo.

Depois dessa separação temporal, os dados dos clientes foram divididos em 80% para treinamento e 20% para teste, utilizando `stratify` para manter a proporção das classes.

Como baseline, foi utilizada a classe majoritária, que apresentou acurácia de **61,61%**.

O primeiro modelo utilizado foi uma **Árvore de Decisão**, por ser simples de interpretar e adequada para uma avaliação inicial do problema.

A versão revisada da Árvore de Decisão, com profundidade máxima 5, apresentou acurácia de **72,40%**, ficando **10,79 pontos percentuais acima do baseline**.

Também foi testada uma segunda Árvore de Decisão, com profundidade máxima 3, que apresentou acurácia de **72,27%**.

Durante a revisão do modelo, foram adicionadas a variável de recência e o agrupamento dos países em **Reino Unido** e **Outros**. A transformação da variável categórica `Pais` também passou a ser realizada somente depois da divisão entre treino e teste.

## Atividade 10 — Avaliação do modelo

Na Atividade 10, foi realizada uma avaliação mais completa da Árvore de Decisão de profundidade 5, buscando compreender não apenas a acurácia, mas também os tipos de erros cometidos pelo modelo.

As principais métricas analisadas foram:

- **Acurácia:** 72,40%;
- **Precisão da classe "Comprou novamente":** 78,67%;
- **Recall da classe "Comprou novamente":** 38,56%;
- **F1-score da classe "Comprou novamente":** 0,52.

A matriz de confusão apresentou:

- **459 verdadeiros negativos**;
- **32 falsos positivos**;
- **188 falsos negativos**;
- **118 verdadeiros positivos**.

A comparação com o baseline mostrou que a Árvore de Decisão apresentou desempenho superior:

| Modelo | Acurácia |
|---|---:|
| Baseline | 61,61% |
| Árvore de Decisão — profundidade 5 | 72,40% |
| Árvore de Decisão — profundidade 3 | 72,27% |

Portanto, o modelo principal supera o baseline e conseguiu aprender padrões úteis para diferenciar clientes que comprariam novamente daqueles que não comprariam.

### Interpretação dos resultados

A acurácia de **72,40%** mostra que o modelo apresentou desempenho superior ao baseline de **61,61%**.

Porém, a acurácia sozinha não representa completamente o comportamento do modelo. Para a classe **"Comprou novamente"**, a precisão foi de **78,67%**, enquanto o recall foi de apenas **38,56%**.

Isso indica que, quando o modelo prevê que um cliente comprará novamente, existe uma boa proporção de acertos. Por outro lado, o modelo deixa de identificar uma parte considerável dos clientes que realmente voltam a comprar.

Por esse motivo, o **recall da classe "Comprou novamente"** foi escolhido como a principal métrica. No contexto do projeto, um falso negativo representa um cliente que realmente voltaria a comprar, mas não foi identificado. Esse erro pode representar uma oportunidade perdida de relacionamento ou de marketing.

Já o falso positivo representa um cliente que o modelo considera como possível comprador novamente, mas que não realiza uma nova compra. Nesse caso, uma ação de marketing poderia ser realizada sem gerar o retorno esperado.

A principal limitação atual do modelo é justamente o número de falsos negativos: **188 clientes que realmente compraram novamente não foram identificados pelo modelo**.

### Overfitting

Foi realizada uma comparação entre o desempenho no conjunto de treino e no conjunto de teste.

| Conjunto | Acurácia |
|---|---:|
| Treino | 72,15% |
| Teste | 72,40% |

A diferença foi de aproximadamente **-0,25 ponto percentual**.

Os resultados ficaram muito próximos e não indicaram um sinal evidente de overfitting. O modelo não apresentou uma diferença grande entre o desempenho no treinamento e no teste.

### Verificação de vazamento de dados

Foi realizada uma verificação para evitar vazamento de dados durante a preparação e avaliação do modelo.

As duplicatas exatas foram removidas anteriormente, durante a etapa de limpeza da base, antes da divisão dos dados utilizados na modelagem.

Também foi respeitada a ordem cronológica do problema. As características foram calculadas somente com compras anteriores à data de corte, enquanto o alvo foi criado utilizando compras posteriores. Dessa forma, informações do futuro não foram utilizadas diretamente nas características do modelo.

Depois da separação temporal entre passado e futuro, os clientes foram divididos em 80% para treinamento e 20% para teste com `stratify`.

A transformação da variável `Pais` foi realizada somente depois da divisão entre treino e teste, evitando utilizar informações do conjunto de teste na transformação do treinamento.

O `CustomerID` não foi utilizado como característica e nenhuma das variáveis utilizadas entrega diretamente a resposta futura.

Na verificação realizada, não foram encontrados clientes duplicados entre os **3.985 registros utilizados na modelagem**.

Com essas verificações, não foi identificado um problema evidente de vazamento de dados que explique o resultado obtido.

## Próximos Passos

Para a continuidade do projeto até a entrega final do semestre, os próximos passos serão:

- investigar formas de aumentar o recall da classe "Comprou novamente";
- avaliar a necessidade de novos ajustes nas características utilizadas;
- testar outros modelos de Machine Learning, quando aplicável;
- avaliar a qualidade das previsões e recomendações;
- desenvolver a etapa de recomendação de produtos a partir dos padrões identificados;
- documentar os resultados finais do projeto.

## Riscos e Limitações

A qualidade das recomendações dependerá da quantidade e qualidade dos dados disponíveis.

O modelo atual ainda possui recall relativamente baixo para a classe "Comprou novamente", deixando 188 clientes que realmente recompraram sem identificação.

Também existe o risco de clientes possuírem poucas informações históricas, dificultando a identificação de padrões.

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
- [x] Avaliar precisão, recall e F1-score.
- [x] Gerar e interpretar a matriz de confusão.
- [x] Escolher e justificar a métrica principal.
- [x] Comparar treino e teste para avaliar overfitting.
- [x] Verificar possíveis problemas de vazamento de dados.
- [x] Preparar os resultados para a AP2.
- [x] Atualizar o notebook da Atividade 10.
- [x] Preparar os slides da AP2.
- [ ] Adicionar `dados_tratados.csv` ao repositório.
- [ ] Adicionar `Limpeza.ipynb` ao repositório.
- [ ] Adicionar as figuras exportadas ao repositório.
- [ ] Testar possíveis melhorias no recall.
- [ ] Avançar para a etapa de recomendação de produtos.
- [ ] Avaliar a qualidade das recomendações.
- [ ] Documentar os resultados finais.
- [ ] Desenvolver o algoritmo de recomendação de produtos.
