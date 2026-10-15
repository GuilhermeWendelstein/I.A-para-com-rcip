# Atividade 11 — Revisão Técnica da AP2
## Projeto SmartShop AI — Sistema Inteligente de Recomendação de Produtos

## 1. Objetivo da revisão

Esta revisão analisa os resultados técnicos obtidos na AP2, os pontos positivos do modelo, suas limitações e as melhorias necessárias para a etapa final do SmartShop AI. A análise considera as métricas registradas nos experimentos e o feedback recebido durante a apresentação.

O modelo avaliado é uma **Árvore de Decisão para classificação**, utilizada para prever se um cliente realizará uma nova compra. Essa classificação é uma etapa do projeto e ainda não corresponde, por si só, à recomendação individualizada de produtos.

## 2. O que funcionou bem

### 2.1. Desempenho superior ao baseline

A Árvore de Decisão com profundidade máxima igual a 5 obteve acurácia de **72,40%**, enquanto o baseline apresentou **61,61%**. A diferença foi de 10,79 pontos percentuais.

Esse resultado indica que o modelo conseguiu aproveitar padrões presentes nas características dos clientes e apresentou desempenho superior à referência utilizada. Na etapa final, o baseline e a árvore atual serão preservados como referências para comparar os novos experimentos.

### 2.2. Preparação dos dados e avaliação documentadas

O projeto utiliza características construídas a partir do histórico anterior à data de corte, enquanto a recompra é identificada no período posterior. Entre as características estão quantidade total comprada, preço médio, quantidade de pedidos, país agrupado e recência.

A transformação da variável `Pais` também passou a ser realizada depois da separação entre treino e teste, com alinhamento das colunas. Essas decisões tornam o processo mais organizado e ajudam a reduzir o risco de vazamento de informações.

O treinamento apresentou **72,15% de acurácia**, enquanto o teste apresentou **72,40%**. A diferença de -0,25 ponto percentual não indica, isoladamente, um problema evidente de sobreajuste.

O feedback recebido na AP2 também destacou positivamente a apresentação da evolução do projeto, a identificação da fonte dos dados, o dicionário de variáveis e a interpretação da matriz de confusão.

## 3. Problemas e limitações identificados

### 3.1. Recall baixo para clientes que recompram

O recall da classe `Comprou novamente` foi de **38,56%**, com precisão de **78,67%** e F1-score de aproximadamente **0,52**.

A matriz de confusão apresentou os seguintes resultados:

| Resultado | Quantidade | Interpretação |
|---|---:|---|
| Verdadeiros negativos | 459 | Clientes que não recompraram e foram classificados corretamente |
| Falsos positivos | 32 | Clientes classificados como recompra que não recompraram |
| Falsos negativos | 188 | Clientes que recompraram, mas não foram identificados pelo modelo |
| Verdadeiros positivos | 118 | Clientes que recompraram e foram identificados corretamente |

Os 188 falsos negativos representam uma limitação importante: o modelo deixou de identificar diversos clientes que efetivamente voltaram a comprar. Em uma aplicação comercial, isso pode significar oportunidades perdidas de relacionamento ou de campanhas direcionadas.

A melhoria do recall será investigada, mas nenhuma configuração será considerada melhor apenas por aumentar essa métrica. Também serão observados a precisão, o F1-score e os efeitos sobre os demais erros.

### 3.2. Dificuldade para explicar decisões técnicas

Durante a apresentação da AP2, houve dificuldade para identificar verbalmente o modelo como uma Árvore de Decisão, explicar a finalidade da data de corte e definir `stratify`.

Isso mostrou uma diferença entre a qualidade da documentação apresentada e o domínio demonstrado nas perguntas técnicas. A dificuldade compromete a capacidade de defender as decisões do projeto e pode prejudicar a apresentação da AS, mesmo quando os resultados estão documentados corretamente.

## 4. Hipóteses para as causas dos problemas

### 4.1. Possíveis causas do recall baixo

**Hipótese 1:** as características utilizadas podem não representar suficientemente todos os padrões associados à recompra. Quantidade total comprada, preço médio, quantidade de pedidos, país e recência resumem o histórico, mas podem não capturar toda a variação do comportamento dos clientes.

**Como testar:** investigar características adicionais construídas exclusivamente com dados anteriores à data de corte e comparar os resultados com o modelo atual. Cada alteração será avaliada por meio das mesmas métricas e da matriz de confusão.

**Hipótese 2:** a configuração atual da Árvore de Decisão pode não estar identificando uma parcela suficiente dos clientes da classe positiva. No conjunto de teste, foram registrados 491 casos de `Não comprou novamente` e 306 casos de `Comprou novamente`. Essa diferença não comprova a causa do recall baixo, mas justifica investigar configurações que considerem melhor a classe positiva.

**Como testar:** comparar a árvore atual com uma versão que utilize `class_weight='balanced'` e, quando adequado, testar diferentes limiares de decisão utilizando probabilidades previstas. Registrar recall, precisão, F1-score e matriz de confusão em cada experimento.

### 4.2. Possível causa das dificuldades na apresentação

**Hipótese:** a preparação dos slides e da documentação pode não ter sido acompanhada de prática suficiente para explicar os conceitos sem consulta ao material.

**Como testar:** realizar ensaios sem os slides e responder a perguntas sobre o tipo de problema, o modelo, a data de corte, `stratify`, baseline, métricas e matriz de confusão. Os pontos em que houver dificuldade serão estudados novamente antes da apresentação final.

## 5. Melhorias propostas para a etapa final

1. **Investigar o recall:** testar `class_weight='balanced'` e outras configurações justificadas, registrando os resultados antes e depois de cada alteração.
2. **Avaliar novas características:** verificar se variáveis adicionais de histórico de compras melhoram o reconhecimento de clientes que recompram, sem utilizar informações posteriores à data de corte como características.
3. **Comparar os experimentos:** manter o baseline e a árvore atual como referências e apresentar uma comparação de acurácia, precisão, recall, F1-score e matriz de confusão.
4. **Desenvolver a recomendação de produtos:** avançar da classificação de recompra para uma etapa que gere recomendações individualizadas e definir como a qualidade dessas recomendações será avaliada.
5. **Reforçar o domínio técnico:** estudar as decisões do projeto e treinar a explicação oral com palavras próprias, sem apenas ler os slides.
6. **Consolidar a entrega:** executar o notebook final integralmente, revisar o README, produzir o relatório, documentar as limitações e melhorias futuras e organizar evidências de execução.

Essas melhorias serão realizadas entre os Encontros 12 e 17, conforme o backlog atualizado e o tempo disponível.

## 6. Conclusão

A AP2 demonstrou que a Árvore de Decisão supera o baseline e que a preparação e a documentação dos dados estão bem encaminhadas. Entretanto, o recall de 38,56% e os 188 falsos negativos mostram que o modelo ainda deixa passar uma parcela significativa dos clientes que recompram.

O feedback da apresentação também indicou a necessidade de aprofundar o domínio das decisões técnicas. Por isso, a etapa final não se limitará a melhorar números: deverá apresentar experimentos verificáveis, desenvolver a recomendação de produtos, documentar limitações e permitir que as escolhas do projeto sejam explicadas e defendidas.

## 7. Uso de inteligência artificial

A inteligência artificial generativa foi utilizada como apoio à organização e à redação inicial deste documento. Os resultados apresentados devem ser conferidos com o notebook e os artefatos do projeto. A revisão final, a validação técnica e a responsabilidade pela entrega são do estudante.
