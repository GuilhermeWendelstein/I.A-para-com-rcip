# SmartShop AI – Pipeline de IA

## 1. Pipeline do projeto

1. **Dados brutos**
   Utilização da base Online Retail do UCI, contendo informações sobre compras, produtos, clientes, datas, quantidades, preços e países.

2. **Limpeza dos dados**
   Tratamento de valores ausentes, duplicados, quantidades menores ou iguais a zero, preços inválidos e cancelamentos.

3. **Preparação dos dados**
   Organização dos registros de compra para representar o comportamento dos clientes em relação aos produtos.

4. **Identificação dos padrões de compra**
   Análise das relações entre clientes e produtos comprados, buscando identificar padrões que possam ser utilizados na recomendação.

5. **Aplicação da abordagem de recomendação**
   Utilização dos padrões encontrados para identificar produtos que podem ser relevantes para cada cliente.

6. **Geração das recomendações**
   Criação de uma lista de produtos recomendados para cada cliente.

7. **Interpretação dos resultados**
   Análise das recomendações para verificar se os produtos indicados possuem relação com o histórico de compras dos clientes.

---

## 2. Entrada, processamento e saída

### Entrada

Os principais dados utilizados serão:

* `CustomerID` – identificação do cliente;
* `StockCode` – código do produto;
* `Description` – descrição do produto;
* `Quantity` – quantidade comprada;
* `InvoiceDate` – data da compra;
* `UnitPrice` – preço unitário;
* `Country` – país.

### Processamento

Os dados serão tratados e organizados. Depois, serão analisados os padrões de compra dos clientes e as relações existentes entre os produtos.

Esses padrões serão utilizados pela abordagem de recomendação para identificar produtos que possam ser relevantes para cada cliente.

### Saída

O sistema deverá retornar uma lista de produtos recomendados para o cliente.

Exemplo:

```text
Cliente: 12345

Produtos recomendados:
1. Produto A
2. Produto B
3. Produto C
4. Produto D
```

---

## 3. Tipo de aprendizado utilizado

O SmartShop AI utilizará **aprendizado não supervisionado**.

A escolha ocorre porque a base Online Retail não possui uma variável `label` indicando qual produto deveria ser recomendado para cada cliente.

O objetivo do projeto é encontrar padrões e relações existentes no histórico de compras para gerar recomendações, em vez de prever uma variável já definida na base.

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

Essas informações serão utilizadas para representar o comportamento de compra dos clientes.

### Label

O projeto **não possui uma label definida na base original**, pois o objetivo é encontrar padrões de compra e gerar recomendações.

---

## 5. Verificação de Data Leakage

Foi verificado se alguma coluna representa uma informação que somente estaria disponível depois que o resultado já tivesse acontecido.

Como a base possui registros históricos de compras, será necessário tomar cuidado para não utilizar informações futuras na geração das recomendações.

Na divisão dos dados, serão utilizados dados anteriores para desenvolver a abordagem e dados posteriores para avaliar seu funcionamento.

---

## 6. Divisão dos dados

### Proporção

Inicialmente será utilizada uma divisão de **80% para treinamento e 20% para teste**.

### Critério

Será utilizada uma **divisão cronológica**, pois a base possui a variável `InvoiceDate` e representa compras realizadas ao longo do tempo.

Os registros mais antigos serão utilizados para desenvolver a abordagem e os registros posteriores para avaliar as recomendações.

### Desbalanceamento

Como o projeto não possui uma classe-alvo tradicional, não será utilizado `stratify`.

Mesmo assim, será observado o problema de produtos muito populares aparecerem com maior frequência nas recomendações.

### Validação cruzada

Neste momento, a validação cruzada não será a prioridade, pois será considerada a ordem temporal dos dados para realizar a avaliação.

---

## 7. Backlog da AP2

| Item                          | Descrição                                                           | Status   |
| ----------------------------- | ------------------------------------------------------------------- | -------- |
| Tratamento dos dados          | Aplicar os tratamentos definidos no diagnóstico de qualidade        | Pendente |
| Preparação dos dados          | Preparar os dados para a abordagem de recomendação                  | Pendente |
| Implementação da recomendação | Desenvolver a abordagem escolhida para o SmartShop AI               | Pendente |
| Treinamento                   | Aplicar a abordagem aos dados de treinamento                        | Pendente |
| Teste                         | Avaliar o funcionamento utilizando os dados de teste                | Pendente |
| Métricas                      | Definir e calcular métricas adequadas para avaliar as recomendações | Pendente |
| Interpretação                 | Analisar os resultados obtidos                                      | Pendente |
| Atualização do notebook       | Registrar e executar as etapas do modelo no Colab                   | Pendente |
| Atualização do README         | Documentar o pipeline e os resultados                               | Pendente |
| Preparação da AP2             | Organizar os resultados para a próxima apresentação                 | Pendente |
