# Sistema Inteligente de Recomendação de Produtos

## Descrição do Problema

Atualmente, muitas lojas virtuais exibem os mesmos produtos para todos os clientes, sem considerar seus interesses, preferências ou histórico de compras. Essa abordagem reduz a personalização da experiência de compra, dificultando que os consumidores encontrem produtos relevantes de forma rápida e eficiente.

Como consequência, muitos clientes deixam de adquirir produtos que poderiam ser de seu interesse, aumentando a taxa de abandono da plataforma e reduzindo as vendas do comércio eletrônico. Esse problema afeta principalmente pequenas e médias lojas, que muitas vezes não possuem ferramentas inteligentes para personalizar as recomendações oferecidas aos seus usuários.

O projeto propõe o desenvolvimento de um sistema inteligente de recomendação de produtos utilizando Inteligência Artificial. A proposta é analisar dados de compras dos clientes para identificar padrões de consumo, perfis semelhantes e oportunidades de personalização.

Até o momento, foram desenvolvidas etapas de análise exploratória, segmentação de clientes com K-means e modelos de classificação para prever a possibilidade de recompra. Essas etapas representam a base analítica do projeto, mas ainda não constituem um mecanismo automático de recomendação de produtos.

## Público / Contexto

O projeto é voltado para lojas virtuais de pequeno e médio porte que desejam oferecer recomendações personalizadas aos seus clientes.

A proposta é utilizar informações do histórico de compras para compreender os comportamentos dos consumidores e, futuramente, apresentar sugestões de produtos com base nos padrões identificados.

## Por que é tratável com IA?

O problema é adequado para a aplicação de Inteligência Artificial porque envolve a identificação de padrões em dados de compras e comportamento dos clientes.

Algoritmos de Machine Learning podem analisar grandes quantidades de registros para identificar comportamentos semelhantes, padrões de consumo e relações entre características dos clientes.

No projeto, foram utilizados algoritmos de classificação e agrupamento para investigar o comportamento dos consumidores. Essas análises podem servir como base para o desenvolvimento futuro de um sistema de recomendação.

O desenvolvimento utiliza Python e Google Colab, com bibliotecas de análise de dados e Machine Learning.

## Tipo de Problema

O objetivo final do projeto é a recomendação de produtos.

Entretanto, a implementação atual também envolve dois problemas de Machine Learning:

- **Classificação:** prever se um cliente realizará uma nova compra em um período futuro.
- **Agrupamento:** identificar perfis de clientes com características de compra semelhantes.

É importante destacar que prever uma recompra não significa identificar qual produto deve ser recomendado. A implementação de um algoritmo específico de recomendação continua sendo uma etapa futura.

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

**Saídas esperadas para a proposta final:**

- Lista de produtos recomendados;
- Ranking dos produtos mais relevantes para cada cliente.

**Saídas dos modelos atualmente implementados:**

- Previsão de possibilidade de recompra;
- Classificação dos clientes em relação à recompra futura;
- Segmentação dos clientes em grupos com comportamentos semelhantes;
- Métricas e análises sobre o desempenho dos modelos.

## Soluções Disponíveis

**Amazon**

A Amazon utiliza sistemas de recomendação para apresentar produtos de acordo com os interesses e o comportamento dos clientes. A proposta é semelhante por também utilizar informações dos usuários para oferecer sugestões personalizadas.

**Recombee**

A Recombee oferece soluções de recomendação utilizando Inteligência Artificial e dados de comportamento dos usuários para gerar sugestões personalizadas.

A diferença é que o projeto será desenvolvido como um protótipo acadêmico utilizando Python e Google Colab.

## Limitações Iniciais

Uma das principais limitações pode ser a qualidade e quantidade dos dados disponíveis. Caso o conjunto de dados possua informações incompletas ou poucos registros de determinados clientes ou produtos, as análises podem ser menos precisas.

Outra limitação é o caso de novos usuários ou produtos. Quando ainda não existem dados suficientes sobre eles, pode ser difícil identificar quais produtos seriam adequados para recomendação.

Além disso, a base utilizada representa uma empresa específica de varejo online e um período histórico limitado, entre 2010 e 2011. Portanto, os padrões encontrados podem não representar todos os consumidores de comércio eletrônico atualmente.

## Abordagens de IA

### Tabela Comparativa

