# Atividade 15 – Relatório Crítico Final
## Projeto SmartShop AI – Sistema Inteligente de Recomendação de Produtos

## 1. Apresentação do projeto

O SmartShop AI é um projeto de Ciência de Dados voltado ao comércio eletrônico. Seu objetivo é analisar o comportamento de compra dos clientes e identificar padrões que possam auxiliar pequenas e médias lojas virtuais na personalização de suas estratégias.

O projeto utiliza a base de dados Online Retail, disponibilizada pelo UCI Machine Learning Repository. Foram realizadas etapas de preparação dos dados, análise exploratória, segmentação de clientes utilizando K-means e experimentos de classificação com Decision Tree e MLPClassifier.

É importante destacar que o projeto ainda não possui um sistema automático de recomendação de produtos em funcionamento. Os modelos desenvolvidos representam etapas de análise e previsão que podem contribuir para uma futura solução de recomendação.

## 2. Principais resultados

Durante o desenvolvimento, foram realizados experimentos com diferentes modelos de classificação. Os resultados obtidos foram:

| Modelo | Acurácia | Precisão | Recall | F1-score |
|---|---:|---:|---:|---:|
| Baseline | 61,61% | 0% | 0% | 0 |
| Decision Tree | 72,40% | 78,67% | 38,56% | 0,5175 |
| MLPClassifier | 73,40% | 73,98% | 47,39% | 0,5777 |

O modelo Baseline apresentou acurácia de 61,61%, mas não conseguiu identificar corretamente exemplos da classe positiva. Isso demonstra que apenas observar a acurácia pode ser insuficiente para avaliar um modelo, principalmente quando existe desequilíbrio entre as classes.

O Decision Tree apresentou 72,40% de acurácia e 78,67% de precisão. Isso significa que, quando identificou um cliente como possível comprador recorrente, acertou em boa parte dessas previsões. Entretanto, seu recall de 38,56% mostra que deixou de identificar muitos clientes que realmente pertenciam à classe positiva.

O MLPClassifier apresentou o melhor resultado geral entre os modelos testados, alcançando 73,40% de acurácia e F1-score de 0,5777. Seu recall de 47,39% foi superior ao do Decision Tree, indicando que conseguiu identificar uma quantidade maior de clientes da classe positiva. Mesmo assim, ainda deixou de identificar mais da metade desses casos.

Na segmentação com K-means, foram comparados diferentes números de grupos. O resultado de silhouette foi 0,312 para dois clusters e 0,307 para quatro clusters. Os valores são próximos, indicando que a escolha de quatro grupos não apresentou uma vantagem estatística clara em relação à escolha de dois. Portanto, a escolha de quatro grupos precisa ser justificada principalmente pela interpretação e utilidade comercial dos segmentos.

## 3. Limitações identificadas

Apesar dos resultados obtidos, o projeto apresenta limitações que precisam ser consideradas.

### 3.1. Representatividade da base de dados

A base Online Retail representa transações de um único contexto comercial. Por isso, os padrões encontrados podem não representar o comportamento de consumidores de outras lojas, segmentos ou períodos. Na prática, um modelo treinado com esses dados pode apresentar resultados diferentes quando aplicado a outro comércio eletrônico.

### 3.2. Ausência de identificação de parte dos clientes

A base possui registros sem identificação de cliente. Esses registros dificultam a análise do comportamento individual e a identificação de padrões de recompra. Isso pode fazer com que determinados comportamentos fiquem de fora das análises que dependem do histórico de cada consumidor.

### 3.3. Dificuldade em identificar a classe positiva

O MLPClassifier alcançou recall de 47,39%, o que significa que ainda não identificou mais da metade dos casos positivos. Em uma aplicação comercial, isso pode fazer com que clientes com potencial de recompra não sejam reconhecidos e deixem de receber ofertas ou recomendações relevantes.

### 3.4. Escolha do número de clusters

