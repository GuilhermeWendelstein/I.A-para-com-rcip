# Diagnóstico da Qualidade dos Dados - SmartShop AI

## 1. Base analisada

A base utilizada no projeto é o dataset **Online Retail**, disponibilizado pelo **UCI Machine Learning Repository**.

A base possui **541.909 registros e 8 colunas** no DataFrame utilizado no projeto.

Os dados representam transações de uma empresa de varejo online do Reino Unido realizadas entre 01/12/2010 e 09/12/2011.

Fonte oficial:
https://archive.ics.uci.edu/dataset/352/online+retail

## 2. Diagnóstico dos problemas de qualidade

### 2.1 Dados ausentes

| Coluna | Valores ausentes | Proporção |
|---|---:|---:|
| CustomerID | 135.080 | 24,93% |
| Description | 1.454 | 0,27% |
| Demais colunas | 0 | 0% |

O principal problema de ausência está em `CustomerID`.

Como o SmartShop AI pretende gerar recomendações personalizadas por cliente, a ausência dessa informação limita a possibilidade de relacionar determinadas compras a clientes específicos.

## 2.2 Dados duplicados

Foram identificadas **5.268 linhas totalmente duplicadas**.

Essas duplicatas exatas deverão ser investigadas e, caso confirmadas como registros repetidos, poderão ser removidas para evitar que o mesmo registro tenha peso maior na análise.

É importante diferenciar isso da repetição de `InvoiceNo`.

Uma mesma compra pode possuir vários produtos e, consequentemente, aparecer em várias linhas. Portanto, a repetição de `InvoiceNo` não significa necessariamente duplicação.

## 2.3 Valores inconsistentes

### Quantity

Foram identificados **10.624 registros com Quantity <= 0**.

Esses valores precisam ser investigados, pois podem representar devoluções, cancelamentos ou outras situações relacionadas à transação.

Não serão removidos automaticamente nesta etapa.

### UnitPrice

Foram identificados **2.517 registros com UnitPrice <= 0**.

Esses registros precisam ser investigados antes da utilização dos dados no modelo, pois valores zero ou negativos podem representar situações diferentes de uma venda normal.

### Cancelamentos

Foram identificados **9.288 registros cujo InvoiceNo começa com "C"**.

Esses registros serão separados das compras válidas durante o tratamento dos dados.

## 2.4 Desbalanceamento

O SmartShop AI é um problema de **recomendação de produtos** e não possui, nesta etapa, uma variável de saída/classe tradicional.

Por esse motivo, o desbalanceamento de classes não se aplica diretamente ao problema neste momento.

Ainda assim, será importante observar a concentração das transações por produtos e clientes, pois produtos muito frequentes podem receber maior peso nas análises e futuras recomendações.

## 3. Tabela de diagnóstico

| Problema encontrado | Onde aparece | Gravidade | Tratamento proposto | Quando será tratado |
|---|---|---|---|---|
| CustomerID ausente | CustomerID | Alta | Avaliar a exclusão desses registros da recomendação personalizada ou utilizá-los apenas em análises gerais | Próxima etapa |
| Description ausente | Description | Baixa | Verificar se a descrição pode ser recuperada a partir do StockCode; caso contrário, avaliar a remoção | Próxima etapa |
| Duplicatas exatas | Registros completos | Média | Investigar e remover duplicatas confirmadas | Próxima etapa |
| Quantity <= 0 | Quantity | Média | Investigar o significado dos registros e separar situações que não representam vendas normais | Próxima etapa |
| UnitPrice <= 0 | UnitPrice | Alta | Investigar os registros e definir se devem ser removidos ou tratados de acordo com o significado da transação | Próxima etapa |
| Cancelamentos | InvoiceNo | Média | Identificar e separar cancelamentos das compras válidas | Próxima etapa |
| Concentração de produtos/clientes | StockCode / CustomerID | Média | Avaliar a distribuição e seu impacto sobre as recomendações | Próxima etapa |

## 4. Ações de tratamento propostas

O objetivo desta etapa é diagnosticar os problemas. A limpeza definitiva será realizada posteriormente.

### CustomerID ausente

Existem duas possibilidades principais:

**Remover da recomendação personalizada:**
- evita criar recomendações associadas a um cliente desconhecido;
- reduz a quantidade de dados disponíveis.

**Manter para análises gerais:**
- preserva informações sobre os produtos vendidos;
- permite análises de frequência e comportamento geral;
- não permite recomendações personalizadas para esses registros.

A decisão será tomada durante a etapa de preparação dos dados.

### Duplicatas

As duplicatas totalmente idênticas deverão ser removidas caso a análise confirme que representam registros repetidos.

### Quantity

Os valores menores ou iguais a zero serão investigados antes da remoção. A decisão considerará o significado de cada transação.

### UnitPrice

Os valores menores ou iguais a zero também serão investigados antes da definição do tratamento.

### Cancelamentos

Os registros identificados como cancelamentos serão separados das compras válidas para evitar que transações canceladas sejam interpretadas automaticamente como comportamento normal de compra.

## 5. Possíveis vieses

### Viés de amostragem

A base representa as transações de uma empresa específica de varejo online e possui forte presença de clientes do Reino Unido.

Portanto, os padrões encontrados podem não representar o comportamento de todos os consumidores de comércio eletrônico.

### Impacto no modelo

O sistema pode aprender padrões muito específicos dessa empresa e desse conjunto de clientes, reduzindo a capacidade de generalização para outros contextos.

Além disso, os registros sem `CustomerID` possuem menos informação para gerar recomendações personalizadas.

### Mitigação

O viés será documentado no projeto e os resultados serão interpretados considerando as características da base.

Os registros sem `CustomerID` serão avaliados separadamente e não serão utilizados indevidamente para gerar recomendações personalizadas.

## 6. Primeiras conclusões

A base possui volume suficiente para permitir uma análise relevante do comportamento de compra.

Porém, foram identificados problemas de qualidade que precisam ser tratados antes da construção do modelo, principalmente:

- valores ausentes em CustomerID;
- valores ausentes em Description;
- duplicatas exatas;
- quantidades menores ou iguais a zero;
- preços menores ou iguais a zero;
- cancelamentos;
- concentração das transações em determinados produtos e clientes.

O diagnóstico será utilizado como base para a próxima etapa de tratamento e preparação dos dados.

## 7. Referência

Chen, D. (2015). **Online Retail**. UCI Machine Learning Repository.

DOI:
https://doi.org/10.24432/C5BW33

Fonte:
https://archive.ics.uci.edu/dataset/352/online+retail

**Data de acesso:** 30/08/2026.
