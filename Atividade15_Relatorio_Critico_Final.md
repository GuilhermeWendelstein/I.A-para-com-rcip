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
| Decision Tree (0,50) | 72,40% | 78,67% | 38,56% | 0,5175 |
| Decision Tree (0,40) | 71,64% | 64,18% | 59,15% | 0,6156 |
| MLPClassifier | 73,40% | 73,98% | 47,39% | 0,5777 |

O modelo Baseline apresentou acurácia de 61,61%, mas não conseguiu identificar corretamente exemplos da classe positiva. Isso demonstra que apenas observar a acurácia pode ser insuficiente para avaliar um modelo, principalmente quando existe desequilíbrio entre as classes.

O Decision Tree com limiar padrão de 0,50 apresentou 72,40% de acurácia e 78,67% de precisão. Entretanto, seu recall de 38,56% mostra que deixou de identificar muitos clientes que realmente pertenciam à classe positiva.

Também foi realizado um teste utilizando o limiar de classificação 0,40 na Árvore de Decisão. Com essa alteração, o recall aumentou para 59,15%, enquanto a precisão caiu para 64,18%. O F1-score passou de 0,5175 para 0,6156. Isso demonstra que a alteração do limite de classificação pode modificar o equilíbrio entre os erros do modelo.

O MLPClassifier apresentou 73,40% de acurácia, 73,98% de precisão e F1-score de 0,5777. Seu recall foi de 47,39%, superior ao da Árvore com limiar padrão, mas inferior ao da Árvore com limiar 0,40.

Portanto, a escolha do modelo depende do objetivo comercial. Caso a prioridade seja identificar uma quantidade maior de clientes com potencial de recompra, a Árvore com limiar 0,40 apresenta vantagem em recall. Já a MLP apresenta a maior acurácia entre os modelos comparados e um equilíbrio diferente entre precisão e recall.

Na segmentação com K-means, foram comparados diferentes números de grupos. O resultado de silhouette foi 0,312 para dois clusters e 0,307 para quatro clusters. Os valores são próximos, indicando que a escolha de quatro grupos não apresentou uma vantagem estatística clara em relação à escolha de dois. Portanto, a escolha de quatro grupos foi exploratória e precisa ser justificada principalmente pela interpretação e utilidade comercial dos segmentos.

## 3. Limitações identificadas

Apesar dos resultados obtidos, o projeto apresenta limitações que precisam ser consideradas.

### 3.1. Representatividade da base de dados

A base Online Retail representa transações de um único contexto comercial. Por isso, os padrões encontrados podem não representar o comportamento de consumidores de outras lojas, segmentos ou períodos. Na prática, um modelo treinado com esses dados pode apresentar resultados diferentes quando aplicado a outro comércio eletrônico.

### 3.2. Ausência de identificação de parte dos clientes

A base possui registros sem identificação de cliente. Esses registros dificultam a análise do comportamento individual e a identificação de padrões de recompra. Isso pode fazer com que determinados comportamentos fiquem de fora das análises que dependem do histórico de cada consumidor.

### 3.3. Dificuldade em identificar a classe positiva

Mesmo com os experimentos realizados, os modelos ainda apresentam dificuldades para identificar todos os clientes que realmente recompraram.

A MLP apresentou recall de 47,39%, enquanto a Árvore com limiar 0,40 alcançou 59,15%. Embora o segundo resultado seja superior, ainda existem clientes da classe positiva que não são identificados.

Em uma aplicação comercial, isso pode fazer com que clientes com potencial de recompra não sejam reconhecidos e deixem de receber ofertas ou recomendações relevantes.

### 3.4. Escolha do número de clusters

Os valores de silhouette para dois e quatro grupos foram muito próximos. Portanto, não existe uma evidência clara de que quatro clusters sejam melhores apenas pelo resultado dessa métrica. Também é necessário apresentar os tamanhos e as características de cada grupo para demonstrar sua utilidade para o negócio.

### 3.5. Erros de classificação e segmentos de clientes

O projeto identificou 188 falsos negativos na avaliação original da Árvore de Decisão com limiar 0,50.