Os valores de silhouette para dois e quatro grupos foram muito próximos. Portanto, não existe uma evidência clara de que quatro clusters sejam melhores apenas pelo resultado dessa métrica. Também é necessário apresentar os tamanhos e as características de cada grupo para demonstrar sua utilidade para o negócio.

### 3.5. Ausência de avaliação dos erros por segmento

O projeto identificou 188 falsos negativos em uma avaliação anterior, mas ainda não foi realizada uma análise que mostre como esses erros estão distribuídos entre os quatro clusters. Essa informação seria importante para descobrir se algum segmento apresenta maior dificuldade de identificação.

### 3.6. Reprodutibilidade

O arquivo de dados tratados não está disponível no repositório do projeto. Isso dificulta que outra pessoa execute os notebooks e reproduza os resultados sem realizar novamente a preparação dos dados.

### 3.7. Ausência de um sistema real de recomendação

Os modelos desenvolvidos analisam e classificam comportamentos, mas ainda não existe uma avaliação de recomendações reais de produtos. Assim, os resultados de acurácia, precisão, recall e F1-score não comprovam, por si só, que o sistema recomenda os produtos mais adequados para cada cliente.

## 4. Auditoria de vieses

A auditoria de vieses é importante para entender quais grupos estão representados nos dados e se o modelo pode apresentar resultados diferentes dependendo das características dos clientes.

A base utilizada representa clientes e transações de um único contexto de comércio eletrônico. Dessa forma, consumidores de outras lojas e pessoas sem identificação nos registros podem não estar adequadamente representados nas análises individuais.

Uma variável que merece atenção é o país do cliente. Essa informação pode representar diferenças geográficas, culturais e econômicas que influenciam os padrões de compra. Caso seja utilizada em um modelo, é necessário verificar se ela acaba funcionando como uma variável indireta para diferenças entre grupos.

Também é importante considerar que os dados históricos de compra não representam necessariamente as necessidades reais dos consumidores. Eles refletem decisões anteriores, como preços, disponibilidade de produtos, divulgação, catálogo da loja e preferências registradas.

Até o momento, não foram realizadas métricas de desempenho separadas por grupos de clientes. Portanto, não é possível afirmar que o modelo apresenta o mesmo desempenho para todos os grupos. Uma análise futura poderá comparar precisão e recall por país ou por segmento, desde que existam dados suficientes para uma comparação confiável.

Não foram identificados indícios suficientes para afirmar que existe discriminação efetiva no modelo. Entretanto, a ausência de uma avaliação por grupos representa uma limitação importante.

## 5. Avaliação de riscos

O risco geral do projeto foi classificado como **baixo**, considerando que sua proposta é auxiliar análises comerciais e futuras recomendações de produtos, sem tomar decisões diretamente relacionadas a direitos fundamentais, saúde ou acesso a serviços essenciais.

Mesmo assim, existem riscos comerciais e relacionados à experiência do consumidor.

Uma previsão incorreta pode fazer com que a loja deixe de oferecer um produto relevante para determinado cliente ou apresente recomendações que não correspondem aos seus interesses. Isso pode prejudicar a experiência de compra e gerar perda de oportunidades comerciais.

O custo dos erros pode ser dividido entre a loja, que pode perder vendas, e o consumidor, que pode receber sugestões pouco relevantes ou ter sua experiência de navegação limitada.

Um possível uso inadequado seria utilizar a previsão do modelo como único critério para impedir que determinados clientes recebam ofertas ou tenham acesso a produtos. Também seria incorreto tratar uma previsão de não recompra como uma certeza sobre o comportamento futuro de uma pessoa.

As recomendações devem funcionar como apoio à decisão, permitindo que o consumidor continue pesquisando e escolhendo livremente os produtos.

## 6. Melhorias propostas

Com base nas limitações identificadas, algumas melhorias podem tornar o projeto mais confiável e útil.

### 6.1. Melhorar a disponibilidade dos dados

Disponibilizar o arquivo de dados tratados ou documentar um processo de preparação que permita reproduzir os resultados. Isso facilitaria a execução dos notebooks por outras pessoas.

### 6.2. Revisar a segmentação de clientes

