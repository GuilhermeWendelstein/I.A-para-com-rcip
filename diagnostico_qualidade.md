# Diagnóstico da Qualidade dos Dados - SmartShop AI

## 1. Base analisada

A base utilizada é o **Online Retail**, disponibilizado pelo **UCI Machine Learning Repository**. A base possui 541.909 registros e 8 colunas, contendo transações de uma loja de varejo online do Reino Unido entre 01/12/2010 e 09/12/2011. A licença informada pelo UCI é CC BY 4.0.

Fonte oficial: https://archive.ics.uci.edu/dataset/352/online+retail

A base será usada como ponto de partida para analisar padrões de compra e desenvolver o sistema de recomendação do SmartShop AI.

## 2. Diagnóstico dos problemas de qualidade

### Dimensões

- **Linhas:** 541.909
- **Colunas:** 8

### Dados ausentes

| Coluna | Valores ausentes | Proporção aproximada |
|---|---:|---:|
| CustomerID | 135.080 | 24,93% |
| Description | 1.454 | 0,27% |
| Demais colunas | 0 | 0% |

O principal problema de dados ausentes está em `CustomerID`. Como o SmartShop AI precisa relacionar compras a clientes, essa ausência pode dificultar recomendações personalizadas para parte dos registros.

### Dados duplicados

Foram identificadas **5.268 linhas totalmente duplicadas** na base original.

Também é importante observar que o `InvoiceNo` pode aparecer em várias linhas. Isso não significa necessariamente duplicação, pois uma mesma compra pode possuir vários produtos. Portanto, a repetição da fatura não deve ser removida automaticamente.

### Inconsistências

Foram identificados alguns pontos que precisam ser analisados:

- `InvoiceNo` iniciando com **C** indica cancelamento.
- Existem **quantidades negativas** em `Quantity`, relacionadas principalmente a devoluções/cancelamentos.
- Existem valores **zero ou negativos** em `UnitPrice`, que precisam ser investigados antes de serem utilizados no modelo.
- `Description` possui valores ausentes.
- A coluna `InvoiceDate` representa data e hora e deverá ser tratada como variável temporal no processamento.

Na base original, há 10.624 registros com `Quantity <= 0` e 2.517 com `UnitPrice <= 0`. Esses registros não serão removidos nesta etapa; eles serão analisados e tratados posteriormente.

### Desbalanceamento

O SmartShop AI é um problema de **recomendação**, portanto a base não possui uma variável de saída/classe tradicional para calcular proporções de classes.

Por isso, o desbalanceamento de classes **não se aplica diretamente** neste momento. Mesmo assim, será importante observar a concentração das compras por país e por produto, pois uma concentração muito grande pode fazer o sistema aprender principalmente o comportamento dos clientes e produtos mais frequentes.

## 3. Tabela de diagnóstico

| Problema encontrado | Onde aparece | Gravidade | Ação de tratamento proposta | Quando será tratado |
|---|---|---|---|---|
| Muitos `CustomerID` ausentes | CustomerID | Alta | Avaliar se os registros sem cliente devem ser excluídos da parte personalizada ou utilizados apenas em análises gerais | Encontro 8 |
| `Description` ausente | Description | Baixa | Verificar se o código do produto permite recuperar a descrição; caso contrário, avaliar a remoção desses poucos registros | Encontro 8 |
| Linhas totalmente duplicadas | Registros completos | Média | Identificar e remover duplicatas exatas para evitar que os mesmos registros tenham peso maior na análise | Encontro 8 |
| Quantidades negativas ou zero | Quantity | Média | Separar devoluções/cancelamentos das vendas normais e definir quais registros serão usados no modelo | Encontro 8 |
| Preços zero ou negativos | UnitPrice | Alta | Investigar os registros e decidir se serão removidos ou tratados de acordo com o significado da transação | Encontro 8 |
| Faturas iniciadas por C | InvoiceNo | Média | Identificar cancelamentos e separá-los das compras válidas antes da construção das recomendações | Encontro 8 |
| Concentração por país/produto | Country / StockCode | Média | Avaliar a distribuição e considerar o impacto de produtos e regiões muito frequentes nas recomendações | Encontro 8 |

## 4. Ações de tratamento propostas

Neste encontro o objetivo é diagnosticar os problemas, e não realizar a limpeza definitiva.

A principal ação será separar registros de compras normais de cancelamentos e devoluções. Também será necessário tratar valores ausentes de `CustomerID`, pois a identificação do cliente é importante para gerar recomendações personalizadas.

As duplicatas exatas deverão ser removidas para evitar que um mesmo registro seja contado mais de uma vez. Os valores de `Quantity` e `UnitPrice` também deverão ser investigados antes da modelagem, pois valores negativos ou zero podem representar situações diferentes de uma venda normal.

## 5. Possíveis vieses

A base representa principalmente transações de uma empresa de varejo online do Reino Unido e possui muitos registros relacionados ao Reino Unido. Portanto, o comportamento de outros países aparece em quantidade bem menor.

Também existe um possível viés relacionado aos clientes que não possuem `CustomerID`. Como não é possível relacionar essas compras diretamente a um cliente, o sistema pode aprender melhor os padrões dos clientes identificados e ter menos informação sobre os demais.

Outro ponto é que a própria base representa o comportamento de uma empresa específica, com seus produtos e clientes. Por isso, os padrões encontrados não necessariamente representam todos os consumidores de comércio eletrônico.

Se o sistema errar uma recomendação, o principal impacto esperado é recomendar produtos pouco relevantes ao cliente ou deixar de apresentar produtos que poderiam interessá-lo.

## 6. Primeiras conclusões

A base possui tamanho suficiente para permitir uma análise interessante, mas apresenta problemas que precisam ser tratados antes da criação do modelo.

Os principais pontos de atenção são os valores ausentes em `CustomerID`, as duplicatas, os cancelamentos, as quantidades negativas e os preços zero ou negativos.

Esses problemas serão usados como ponto de partida para a etapa de tratamento e preparação dos dados.

## 7. Referência

Chen, D. (2015). **Online Retail**. UCI Machine Learning Repository. DOI: https://doi.org/10.24432/C5BW33

Fonte oficial: https://archive.ics.uci.edu/dataset/352/online+retail

**Data de acesso:** 30/08/2026.