Na análise exploratória dos clusters, foram observadas diferenças nas taxas de recompra futura. O grupo 1, por exemplo, apresentou taxa de 69,44%, enquanto o grupo 0 apresentou 19,54%. Esses resultados ajudam a compreender que os clientes possuem comportamentos diferentes.

Entretanto, o cruzamento dos falsos negativos com os clusters não permite, por si só, afirmar que determinado grupo é a causa dos erros. Essa análise deve ser interpretada como uma forma de investigar possíveis padrões de dificuldade de classificação.

### 3.6. Reprodutibilidade

O arquivo de dados tratados precisa estar disponível no repositório do projeto ou ter seu processo de geração documentado de forma clara. Sem isso, outra pessoa pode encontrar dificuldades para executar os notebooks e reproduzir os resultados.

### 3.7. Ausência de um sistema real de recomendação

Os modelos desenvolvidos analisam e classificam comportamentos, mas ainda não existe uma avaliação de recomendações reais de produtos. Assim, os resultados de acurácia, precisão, recall e F1-score não comprovam, por si só, que o sistema recomenda os produtos mais adequados para cada cliente.

## 4. Auditoria de vieses

A auditoria de vieses é importante para entender quais grupos estão representados nos dados e se o modelo pode apresentar resultados diferentes dependendo das características dos clientes.

Uma variável que merece atenção é o país do cliente. Essa informação pode representar diferenças geográficas, culturais e econômicas que influenciam os padrões de compra. Como ela foi utilizada entre as variáveis do modelo, foi realizada uma comparação do desempenho da Árvore de Decisão com limiar padrão de 0,50 entre os grupos Reino Unido e Outros.

Os resultados no conjunto de teste foram:

| Grupo | Clientes no teste | Casos positivos reais | Verdadeiros positivos | Falsos negativos | Recall |
|---|---:|---:|---:|---:|---:|
| Reino Unido | 730 | 284 | 107 | 177 | 37,68% |
| Outros | 67 | 22 | 11 | 11 | 50,00% |

O grupo Reino Unido apresentou recall de 37,68%, enquanto o grupo Outros apresentou 50,00%. Isso indica uma diferença observada no desempenho entre os grupos avaliados.

Entretanto, é necessário considerar a quantidade de registros disponíveis. Embora existam 386 clientes classificados como Outros no conjunto completo de dados, somente 67 pertencem a esse grupo no conjunto de teste. Portanto, o resultado de 50% deve ser interpretado com cautela, pois uma amostra menor torna a estimativa menos estável.

Antes da análise, a expectativa era encontrar possíveis diferenças de desempenho entre os países, considerando que os padrões de compra poderiam variar entre os grupos. Essa expectativa não foi registrada previamente como uma hipótese formal. Após a execução, foi observada uma diferença de recall entre os grupos, mas não existem evidências suficientes para afirmar que essa diferença representa discriminação ou que seja causada diretamente pela variável país.

Também é importante considerar que os dados históricos de compra não representam necessariamente as necessidades reais dos consumidores. Eles refletem decisões anteriores, como preços, disponibilidade de produtos, divulgação, catálogo da loja e preferências registradas.

Assim, a auditoria permitiu identificar uma diferença que merece acompanhamento, mas não permite concluir que o modelo apresenta desempenho igual ou justo para todos os grupos.

## 5. Avaliação de riscos

O risco geral do projeto foi classificado como baixo, considerando que sua proposta é auxiliar análises comerciais e futuras recomendações de produtos, sem tomar decisões diretamente relacionadas a direitos fundamentais, saúde ou acesso a serviços essenciais.

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

Apresentar o tamanho e as características de cada cluster, além de justificar a escolha de quatro grupos com base em sua utilidade comercial. Também é importante continuar investigando a distribuição dos erros de classificação entre os segmentos.

### 6.3. Ajustar e validar o limite de classificação

Os testes realizados mostraram que a Árvore de Decisão com limiar 0,40 alcançou recall de 59,15%, superior aos 47,39% da MLP. Entretanto, sua precisão foi menor.

