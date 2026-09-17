# SmartShop AI – Pipeline de IA

## 1. Pipeline do projeto

1. **Dados brutos**
   Utilização da base Online Retail do UCI, contendo informações sobre compras, produtos, clientes, datas, quantidades, preços e países.

2. **Limpeza dos dados**
   Tratamento de valores ausentes, duplicados, quantidades menores ou iguais a zero, preços inválidos e cancelamentos.

3. **Preparação dos dados**
   Organização dos registros de compra para representar o comportamento dos clientes em relação aos produtos.

4. **Criação dos pares Cliente–Produto**
   Criação de registros relacionando clientes e produtos para analisar a possibilidade de recompra.

5. **Criação das características históricas**
   Cálculo de informações como recência da última compra, frequência de compras, quantidade comprada e gasto médio, utilizando apenas informações anteriores ao período que será previsto.

6. **Criação do label de recompra**
   Criação de uma variável que indica se o cliente comprará determinado produto no próximo período, sendo `1` para recompra e `0` para ausência de recompra.

7. **Divisão cronológica dos dados**
   Separação dos dados em treinamento e teste seguindo a ordem temporal das compras, evitando que informações futuras sejam utilizadas no treinamento.

8. **Treinamento do modelo de classificação**
   Utilização de aprendizado supervisionado para treinar um modelo capaz de prever a probabilidade de um cliente comprar determinado produto no próximo período.

9. **Avaliação do modelo**
   Avaliação das previsões utilizando métricas como Precisão, Recall, F1 e Matriz de Confusão.

10. **Geração das recomendações**
    Utilização das probabilidades previstas pelo modelo para ordenar os produtos e gerar uma lista de produtos recomendados para cada cliente.

11. **Interpretação dos resultados**
    Análise das recomendações e das métricas obtidas para verificar os resultados do modelo e identificar possíveis limitações.

---

## 2. Entrada, processamento e saída

### Entrada

Durante o treinamento, serão utilizados os registros históricos da base Online Retail para criar os pares Cliente–Produto, as características históricas e o label de recompra.

No uso real do sistema, a entrada será formada pelo identificador do cliente e seu histórico de compras disponível até o momento da recomendação.

### Processamento

Os dados serão tratados e organizados. Depois, serão criados os pares Cliente–Produto e calculadas as características históricas, como recência, frequência, quantidade comprada e gasto médio.

Em seguida, será criado o label de recompra, indicando se o cliente comprou determinado produto no próximo período.

Os dados serão divididos cronologicamente em treinamento e teste. O modelo de classificação será treinado com os dados históricos e utilizado para prever a probabilidade de recompra de cada par Cliente–Produto.

Essas probabilidades serão utilizadas para ordenar os produtos e gerar as recomendações.

### Saída

O sistema deverá retornar uma lista de produtos recomendados para o cliente, ordenada de acordo com a probabilidade prevista de recompra.

Exemplo:

Cliente: 12345

Produtos recomendados:
1. Produto A
2. Produto B
3. Produto C
4. Produto D

---

## 3. Tipo de aprendizado utilizado

O SmartShop AI utilizará **aprendizado supervisionado, por meio de classificação binária**.

A escolha foi alterada em relação ao esboço inicial. Inicialmente, o projeto havia sido definido como aprendizado não supervisionado porque a base Online Retail não possui uma variável `label` pronta.

Para a AP2, o problema será reformulado para prever se um cliente comprará determinado produto no próximo período. Dessa forma, será criado um label a partir do histórico da própria base, sendo `1` quando houver recompra e `0` quando não houver.

A classificação permitirá utilizar métricas como Precisão, Recall, F1 e Matriz de Confusão.

A recomendação continuará sendo o objetivo final do projeto, utilizando as probabilidades previstas pelo modelo para ordenar os produtos mais prováveis de serem comprados por cada cliente.

---

## 4. Features e Label

### Features

* `CustomerID`
* `StockCode`
* `Description`
* `Quantity`
* `InvoiceDate`
* `UnitPrice`
* `Country`