| Abordagem | Como funcionaria no projeto | Vantagens | Desvantagens | Viabilidade no semestre |
|---|---|---|---|---|
| Aprendizado de Máquina | Analisa os dados de compras e comportamento dos clientes para identificar padrões e gerar recomendações. | Consegue encontrar padrões nos dados e gerar recomendações personalizadas. | Depende da quantidade e qualidade dos dados disponíveis. | Alta, utilizando Python e Google Colab. |
| Sistemas Especialistas | Utiliza regras definidas manualmente para recomendar produtos. | Simples de entender, desenvolver e testar. | Exige a criação manual de muitas regras e possui menor flexibilidade. | Alta, porém com um sistema mais limitado. |

## Abordagem Escolhida

A abordagem escolhida para o projeto é o **Aprendizado de Máquina**.

Essa escolha foi feita porque o principal problema do projeto é encontrar padrões nos dados de compras e comportamento dos clientes para gerar recomendações.

Em vez de criar manualmente uma regra para cada combinação de produtos, os modelos podem analisar os dados e identificar padrões de comportamento.

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

**Fonte oficial:**

https://archive.ics.uci.edu/dataset/352/online+retail

**DOI:**

https://doi.org/10.24432/C5BW33

**Licença dos dados:** CC BY 4.0 (Creative Commons Attribution 4.0 International).

A licença permite o compartilhamento e a adaptação dos dados, desde que seja fornecida a atribuição adequada à fonte original.

Essa licença refere-se à base de dados Online Retail, não representando automaticamente a licença do código desenvolvido neste projeto.

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

- Remoção de registros sem `CustomerID`;
- Remoção de duplicatas exatas;
- Conversão de `InvoiceDate` para o tipo de data;
- Remoção de registros de cancelamento;
- Tratamento de registros com `Quantity` ou `UnitPrice` não positivos;
- Verificação de valores ausentes após o tratamento;
- Verificação de duplicatas após o tratamento;
- Salvamento da base tratada separadamente.

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
| Remoção de valores ausentes | `CustomerID` | Necessário para relacionar as compras aos clientes | Redução do número de registros | Perda de compras sem identificação de cliente |
| Remoção de duplicatas | Todas | Evitar registros exatamente repetidos | Redução do número de registros | Possível remoção de uma repetição legítima, por isso apenas duplicatas exatas foram removidas |
| Conversão de tipo | `InvoiceDate` | Permitir o tratamento correto da data | Sem alteração na quantidade de linhas ou colunas | Datas inválidas poderiam causar problemas no processamento |
| Remoção de cancelamentos | `InvoiceNo` | Trabalhar com compras válidas | Redução do número de registros | Perda de informações sobre cancelamentos |
| Tratamento de valores não positivos | `Quantity` e `UnitPrice` | Evitar valores incompatíveis com compras normais | Redução do número de registros | Alguns valores podem representar devoluções ou ajustes legítimos |

### Comparação Geral da Base

| Situação | Linhas | Colunas |
|---|---:|---:|
| Antes da limpeza | 541.909 | 8 |
| Depois da limpeza | 392.692 | 8 |

## Data Leakage

Foi realizada uma verificação para evitar vazamento de dados.

As transformações realizadas nesta etapa não utilizaram informações do resultado futuro do modelo.

Também foi respeitada a ordem cronológica do problema: as características foram calculadas utilizando compras anteriores à data de corte, enquanto o alvo foi criado utilizando compras posteriores.

As colunas `InvoiceNo` e `CustomerID` não são utilizadas diretamente como características dos modelos. O `CustomerID` permanece na base tratada para permitir o relacionamento entre clientes e compras.

Na etapa de modelagem, transformações que aprendem parâmetros dos dados, como escalonamento, são ajustadas utilizando somente os dados de treinamento quando aplicável.

# Dicionário de Variáveis

A base Online Retail possui oito colunas principais:

| Variável | Descrição | Tipo |
|---|---|---|
| `InvoiceNo` | Identificador da fatura ou pedido. Registros iniciados com C indicam cancelamentos. | Texto |
| `StockCode` | Código de identificação do produto. | Texto |
| `Description` | Descrição ou nome do produto. | Texto |
| `Quantity` | Quantidade de unidades compradas em uma linha da fatura. | Numérico |
| `InvoiceDate` | Data e horário em que a compra foi realizada. | Data e hora |
| `UnitPrice` | Preço unitário do produto em libras esterlinas. | Numérico |
| `CustomerID` | Identificador do cliente. | Numérico/identificador |
| `Country` | País associado ao cliente. | Texto |