Apresentar o tamanho e as características de cada cluster, além de justificar a escolha de quatro grupos com base em sua utilidade comercial. Também é importante analisar em qual segmento estão concentrados os 188 falsos negativos identificados anteriormente.

### 6.3. Ajustar o limite de classificação

Testar diferentes limites de probabilidade no Decision Tree e comparar seus resultados com o MLPClassifier. Isso permitirá verificar se a diferença de recall entre os modelos está relacionada à capacidade de aprendizado ou ao limite utilizado para classificar os clientes.

### 6.4. Melhorar o tratamento das variáveis

Utilizar ferramentas como OneHotEncoder com handle_unknown='ignore' dentro de um Pipeline, garantindo que o tratamento das variáveis categóricas seja consistente entre os dados de treinamento e teste.

### 6.5. Avaliar melhor o desempenho dos modelos

Realizar validação cruzada e testes adicionais para verificar se os resultados se mantêm em diferentes divisões dos dados. Também é importante acompanhar precisão e recall para evitar que uma melhoria em uma métrica prejudique excessivamente outra.

### 6.6. Realizar uma auditoria por grupos

Comparar o desempenho dos modelos entre segmentos ou países, quando houver quantidade suficiente de registros. Isso ajudaria a identificar possíveis diferenças de desempenho.

### 6.7. Desenvolver e avaliar recomendações reais

Como etapa futura, implementar um mecanismo que indique produtos para cada cliente. Depois, avaliar a qualidade das recomendações com métricas próprias, como Precision@K, Recall@K e NDCG@K, além de observar diversidade e relevância dos produtos apresentados.

## 7. Roteiro para apresentação da Avaliação Semestral

A apresentação terá duração aproximada de oito minutos, organizada da seguinte maneira:

| Tempo | Conteúdo |
|---|---|
| 0:00 – 0:45 | Apresentação do SmartShop AI e do problema que o projeto busca resolver. |
| 0:45 – 1:30 | Apresentação da base Online Retail, sua origem e as principais variáveis utilizadas. |
| 1:30 – 2:30 | Explicação da preparação dos dados e da segmentação com K-means. |
| 2:30 – 4:00 | Apresentação do Decision Tree, do Baseline e dos resultados obtidos. |
| 4:00 – 5:00 | Comparação com o MLPClassifier e explicação das métricas. |
| 5:00 – 6:00 | Discussão das limitações, possíveis vieses e riscos do projeto. |
| 6:00 – 7:15 | Apresentação das melhorias propostas e dos próximos passos. |
| 7:15 – 8:00 | Conclusão e demonstração dos materiais disponíveis no repositório. |

Após a apresentação, haverá um período de até quatro minutos para responder às perguntas da avaliação.

## 8. Conclusão

O desenvolvimento do SmartShop AI permitiu aplicar diferentes etapas de um projeto de Ciência de Dados, desde a preparação dos dados até a análise de resultados utilizando técnicas de segmentação e classificação.

Os experimentos demonstraram que o MLPClassifier apresentou desempenho superior ao Decision Tree em recall e F1-score, embora ainda existam dificuldades para identificar todos os clientes da classe positiva.

Também foi possível identificar limitações relacionadas à representatividade dos dados, à segmentação dos clientes, à avaliação de vieses e à reprodução dos experimentos.

Conclui-se que o projeto atingiu uma etapa importante de análise e experimentação, mas ainda precisa de melhorias antes de ser utilizado como um sistema real de recomendação. Os próximos passos envolvem tornar os resultados reproduzíveis, aprofundar a análise dos clusters e implementar um mecanismo de recomendação que possa ser avaliado diretamente.

## 9. Declaração de uso de Inteligência Artificial

Foram utilizadas ferramentas de Inteligência Artificial como apoio à organização das ideias, esclarecimento de conceitos, revisão de textos e auxílio durante o desenvolvimento do projeto. As decisões sobre o projeto, a execução dos experimentos, a análise dos resultados e a validação das informações foram realizadas e revisadas pelo estudante.
