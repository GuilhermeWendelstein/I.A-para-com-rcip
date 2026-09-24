# Sistema Inteligente de Recomendação de Produtos

## Descrição do Problema

Atualmente, muitas lojas virtuais exibem os mesmos produtos para todos os clientes, sem considerar seus interesses, preferências ou histórico de compras. Essa abordagem reduz a personalização da experiência de compra, dificultando que os consumidores encontrem produtos relevantes de forma rápida e eficiente.

Como consequência, muitos clientes deixam de adquirir produtos que poderiam ser de seu interesse, aumentando a taxa de abandono da plataforma e reduzindo as vendas do comércio eletrônico. Esse problema afeta principalmente pequenas e médias lojas, que muitas vezes não possuem ferramentas inteligentes para personalizar as recomendações oferecidas aos seus usuários.

O projeto propõe o desenvolvimento de um sistema de recomendação de produtos utilizando Inteligência Artificial. A solução será capaz de analisar dados de compras e comportamento dos clientes para identificar padrões de consumo e sugerir produtos personalizados.

## Público / Contexto

O projeto é voltado para lojas virtuais de pequeno e médio porte que desejam oferecer recomendações personalizadas aos seus clientes.

O sistema será utilizado como uma proposta acadêmica de recomendação de produtos, apresentando sugestões com base no histórico de compras e nos padrões identificados nos dados disponíveis.

## Por que é tratável com IA?

O problema é adequado para a aplicação de Inteligência Artificial porque envolve a identificação de padrões em dados de compras. Esses padrões podem ser difíceis de identificar manualmente, principalmente quando existe uma grande quantidade de produtos e clientes.

Algoritmos de recomendação podem analisar os dados para identificar relações entre produtos e comportamentos de compra. Com isso, o sistema poderá utilizar essas informações para gerar recomendações de produtos mais relevantes.

No projeto serão utilizadas bibliotecas de Python e Google Colab para analisar, preparar e posteriormente utilizar os dados na construção do modelo de recomendação.

## Tipo de Problema

O projeto se encaixa principalmente no tipo de **recomendação**, pois seu objetivo é sugerir produtos que podem ser relevantes para cada cliente.

O sistema poderá analisar informações sobre o histórico de compras e os produtos adquiridos para encontrar padrões e gerar recomendações. O agrupamento ou a análise de similaridade entre clientes e produtos poderá ser utilizado como apoio, mas o resultado principal será a recomendação de produtos.

## Entradas e Saídas Esperadas

**Entradas:**

- Histórico de compras dos clientes;
- Produtos comprados;
- Código e descrição dos produtos;
- Quantidade comprada;
- Preço dos produtos;
- Data das compras;
- País do cliente;
- Relação entre produtos comprados.

**Saídas:**

- Lista de produtos recomendados;
- Ranking dos produtos mais relevantes para cada cliente.

**Exemplo:** Entrada: histórico de compras de um cliente. Saída: uma lista de produtos que podem ser interessantes para esse cliente.

## Soluções Disponíveis