Durante a preparação para a modelagem, algumas variáveis foram transformadas ou agrupadas.

As características utilizadas no primeiro classificador foram:

| Característica | Descrição |
|---|---|
| `QuantidadeTotal` | Quantidade total de produtos comprados pelo cliente no período anterior à data de corte. |
| `PrecoMedio` | Preço médio dos produtos comprados pelo cliente. |
| `QuantidadePedidos` | Quantidade de pedidos realizados pelo cliente. |
| `Pais` | Agrupamento do país em Reino Unido ou Outros. |
| `Recencia` | Tempo em dias desde a última compra do cliente até a data de corte. |

A variável alvo indica se o cliente realizou uma nova compra no período posterior à data de corte.

# Artefatos do Projeto

## Caderno da Atividade 8

O notebook foi executado do início ao fim, com as células processadas e os resultados finais verificados.

[🔗 Abrir Caderno da Atividade 8 no Google Colab](https://colab.research.google.com/drive/10ObqzV4xG1I7mYuFZ3TnwXEO8lgIKQ2_?usp=sharing)

## Base tratada

A base final foi salva separadamente como:

`dados_tratados.csv`

Dimensões da base tratada:

**392.692 linhas × 8 colunas**

O arquivo será disponibilizado no repositório para facilitar a reprodução dos experimentos.

## Diagnóstico

O diagnóstico da qualidade dos dados foi realizado antes da etapa de limpeza, permitindo identificar os principais problemas da base e definir as transformações necessárias.

# Escopo Atualizado

Até o momento, o projeto possui:

- Definição do problema como recomendação de produtos;
- Definição do Aprendizado de Máquina como abordagem;
- Escolha da base Online Retail;
- Diagnóstico da qualidade dos dados;
- Limpeza e preparação da base;
- Verificação dos dados após o tratamento;
- Salvamento e verificação da base tratada;
- Registro das decisões de tratamento;
- Verificação de possíveis problemas de vazamento de dados;
- Definição das características utilizadas nos modelos;
- Criação de um alvo para classificação binária;
- Separação dos dados em treinamento e teste;
- Criação de um baseline;
- Treinamento e avaliação de Árvores de Decisão;
- Treinamento e avaliação de uma rede neural MLP;
- Análise de precisão, recall e F1-score;
- Geração e interpretação de matrizes de confusão;
- Diagnóstico de overfitting;
- Segmentação de clientes com K-means;
- Análise de perfis e taxas de recompra futura;
- Testes de diferentes limiares de classificação;
- Auditoria de desempenho por país;
- Análise de falsos negativos;
- Documentação das limitações dos modelos.

## Primeiro Modelo de Machine Learning

### Atividade 9

Na etapa inicial de modelagem, o problema foi estruturado como uma classificação binária. O objetivo é identificar se um cliente realizará uma nova compra em um período futuro.

As características utilizadas foram:

- Quantidade total de produtos comprados;
- Preço médio das compras;
- Quantidade de pedidos realizados;
- País do cliente;
- Recência, calculada a partir da última compra do cliente antes da data de corte.

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
- **F1-score da classe "Comprou novamente":** 0,5175.

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

### Interpretação dos resultados

A acurácia de **72,40%** mostra que o modelo apresentou desempenho superior ao baseline de **61,61%**.

Porém, a acurácia sozinha não representa completamente o comportamento do modelo. Para a classe "Comprou novamente", a precisão foi de **78,67%**, enquanto o recall foi de **38,56%**.

Isso indica que, quando o modelo prevê que um cliente comprará novamente, existe uma boa proporção de acertos. Por outro lado, o modelo deixa de identificar uma parte considerável dos clientes que realmente voltam a comprar.

Por esse motivo, o **recall da classe "Comprou novamente"** foi escolhido como uma das principais métricas. No contexto do projeto, um falso negativo representa um cliente que realmente voltaria a comprar, mas não foi identificado. Esse erro pode representar uma oportunidade perdida de relacionamento ou de marketing.

Já o falso positivo representa um cliente que o modelo considera como possível comprador novamente, mas que não realiza uma nova compra. Nesse caso, uma ação de marketing poderia ser realizada sem gerar o retorno esperado.

A principal limitação inicial do modelo foi justamente o número de falsos negativos: **188 clientes que realmente compraram novamente não foram identificados pelo modelo**.

### Overfitting

Foi realizada uma comparação entre o desempenho no conjunto de treino e no conjunto de teste.

| Conjunto | Acurácia |
|---|---:|
| Treino | 72,15% |
| Teste | 72,40% |

A diferença foi de aproximadamente **-0,25 ponto percentual**.

Os resultados ficaram muito próximos e não indicaram um sinal evidente de overfitting nesta execução.

### Verificação de vazamento de dados

Foi realizada uma verificação para evitar vazamento de dados durante a preparação e avaliação do modelo.

As duplicatas exatas foram removidas anteriormente, durante a etapa de limpeza da base.

Também foi respeitada a ordem cronológica do problema. As características foram calculadas somente com compras anteriores à data de corte, enquanto o alvo foi criado utilizando compras posteriores.

Depois da separação temporal entre passado e futuro, os clientes foram divididos em 80% para treinamento e 20% para teste com `stratify`.

A transformação da variável `Pais` foi realizada somente depois da divisão entre treino e teste.

O `CustomerID` não foi utilizado como característica e nenhuma das variáveis utilizadas entrega diretamente a resposta futura.

Na verificação realizada, não foram encontrados clientes duplicados entre os **3.985 registros utilizados na modelagem**.

## Atividade 12 — Análise complementar com agrupamento

### Objetivo

A Atividade 12 complementa o classificador supervisionado desenvolvido anteriormente com uma análise exploratória de perfis de clientes.

A pergunta investigada foi se existem grupos de clientes com comportamentos de compra diferentes e se esses perfis apresentam diferenças na recompra futura.

A análise utiliza **K-means** e não substitui o modelo de classificação nem constitui, por si só, um algoritmo de recomendação de produtos.

### Arquivos da atividade

- [Notebook da Atividade 12 — análise complementar](Atividade12_Analise_Complementar.ipynb)
- Base tratada utilizada pelo notebook: `dados_tratados.csv`

O notebook contém as etapas de preparação, comparação do número de grupos, visualizações, interpretação dos perfis e discussão das limitações.

### Metodologia

A análise parte da base tratada, com **392.692 registros e 8 colunas**, que contém **4.338 clientes identificados**.

Para preservar a lógica temporal do projeto, foi utilizado o percentil 80 das datas como ponto de corte:

- **Data de corte:** 01/11/2011 15:55;
- **Registros anteriores ao corte:** 314.183;
- **Registros posteriores ao corte:** 78.509;
- **Clientes utilizados na segmentação:** 3.985.

As características dos clientes foram calculadas somente com compras anteriores ao corte. Foram utilizadas quatro variáveis: quantidade total comprada, preço médio, quantidade de pedidos e recência.

Foi aplicada transformação `log1p` à quantidade total, ao preço médio e ao número de pedidos; em seguida, as quatro características foram padronizadas com `StandardScaler`.

A presença do cliente no período posterior foi usada somente depois da formação dos grupos, para descrever a recompra futura e comparar os perfis.

### Escolha do número de grupos

Foram comparadas soluções de **2 a 6 grupos**, usando a inércia (método do cotovelo) e o coeficiente de silhueta.

| Número de grupos (k) | Coeficiente de silhueta |
|---:|---:|
| 2 | 0,312 |
| 3 | 0,300 |
| 4 | 0,307 |
| 5 | 0,260 |
| 6 | 0,257 |

Foi escolhida a solução com **k = 4** para a exploração dos perfis, priorizando a possibilidade de interpretar quatro grupos no contexto do negócio.

Essa escolha não significa que k=4 seja matematicamente superior: a maior silhueta observada foi a de k=2. A decisão deve, portanto, ser entendida como exploratória e sujeita a revisão.

### Resultados dos grupos

| Grupo | Clientes | Média de pedidos | Recência média (dias) | Taxa de recompra futura |
|---|---:|---:|---:|---:|
| 0 | 916 | 1,35 | 233,12 | 19,54% |
| 1 | 1.021 | 9,62 | 32,99 | 69,44% |
| 2 | 290 | 1,78 | 126,87 | 22,76% |
| 3 | 1.758 | 2,05 | 49,77 | 32,76% |

### Interpretação e valor para o projeto

Os grupos apresentaram diferenças nas características de volume comprado, preço médio, frequência de pedidos e recência.

A taxa de recompra futura também variou entre os grupos, indicando que a segmentação pode ajudar a formular hipóteses sobre o comportamento dos clientes e possíveis estratégias de relacionamento.

Esse resultado complementa o classificador supervisionado ao resumir perfis comportamentais, em vez de apenas prever se um cliente fará uma nova compra.

Entretanto, as diferenças observadas são descritivas: não demonstram causalidade, não provam que uma campanha terá resultado e não identificam diretamente qual produto deve ser recomendado.

### Limitações

- O K-means é sensível às variáveis selecionadas, à escala dos dados e ao número de grupos.
- Os valores de silhueta foram modestos; k=2 apresentou o maior resultado entre as soluções testadas.
- A transformação logarítmica reduz, mas não elimina, a influência de valores extremos.
- O preço médio não representa o gasto total do cliente.
- O indicador de recompra verifica somente se o cliente aparece no período futuro; não mede o valor gasto, a quantidade comprada nem a satisfação.
- A base representa um período histórico limitado, de 2010 a 2011.
- Os nomes atribuídos aos perfis são interpretações humanas simplificadas, não categorias produzidas automaticamente pelo algoritmo.
- A segmentação ainda não é um sistema de recomendação de produtos e não comprova aumento de vendas.

### Conclusão da Atividade 12

A análise encontrou quatro perfis exploratórios e diferenças de comportamento entre eles, incluindo variações na taxa de recompra futura.

A segmentação pode ser utilizada como ponto de partida para novas investigações e para complementar a análise supervisionada já realizada.

Antes de transformar esses resultados em ações comerciais, será necessário validar os perfis e avaliar as recomendações em uma etapa própria.

## Atividade 13 — Experimento com rede neural

### Objetivo

A Atividade 13 amplia os experimentos de Machine Learning do SmartShop AI com uma rede neural para prever se um cliente realizará uma nova compra.

O modelo é comparado ao baseline e à Árvore de Decisão de profundidade 5, utilizando a mesma divisão entre treino e teste.

### Arquivos da atividade

- [Notebook da Atividade 13 — experimento com rede neural](Atividade13_SmartShopAI.ipynb)
- Base tratada utilizada pelo notebook: `dados_tratados.csv`

### Metodologia

Foi utilizado o `MLPClassifier`, da biblioteca scikit-learn, com duas camadas ocultas contendo 16 e 8 neurônios, respectivamente, e função de ativação ReLU.

A rede neural foi implementada em um `Pipeline` com `StandardScaler`. Dessa forma, a padronização é ajustada utilizando somente os dados de treinamento e depois aplicada ao conjunto de teste.

O treinamento foi configurado para até 500 iterações, com `early_stopping=True` e `n_iter_no_change=20`.

A comparação utiliza os mesmos conjuntos de treino e teste empregados na avaliação da Árvore de Decisão.

### Resultados

Os resultados registrados no notebook foram:

| Modelo | Acurácia | Precisão da classe positiva | Recall da classe positiva | F1-score da classe positiva |
|---|---:|---:|---:|---:|
| Baseline | 61,61% | 0,00% | 0,00% | 0,0000 |
| Árvore de Decisão — profundidade 5 | 72,40% | 78,67% | 38,56% | 0,5175 |
| Rede neural MLP — camadas (16, 8) | 73,40% | 73,98% | 47,39% | 0,5777 |

Nesta execução, a rede neural apresentou acurácia de **73,40%**, enquanto a Árvore de Decisão apresentou **72,40%** e o baseline, **61,61%**.

O recall da classe positiva aumentou de **38,56%** na Árvore de Decisão para **47,39%** na rede neural, uma diferença de **8,83 pontos percentuais**.

A precisão da rede neural foi de **73,98%**, abaixo dos **78,67%** da Árvore de Decisão.

O F1-score da rede neural foi de **0,5777**, superior ao valor de **0,5175** da Árvore de Decisão.

### Desempenho no treino e no teste

| Conjunto | Acurácia | Precisão da classe positiva | Recall da classe positiva | F1-score da classe positiva |
|---|---:|---:|---:|---:|
| Treino | 71,68% | 71,49% | 43,63% | 0,5419 |
| Teste | 73,40% | 73,98% | 47,39% | 0,5777 |

As métricas do conjunto de teste ficaram próximas ou acima das métricas de treino nesta execução. Isso não indica um sinal evidente de overfitting no experimento registrado, mas não comprova que o problema esteja ausente em outras divisões dos dados.

### Convergência e dificuldades técnicas

A rede neural foi treinada em **61 iterações**, dentro do limite máximo de 500. Nesta execução, não foi emitido `ConvergenceWarning`.

A opção `early_stopping=True` permitiu interromper o treinamento antes de atingir o limite máximo de iterações.

Uma decisão técnica importante foi utilizar o `StandardScaler` dentro do `Pipeline`, garantindo que os parâmetros da padronização fossem aprendidos apenas com os dados de treino.

### Interpretação dos resultados

Nesta divisão dos dados, a rede neural apresentou resultados melhores que a Árvore de Decisão em acurácia, recall e F1-score da classe positiva.

Uma hipótese técnica é que a rede neural tenha conseguido aprender combinações não lineares entre as características utilizadas para representar os clientes. Entretanto, essa explicação é uma hipótese, não uma causa comprovada pelos resultados.

Apesar da melhora, o recall ficou em **47,39%**, o que significa que o modelo ainda não identifica mais da metade dos clientes que realmente voltam a comprar.

### Decisão sobre o uso no projeto final

A rede neural será mantida como candidata para o projeto final, sem descartar a Árvore de Decisão.

O MLP apresentou resultados superiores nesta execução para acurácia, recall e F1-score. Entretanto, a Árvore de Decisão continua sendo uma alternativa mais simples de interpretar e apresentou maior precisão para a classe positiva.

A decisão definitiva deverá considerar novos experimentos, a estabilidade das métricas e o impacto dos falsos positivos e falsos negativos no contexto do negócio.

Também é importante destacar que prever a recompra de um cliente não equivale, por si só, a recomendar produtos específicos.

### Limitações

- A comparação foi realizada com uma única divisão de treino e teste.
- Foi avaliada uma configuração inicial da rede neural, sem uma busca extensa de hiperparâmetros.
- O recall da rede neural ainda é inferior a 50%.
- A rede neural é menos interpretável do que a Árvore de Decisão.
- Os resultados não garantem desempenho semelhante em outros períodos ou em outras bases de clientes.
- O experimento prevê recompra, mas não recomenda diretamente produtos específicos.

### Conclusão da Atividade 13

A rede neural MLP, utilizando `StandardScaler` e as mesmas divisões de treino e teste da Árvore de Decisão, apresentou acurácia de **73,40%** e recall de **47,39%** para a classe "Comprou novamente".

Os resultados foram superiores aos da Árvore de Decisão nesta execução, principalmente na identificação de clientes que voltam a comprar.

A rede neural será mantida como candidata para o projeto final, enquanto a Árvore de Decisão continuará como referência interpretável.

## Atividade 14 — Análise de aplicação real de IA

[Ver análise do sistema de recomendação da Amazon](Atividade14.md)

## Atividade 15 — Relatório Crítico Final

[🔗 Acessar o Relatório Crítico Final](Atividade15_Relatorio_Critico_Final.md)

# Experimentos complementares e auditoria dos modelos

## Teste de limiar da Árvore de Decisão

Na avaliação inicial, a Árvore de Decisão utilizava o limiar padrão de 0,50 para classificar os clientes.

Como o recall da classe positiva era relativamente baixo, foram testados diferentes limiares de decisão para investigar o impacto sobre as métricas.

O experimento mostrou que a alteração do limiar modifica o equilíbrio entre precisão e recall.

| Limiar | Acurácia | Precisão | Recall | F1-score |
|---:|---:|---:|---:|---:|
| 0,50 | 72,40% | 78,67% | 38,56% | 0,5175 |
| 0,40 | 71,64% | 64,18% | 59,15% | 0,6156 |

Com o limiar de **0,40**, o recall aumentou de **38,56% para 59,15%**, enquanto a precisão diminuiu de **78,67% para 64,18%**.

O F1-score também aumentou, passando de **0,5175 para 0,6156**.

Esse resultado mostra que o limiar pode ser ajustado de acordo com o objetivo do negócio. Se a prioridade for identificar mais clientes com possibilidade de recompra, um limiar menor pode ser interessante, mesmo que aumente a quantidade de falsos positivos.

Entretanto, esse experimento foi realizado no conjunto de teste e deve ser entendido como exploratório. Em uma avaliação mais rigorosa, o limiar deve ser escolhido utilizando um conjunto de validação separado, preservando o teste para a avaliação final.

## Auditoria de desempenho por país

Foi realizada uma análise para verificar se o desempenho do classificador apresentava diferenças entre os grupos de países utilizados na modelagem.

A variável `Pais` foi agrupada em duas categorias:

- Reino Unido;
- Outros.

A auditoria utilizou as previsões da Árvore de Decisão com o limiar padrão de 0,50.

| Grupo | Clientes no teste | Positivos reais | Verdadeiros positivos | Falsos negativos | Recall |
|---|---:|---:|---:|---:|---:|
| Reino Unido | 730 | 284 | 107 | 177 | 37,68% |
| Outros | 67 | 22 | 11 | 11 | 50,00% |

O conjunto completo possuía 386 clientes classificados como Outros, mas somente 67 desses clientes estavam presentes no conjunto de teste.

O recall observado foi maior no grupo Outros. Entretanto, esse grupo possui uma quantidade menor de clientes no teste, o que exige cautela na interpretação.

A diferença observada não comprova que o país seja a causa do desempenho diferente. Ela indica que vale a pena continuar investigando o comportamento dos modelos entre os grupos.

A análise também mostra a importância de verificar o desempenho dos modelos em diferentes segmentos, em vez de considerar somente uma métrica geral.

## Análise de falsos negativos e agrupamentos

Os falsos negativos representam clientes que realizaram uma nova compra no período futuro, mas não foram identificados pelo classificador.

Na análise complementar, esses erros foram investigados em relação aos grupos formados pelo K-means.

Foi observado que os perfis de clientes apresentavam taxas de recompra diferentes. O grupo 1, por exemplo, apresentou taxa de recompra futura de 69,44%, enquanto o grupo 0 apresentou 19,54%.

Esse cruzamento permite investigar se determinados perfis concentram mais oportunidades de melhoria para o classificador.

Entretanto, a associação entre grupos e erros não significa que o K-means cause os erros de classificação. A análise é exploratória e não demonstra causalidade.

# Resultados obtidos

Foram realizados experimentos utilizando K-means, Decision Tree e MLPClassifier.

| Modelo | Acurácia | Precisão | Recall | F1-score |
|---|---:|---:|---:|---:|
| Baseline | 61,61% | 0,00% | 0,00% | 0,0000 |
| Decision Tree — limiar 0,50 | 72,40% | 78,67% | 38,56% | 0,5175 |
| Decision Tree — limiar 0,40 | 71,64% | 64,18% | 59,15% | 0,6156 |
| MLPClassifier | 73,40% | 73,98% | 47,39% | 0,5777 |

O MLPClassifier apresentou a maior acurácia entre os modelos comparados. Entretanto, a Árvore de Decisão com limiar 0,40 apresentou o maior recall e F1-score da classe positiva.

A escolha do modelo depende do objetivo da aplicação:

- Se a prioridade for maior precisão, a árvore com limiar 0,50 apresentou o melhor resultado.
- Se a prioridade for identificar mais clientes que realmente recompram, a árvore com limiar 0,40 apresentou o maior recall.
- Se a prioridade for manter uma alternativa com desempenho geral competitivo, o MLP apresentou a maior acurácia.

Os resultados foram obtidos em uma única divisão de treino e teste e não devem ser interpretados como garantia de desempenho futuro.

# Limitações conhecidas

- A base representa um único contexto comercial.
- Existem registros sem identificação de cliente, removidos durante a preparação.
- O MLPClassifier ainda apresenta recall limitado.
- A escolha de quatro clusters precisa de justificativa comercial mais aprofundada.
- O grupo Outros possui uma quantidade menor de clientes no conjunto de teste, exigindo cautela na auditoria.
- Os resultados dos modelos foram obtidos em uma única divisão de treino e teste.
- O ajuste de limiar foi exploratório e precisa ser validado em dados separados.
- O arquivo de dados tratados precisa estar disponível para facilitar a reprodução dos experimentos.
- O projeto ainda não possui um mecanismo automático de recomendação de produtos.

# Próximas melhorias

- Aprofundar a análise dos segmentos encontrados pelo K-means.
- Investigar a distribuição dos falsos negativos entre os clusters.
- Realizar validações adicionais e auditoria de desempenho por grupos.
- Avaliar o limiar dos modelos utilizando um conjunto de validação.
- Investigar características adicionais que possam melhorar as previsões.
- Implementar um algoritmo específico de recomendação de produtos.
- Avaliar a qualidade das recomendações com métricas apropriadas.
- Documentar os resultados finais do projeto.

# Como executar o projeto

O projeto utiliza Python e notebooks Jupyter/Google Colab.

## Requisitos

- Python;
- Google Colab ou ambiente Jupyter;
- Bibliotecas de análise de dados e Machine Learning.

As principais bibliotecas utilizadas incluem:

- pandas;
- numpy;
- matplotlib;
- seaborn;
- scikit-learn;
- openpyxl.

## Execução

1. Acesse o repositório do projeto no GitHub.
2. Abra o notebook que deseja executar.
3. No Google Colab, carregue o notebook.
4. Disponibilize o arquivo `dados_tratados.csv` no ambiente quando o notebook exigir essa base.
5. Execute as células na ordem apresentada.
6. Confira as saídas e métricas geradas.

A base tratada será adicionada ao repositório para facilitar a reprodução dos experimentos.

# Estrutura do Projeto

Os principais arquivos e notebooks do projeto são:

| Arquivo | Descrição |
|---|---|
| `Limpeza(4).ipynb` | Diagnóstico, limpeza e preparação da base de dados. |
| `Modelo_Atividade9.ipynb` | Desenvolvimento inicial do modelo de classificação. |
| `Avaliação.ipynb` | Avaliação do modelo e análise das métricas. |
| `Atividade12_Analise_Complementar.ipynb` | Segmentação de clientes com K-means. |
| `Atividade13_SmartShopAI_(2).ipynb` | Experimento com rede neural e análises complementares. |
| `Atividade14.md` | Análise de uma aplicação real de Inteligência Artificial. |
| `Atividade15_Relatorio_Critico_Final.md` | Relatório crítico final do projeto. |

Os nomes dos arquivos devem corresponder aos arquivos efetivamente presentes no repositório.

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
- [x] Comparar o modelo com o baseline.
- [x] Adicionar a variável de recência.
- [x] Agrupar os países em Reino Unido e Outros.
- [x] Ajustar a transformação das variáveis categóricas para ocorrer após a separação entre treino e teste.
- [x] Testar uma segunda Árvore de Decisão com profundidade diferente.
- [x] Avaliar precisão, recall e F1-score.
- [x] Gerar e interpretar a matriz de confusão.
- [x] Comparar treino e teste para avaliar overfitting.
- [x] Preparar os resultados para a AP2.
- [x] Realizar análise complementar com K-means.
- [x] Comparar diferentes quantidades de grupos.
- [x] Interpretar os perfis de clientes.
- [x] Treinar e avaliar uma rede neural MLP.
- [x] Comparar os resultados entre os modelos.
- [x] Testar diferentes limiares da Árvore de Decisão.
- [x] Realizar auditoria de desempenho por país.
- [x] Investigar falsos negativos em relação aos clusters.
- [x] Preparar o relatório crítico final.
- [x] Documentar as limitações dos modelos.
- [ ] Adicionar a base `dados_tratados.csv` ao repositório.
- [ ] Conferir a execução dos notebooks após disponibilizar a base.
- [ ] Exportar e adicionar as figuras finais ao repositório, se necessário.
- [ ] Implementar um algoritmo específico de recomendação de produtos.
- [ ] Avaliar a qualidade das recomendações.
- [ ] Documentar os resultados finais da recomendação.

## Declaração de uso de IA

O ChatGPT foi utilizado como apoio à organização da documentação, esclarecimento de conceitos, revisão de código e estruturação de análises.

O estudante é responsável por conferir o código, executar os experimentos, validar os resultados e compreender as decisões técnicas apresentadas no projeto.