Essa comparação demonstra a importância de escolher o limite de classificação de acordo com o objetivo comercial. Como os limiares foram explorados no conjunto de teste, os resultados devem ser considerados exploratórios. Em uma avaliação metodologicamente mais rigorosa, o limite deve ser escolhido utilizando um conjunto de validação e o conjunto de teste deve ser reservado para a avaliação final.

### 6.4. Melhorar o tratamento das variáveis

Utilizar ferramentas como OneHotEncoder com handle_unknown='ignore' dentro de um Pipeline, garantindo que o tratamento das variáveis categóricas seja consistente entre os dados de treinamento e teste.

### 6.5. Avaliar melhor o desempenho dos modelos

Realizar validação cruzada e testes adicionais para verificar se os resultados se mantêm em diferentes divisões dos dados. Também é importante acompanhar precisão e recall para evitar que uma melhoria em uma métrica prejudique excessivamente outra.

### 6.6. Continuar a auditoria por grupos

Comparar o desempenho dos modelos entre segmentos ou países, quando houver quantidade suficiente de registros. Também é importante observar a incerteza das métricas em grupos menores, evitando conclusões baseadas em poucas observações.

### 6.7. Desenvolver e avaliar recomendações reais

Como etapa futura, implementar um mecanismo que indique produtos para cada cliente. Depois, avaliar a qualidade das recomendações com métricas próprias, como Precision@K, Recall@K e NDCG@K, além de observar diversidade e relevância dos produtos apresentados.

## 7. Roteiro para apresentação da Avaliação Semestral

A apresentação terá duração aproximada de oito minutos, organizada da seguinte maneira:

| Tempo | Conteúdo |
|---|---|
| 0:00 – 0:45 | Apresentação do SmartShop AI e do problema que o projeto busca resolver. |
| 0:45 – 1:30 | Apresentação da base Online Retail, sua origem e as principais variáveis utilizadas. |
| 1:30 – 2:30 | Explicação da preparação dos dados e da segmentação com K-means. |
| 2:30 – 4:00 | Apresentação do Baseline, da Árvore de Decisão e do teste de limiar 0,40. |
| 4:00 – 5:00 | Comparação com o MLPClassifier e explicação das métricas. |
| 5:00 – 6:15 | Discussão da auditoria por país, limitações e riscos do projeto. |
| 6:15 – 7:15 | Apresentação das melhorias propostas e dos próximos passos. |
| 7:15 – 8:00 | Conclusão e demonstração dos materiais disponíveis no repositório. |

Após a apresentação, haverá um período de até quatro minutos para responder às perguntas da avaliação.

## 8. Conclusão

O desenvolvimento do SmartShop AI permitiu aplicar diferentes etapas de um projeto de Ciência de Dados, desde a preparação dos dados até a análise de resultados utilizando técnicas de segmentação e classificação.

Os experimentos demonstraram que o MLPClassifier apresentou a maior acurácia entre os modelos comparados, enquanto a Árvore de Decisão com limiar 0,40 alcançou o maior recall e F1-score. Isso mostrou que a escolha do modelo depende do objetivo da aplicação e do equilíbrio desejado entre precisão e identificação de clientes com potencial de recompra.

A auditoria por país também identificou diferenças observadas no recall entre Reino Unido e Outros. Entretanto, o tamanho menor do grupo Outros no conjunto de teste exige cautela na interpretação dos resultados.

Também foram identificadas limitações relacionadas à representatividade dos dados, à segmentação dos clientes, à reprodução dos experimentos e à ausência de um mecanismo real de recomendação.

Conclui-se que o projeto atingiu uma etapa importante de análise e experimentação, mas ainda precisa de melhorias antes de ser utilizado como um sistema real de recomendação. Os próximos passos envolvem tornar os resultados reproduzíveis, aprofundar a análise dos clusters e implementar um mecanismo de recomendação que possa ser avaliado diretamente.

## 9. Declaração de uso de Inteligência Artificial

Foram utilizadas ferramentas de Inteligência Artificial como apoio à organização das ideias, esclarecimento de conceitos, revisão de textos e auxílio durante o desenvolvimento do projeto. As decisões sobre o projeto, a execução dos experimentos, a análise dos resultados e a validação das informações foram realizadas e revisadas pelo estudante.