**Amazon**  
[Link:](https://www.amazon.com/)

A Amazon utiliza sistemas de recomendação para apresentar produtos de acordo com os interesses e o comportamento dos clientes. A proposta é semelhante ao projeto por também utilizar informações dos usuários para oferecer sugestões personalizadas.

A principal diferença é que a Amazon possui uma estrutura comercial de grande escala, enquanto o projeto será desenvolvido como uma proposta acadêmica utilizando dados públicos e um escopo menor.

**Recombee**  
[Link:](https://www.recombee.com/)

A Recombee oferece soluções de recomendação utilizando Inteligência Artificial e dados de comportamento dos usuários para gerar sugestões personalizadas.

A proposta é semelhante por utilizar dados para gerar recomendações, mas o projeto será desenvolvido como um protótipo acadêmico utilizando Python e Google Colab.

## Limitações Iniciais

Uma das principais limitações está relacionada à qualidade dos dados utilizados. A base possui registros sem identificação de cliente, duplicidades, cancelamentos e valores que precisam ser tratados antes da utilização no modelo.

Outra limitação está relacionada a novos clientes ou produtos. Quando existem poucos dados sobre determinado cliente ou produto, pode ser mais difícil encontrar padrões suficientes para gerar uma recomendação personalizada.

Também é importante considerar que a base representa o comportamento de uma empresa específica. Portanto, os padrões encontrados não necessariamente representam todos os consumidores de comércio eletrônico.

## Abordagens de IA

### Tabela Comparativa

| Abordagem | Como funcionaria no projeto | Vantagens | Desvantagens | Viabilidade no semestre |
|---|---|---|---|---|
| Aprendizado de Máquina | Analisaria os dados de compras e comportamento dos clientes para identificar padrões e gerar recomendações de produtos. | Consegue encontrar padrões nos dados e pode gerar recomendações mais personalizadas. | Depende da quantidade e qualidade dos dados disponíveis. | Alta, utilizando Python e Google Colab. |
| Sistemas Especialistas | Utilizaria regras definidas manualmente, como recomendar um produto relacionado após determinada compra. | Simples de entender e implementar. | Exige criação manual das regras e possui menor flexibilidade. | Alta, porém com um sistema mais limitado. |

## Abordagem Escolhida

A abordagem escolhida para o projeto é o **Aprendizado de Máquina**.

Essa escolha foi feita porque o principal problema é encontrar padrões nos dados de compras para gerar recomendações. O Aprendizado de Máquina permite utilizar os dados disponíveis para identificar relações entre produtos e comportamentos dos clientes.

Em vez de criar manualmente uma regra para cada combinação de produtos, o modelo poderá analisar os registros e identificar relações existentes nos dados.

Além disso, o uso de Python e Google Colab torna a abordagem compatível com o desenvolvimento acadêmico do projeto.

## Regras suficientes?

Uma solução baseada somente em regras seria possível, mas não atenderia completamente ao objetivo do projeto.

Por exemplo, seria possível criar uma regra como "se o cliente comprar um celular, recomendar uma capinha". Esse tipo de regra funciona para situações específicas, mas seria necessário criar diversas regras conforme aumentasse a quantidade de produtos e comportamentos.

Por isso, o Aprendizado de Máquina foi escolhido para permitir que os padrões sejam identificados a partir dos próprios dados.

## Base de Dados

A base utilizada no projeto é a **Online Retail**, disponibilizada pelo **UCI Machine Learning Repository**.

A base possui:

- 541.909 registros;
- 8 colunas;
- 4.070 produtos;
- 4.372 clientes identificados;
- 38 países;
- Período de 01/12/2010 a 09/12/2011;
- Licença CC BY 4.0.

### Fonte

UCI Machine Learning Repository:

https://archive.ics.uci.edu/dataset/352/online+retail

### Principais colunas

| Coluna | Descrição |
|---|---|
| InvoiceNo | Identificador da fatura/transação |
| StockCode | Código do produto |
| Description | Descrição do produto |
| Quantity | Quantidade de produtos |
| InvoiceDate | Data e hora da transação |
| UnitPrice | Preço unitário |
| CustomerID | Identificador do cliente |
| Country | País do cliente |

## Diagnóstico da Qualidade dos Dados

Antes da limpeza definitiva, foi realizada uma análise da qualidade da base.

Foram encontrados os seguintes problemas:

- 135.080 valores ausentes em `CustomerID`;
- 1.454 valores ausentes em `Description`;
- 5.268 linhas totalmente duplicadas;
- 10.624 registros com `Quantity <= 0`;
- 2.517 registros com `UnitPrice <= 0`;
- 9.288 faturas iniciadas com `C`, relacionadas a cancelamentos.

Também foi identificado que a repetição de `InvoiceNo` não significa necessariamente uma duplicata, pois uma mesma fatura pode possuir vários produtos.

Outro ponto observado foi a concentração de registros em determinados países e produtos, o que deve ser considerado durante a análise e construção das recomendações.

## Limpeza e Preparação dos Dados

Após o diagnóstico, foi realizada a etapa de limpeza e preparação da base.

As seguintes transformações foram realizadas:

### Valores ausentes

Os registros sem `CustomerID` foram removidos.

Essa decisão foi tomada porque o identificador do cliente é necessário para relacionar as compras ao histórico de cada cliente. Preencher esse valor artificialmente poderia criar uma identificação incorreta.

Os valores ausentes de `Description` não foram preenchidos artificialmente, pois o `StockCode` pode identificar o produto e essa questão poderá ser revisada posteriormente caso a descrição seja necessária para o modelo.

### Duplicidades

Foram removidas somente as linhas totalmente duplicadas.

A repetição de `InvoiceNo` não foi utilizada como critério de duplicidade, pois uma mesma compra pode possuir diversos produtos.

### Data

A coluna `InvoiceDate` foi convertida para o tipo de data e hora (`datetime`), permitindo que ela seja utilizada corretamente em análises temporais posteriores.

### Cancelamentos

Foram removidos os registros cujo `InvoiceNo` começa com `C`, pois representam cancelamentos e o objetivo desta preparação é trabalhar com compras válidas para a construção das recomendações.

### Quantidade e preço

Foram removidos registros com:

- `Quantity <= 0`;
- `UnitPrice <= 0`.

A decisão foi tomada para manter registros compatíveis com compras válidas, evitando que quantidades ou preços não positivos influenciem diretamente a preparação do modelo.

Essas transformações podem resultar na perda de informações relacionadas a devoluções, ajustes ou outros tipos de transação. Por isso, esse risco foi registrado na tabela de decisões do notebook.

## Registro das Decisões

As transformações realizadas foram registradas considerando:

- transformação aplicada;
- coluna afetada;
- motivo da decisão;
- impacto sobre os dados;
- possíveis riscos.

O registro completo das decisões está documentado no notebook da Atividade 8.

## Data Leakage

Durante a preparação dos dados, não foram ajustadas sobre a base completa transformações que aprendem parâmetros, como escalonamento ou imputação por estatísticas.

A divisão entre treino e teste deverá ser realizada antes de qualquer transformação que aprenda parâmetros dos dados.

Também foi considerado que identificadores como `InvoiceNo` e `CustomerID` não devem ser utilizados diretamente como características do modelo. O `CustomerID` continuará disponível na base tratada para permitir o relacionamento das compras com os clientes, mas deverá ser tratado como identificador na definição das features.

## Artefatos do Projeto

### Notebook

O notebook contém:

- carregamento da base;
- inspeção inicial;
- tratamento dos valores ausentes;
- remoção de duplicidades;
- análise de categorias;
- verificação de codificação;
- verificação de escalonamento;
- conversão de tipos;
- remoção de cancelamentos;
- tratamento de valores inválidos;
- verificação final;
- tabela de decisões;
- verificação de Data Leakage;
- salvamento da base tratada.

**Notebook da Atividade 8:**  
COLE AQUI O LINK DO GOOGLE COLAB

### Base tratada

A base final é salva separadamente como:

`dados_tratados.csv`

A base original não é sobrescrita.

O arquivo tratado é verificado novamente após o salvamento para confirmar que pode ser carregado corretamente.

**Arquivo:** `dados_tratados.csv`

### Diagnóstico

O diagnóstico completo da qualidade dos dados está documentado no arquivo:

`diagnostico_qualidade.md`

## Escopo do Projeto Atualizado

Até o final do semestre, o projeto terá como objetivo:

- Analisar um conjunto de dados de comércio eletrônico;
- Realizar o diagnóstico da qualidade dos dados;
- Realizar a limpeza e preparação dos dados;
- Explorar os dados e identificar padrões de compra;
- Desenvolver um modelo de recomendação utilizando Aprendizado de Máquina;
- Gerar recomendações de produtos;
- Testar o modelo utilizando o Google Colab;
- Avaliar a qualidade das recomendações;
- Documentar os resultados obtidos.

O projeto não terá como objetivo criar uma loja virtual completa, realizar recomendações em tempo real para usuários reais, utilizar dados pessoais reais de clientes ou desenvolver um sistema de recomendação em escala comercial.

## Próximos Passos

Após a limpeza e preparação da base, os próximos passos são:

- Definir as variáveis que serão utilizadas como entradas do modelo;
- Avaliar a necessidade de codificação das variáveis;
- Avaliar a necessidade de escalonamento;
- Explorar os padrões de compra presentes na base tratada;
- Definir e implementar o algoritmo de recomendação;
- Separar os dados adequadamente para treinamento e teste;
- Avaliar as recomendações geradas.

## Riscos Técnicos

Uma das principais dificuldades está relacionada à qualidade dos dados. Registros sem identificação de cliente, cancelamentos, devoluções e valores inválidos podem afetar os padrões utilizados pelo sistema.

**Mitigação:** realizar diagnóstico e limpeza dos dados antes da construção do modelo, mantendo registro das decisões tomadas.

Outro risco é a complexidade do modelo em relação ao prazo do semestre.

**Mitigação:** utilizar uma abordagem de Aprendizado de Máquina compatível com o nível do projeto e priorizar uma solução funcional.

Também existe o risco de novos clientes ou produtos possuírem poucos dados.

**Mitigação:** considerar estratégias de recomendação mais gerais para situações em que não exista histórico suficiente.

## Lista de Pendências Atualizada

- [x] Criar o repositório no GitHub.
- [x] Buscar possíveis conjuntos de dados de e-commerce.
- [x] Definir o tipo de problema como recomendação.
- [x] Pesquisar soluções semelhantes.
- [x] Comparar possíveis abordagens de IA.
- [x] Definir o Aprendizado de Máquina como abordagem escolhida.
- [x] Escolher a base Online Retail.
- [x] Realizar o diagnóstico da qualidade dos dados.
- [x] Identificar valores ausentes.
- [x] Identificar duplicidades.
- [x] Identificar cancelamentos e valores não positivos.
- [x] Realizar a limpeza e preparação da base.
- [x] Registrar as decisões de tratamento.
- [x] Verificar possíveis situações de Data Leakage.
- [x] Salvar a base tratada separadamente da base original.
- [ ] Explorar os dados tratados e identificar padrões de compra.
- [ ] Definir as features utilizadas pelo modelo.
- [ ] Desenvolver o algoritmo de recomendação.
- [ ] Testar o modelo utilizando o Google Colab.
- [ ] Avaliar a qualidade das recomendações.
- [ ] Documentar os resultados finais.