Essas informações serão utilizadas para representar o comportamento de compra dos clientes e para construir as características históricas utilizadas pelo modelo.

A coluna `Description` não será utilizada diretamente como feature principal, pois representa a descrição textual do produto e o código `StockCode` já identifica o produto.

A coluna `InvoiceNo` não será utilizada como feature do modelo, pois identifica a fatura e pode representar informações específicas da transação.

Registros sem `CustomerID` serão removidos da etapa de modelagem, pois não é possível relacioná-los corretamente a um cliente.

### Label

O label será criado a partir do histórico de compras e indicará se o cliente comprará determinado produto no próximo período.

* `1` = o cliente comprou o produto no próximo período;
* `0` = o cliente não comprou o produto no próximo período.

O label não existe originalmente na base e será construído durante a preparação dos dados.

---

## 5. Verificação de Data Leakage

Foi identificado **risco de data leakage** caso informações futuras sejam utilizadas para prever uma compra que ainda não aconteceu.

Por isso, informações como `Quantity`, `UnitPrice` e `InvoiceDate` referentes ao período que está sendo previsto não poderão ser utilizadas como características do modelo.

As características utilizadas na previsão serão calculadas somente com informações anteriores ao período previsto.

A divisão dos dados também será cronológica, utilizando períodos anteriores para treinamento e períodos posteriores para teste. Dessa forma, o modelo não terá acesso a informações futuras durante o treinamento.

A decisão será verificar e documentar essa separação durante a preparação dos dados, garantindo que as features utilizadas estejam disponíveis antes do evento que o modelo deverá prever.

---

## 6. Divisão dos dados

### Proporção

Inicialmente será utilizada uma divisão de **80% para treinamento e 20% para teste**.

### Critério

Será utilizada uma **divisão cronológica**, pois a base possui a variável `InvoiceDate` e representa compras realizadas ao longo do tempo.

Os registros mais antigos serão utilizados para desenvolver o modelo e os registros posteriores para avaliar seu funcionamento.

### Desbalanceamento

Após a criação do label, será verificado o balanceamento entre as classes `1` e `0`.

Não será utilizado `stratify`, pois a divisão será baseada na ordem temporal dos dados.

Também será observado o problema de produtos muito populares aparecerem com maior frequência nas recomendações.

### Validação cruzada

Neste momento, a validação cruzada tradicional não será a prioridade, pois será considerada a ordem temporal dos dados para realizar a avaliação.

---

## 7. Backlog da AP2

| Item | Descrição | Status |
| --- | --- | --- |
| Definição do aprendizado | Reformular o problema como classificação de recompra | Concluído |
| Tratamento dos dados | Aplicar os tratamentos definidos no diagnóstico de qualidade | Pendente |
| Preparação dos dados | Preparar os dados para a criação dos pares Cliente–Produto | Pendente |
| Criação dos pares Cliente–Produto | Criar os registros utilizados na previsão de recompra | Pendente |
| Criação das características | Calcular recência, frequência, quantidade, gasto médio e demais características | Pendente |
| Criação do label | Criar o label `1` para recompra e `0` para ausência de recompra | Pendente |
| Verificação de leakage | Garantir que informações futuras não sejam utilizadas nas features | Pendente |
| Divisão dos dados | Separar os dados cronologicamente em treinamento e teste | Pendente |
| Treinamento | Treinar o primeiro modelo de classificação | Pendente |
| Métricas | Calcular Precisão, Recall, F1 e Matriz de Confusão | Pendente |
| Interpretação | Analisar os resultados e as limitações do modelo | Pendente |
| Geração das recomendações | Criar o ranking de produtos com base nas probabilidades previstas | Pendente |
| Atualização do notebook | Registrar e executar as etapas do modelo no Colab | Pendente |
| Atualização do README | Documentar o pipeline, o tipo de aprendizado e os resultados | Pendente |
| Preparação da AP2 | Organizar os resultados para a próxima apresentação | Pendente |
