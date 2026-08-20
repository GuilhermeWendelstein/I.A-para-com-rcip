# SmartShop AI - Sistema Inteligente de Recomendação de Produtos

## Descrição do Problema

Atualmente, muitas lojas virtuais exibem os mesmos produtos para todos os clientes, sem considerar seus interesses, preferências ou histórico de compras. Essa abordagem reduz a personalização da experiência de compra, dificultando que os consumidores encontrem produtos relevantes de forma rápida e eficiente.

Como consequência, muitos clientes deixam de adquirir produtos que poderiam ser de seu interesse, aumentando a taxa de abandono da plataforma e reduzindo as vendas do comércio eletrônico. Esse problema afeta principalmente pequenas e médias lojas, que muitas vezes não possuem ferramentas inteligentes para personalizar as recomendações oferecidas aos seus usuários.

O SmartShop AI propõe o desenvolvimento de um sistema de recomendação de produtos utilizando Inteligência Artificial. A solução será capaz de analisar dados de compras e comportamento dos clientes para identificar padrões de consumo e sugerir produtos personalizados, melhorando a experiência do usuário e auxiliando o aumento das vendas.

## Público / Contexto

O projeto é voltado para lojas virtuais de pequeno e médio porte que desejam oferecer recomendações personalizadas aos seus clientes.

O sistema será utilizado durante a navegação dos consumidores na plataforma de vendas, apresentando sugestões de produtos com base em seu histórico de compras ou em padrões identificados no comportamento de clientes semelhantes.

## Por que é tratável com IA?

O problema é adequado para a aplicação de Inteligência Artificial porque envolve a identificação de padrões em dados de compras e navegação dos usuários. Esses padrões podem ser difíceis de identificar manualmente, principalmente quando existe uma grande quantidade de produtos e clientes.

Algoritmos de recomendação podem analisar esses dados para identificar quais produtos costumam ser adquiridos em conjunto e quais clientes apresentam comportamentos semelhantes. Com isso, o sistema pode utilizar essas informações para gerar recomendações de produtos mais relevantes.

No Google Colab serão utilizadas bibliotecas de Python para analisar os dados e desenvolver um modelo de recomendação. O sistema utilizará dados públicos ou simulados, sem utilizar informações pessoais dos usuários, respeitando princípios éticos e de privacidade.

## Tipo de Problema

O SmartShop AI se encaixa principalmente no tipo de **recomendação**, pois seu objetivo é sugerir produtos que podem ser relevantes para cada cliente.

O sistema poderá analisar informações sobre histórico de compras e comportamento dos usuários para encontrar padrões e gerar recomendações personalizadas. O agrupamento de clientes com comportamentos semelhantes pode ser utilizado como apoio, mas o resultado principal do projeto será a recomendação de produtos.

## Entradas e Saídas Esperadas

**Entradas:**

- Histórico de compras dos clientes;
- Produtos comprados;
- Produtos visualizados, caso estejam disponíveis no conjunto de dados;
- Categorias dos produtos;
- Preços dos produtos;
- Relação entre produtos comprados em conjunto.

**Saídas:**

- Lista de produtos recomendados;
- Ranking dos produtos mais relevantes para cada cliente.

**Exemplo:** Entrada: histórico de compras e comportamento de um cliente. Saída: uma lista de produtos que podem ser interessantes para esse cliente.

## Soluções Disponíveis

**Amazon**  
[Link:] (https://www.amazon.com/)

A Amazon utiliza sistemas de recomendação para apresentar produtos de acordo com os interesses e o comportamento dos clientes. A proposta é semelhante ao SmartShop AI por também utilizar informações dos usuários para oferecer sugestões personalizadas. A principal diferença é que a Amazon possui uma estrutura comercial de grande escala, enquanto o SmartShop AI será desenvolvido como um projeto acadêmico, utilizando dados públicos ou simulados e com um escopo menor.

**Recombee**  
[Link:] (https://www.recombee.com/)

A Recombee oferece soluções de recomendação utilizando Inteligência Artificial e dados de comportamento dos usuários para gerar sugestões personalizadas. É semelhante ao SmartShop AI por possuir uma proposta de recomendar produtos ou conteúdos de acordo com cada usuário. A diferença é que o SmartShop AI será desenvolvido como um protótipo acadêmico utilizando Python e Google Colab, enquanto a Recombee oferece uma solução comercial pronta para utilização.

## Limitações Iniciais

Uma das principais limitações pode ser encontrar um conjunto de dados com quantidade e qualidade suficientes de informações. Caso a base seja pequena ou não possua informações suficientes sobre o comportamento dos clientes, as recomendações podem não ser tão precisas.

Outra limitação é o caso de novos usuários ou produtos. Quando ainda não existem dados suficientes sobre eles, pode ser difícil para o sistema identificar quais produtos serão mais adequados para recomendação.

Também será necessário ter cuidado com a privacidade dos dados. Por isso, inicialmente serão utilizados conjuntos de dados públicos ou dados simulados, evitando informações pessoais reais dos usuários.

## Abordagens de IA

### Tabela Comparativa

| Abordagem | Como funcionaria no projeto | Vantagens | Desvantagens | Viabilidade no semestre |
|---|---|---|---|---|
| Aprendizado de Máquina | Analisaria os dados de compras e comportamento dos clientes para identificar padrões e gerar recomendações de produtos. | Consegue encontrar padrões nos dados e pode gerar recomendações mais personalizadas sem precisar criar todas as regras manualmente. | Depende da quantidade e qualidade dos dados disponíveis e pode apresentar resultados menos precisos quando existem poucos dados. | Alta, utilizando Python, bibliotecas de IA e Google Colab. |
| Sistemas Especialistas | Utilizaria regras definidas manualmente, como recomendar uma capinha quando o cliente comprar um celular. | É simples de entender, desenvolver e testar, principalmente em situações com poucas regras. | Exige a criação manual de muitas regras e pode se tornar difícil de manter conforme aumenta a quantidade de produtos e comportamentos. | Alta, porém com um sistema mais limitado e menos flexível. |

## Abordagem Escolhida

A abordagem escolhida para o SmartShop AI é o **Aprendizado de Máquina**.

Essa escolha foi feita porque o principal problema do projeto é encontrar padrões nos dados de compras e comportamento dos clientes para gerar recomendações. O Aprendizado de Máquina é adequado para esse cenário porque permite que o sistema utilize os dados disponíveis para identificar relações entre produtos e comportamentos dos usuários.

Por exemplo, em vez de criar manualmente uma regra para cada combinação de produtos, o modelo poderá analisar os dados e identificar quais produtos costumam aparecer relacionados nas compras. Isso torna a abordagem mais adequada para um sistema de recomendação.

Além disso, o uso de Python e Google Colab torna essa abordagem viável dentro do prazo do semestre, permitindo desenvolver e testar um modelo em uma escala adequada ao projeto.

## Regras suficientes?

Uma solução baseada somente em regras seria possível, mas não seria suficiente para atender completamente ao objetivo do SmartShop AI.

Por exemplo, seria possível criar uma regra como "se o cliente comprar um celular, recomendar uma capinha". Esse tipo de regra funciona para situações específicas, mas conforme aumenta a quantidade de produtos e clientes, seria necessário criar e atualizar muitas regras manualmente.

Além disso, regras fixas teriam dificuldade para identificar padrões que não foram definidos previamente. Por isso, o Aprendizado de Máquina é mais adequado ao projeto, pois pode encontrar padrões nos dados e utilizar essas informações para gerar recomendações sem que todas as relações precisem ser cadastradas manualmente.

## Escopo do Projeto Atualizado

Até o final do semestre, o SmartShop AI terá como objetivo:

- Analisar um conjunto de dados de comércio eletrônico;
- Realizar o tratamento e limpeza dos dados;
- Explorar os dados e identificar padrões de compra;
- Desenvolver um modelo de recomendação utilizando Aprendizado de Máquina;
- Gerar recomendações de produtos;
- Testar o modelo utilizando o Google Colab;
- Avaliar a qualidade das recomendações;
- Documentar os resultados obtidos.

O projeto não terá como objetivo criar uma loja virtual completa, realizar recomendações em tempo real para usuários reais, utilizar dados pessoais reais de clientes ou desenvolver um sistema de recomendação em escala comercial.

## Riscos Técnicos Iniciais

Uma das principais dificuldades pode ser a qualidade e quantidade dos dados. Caso o conjunto de dados seja pequeno ou tenha muitos dados incompletos, o modelo pode gerar recomendações menos precisas.

**Mitigação:** procurar datasets com uma quantidade adequada de registros e realizar uma etapa de análise, limpeza e tratamento dos dados antes de desenvolver o modelo.

Outro risco é a complexidade do modelo em relação ao prazo do semestre. Um sistema de recomendação muito avançado poderia exigir mais tempo e conhecimento para ser desenvolvido.

**Mitigação:** utilizar uma abordagem de Aprendizado de Máquina compatível com o nível do projeto e priorizar uma solução funcional antes de tentar implementar recursos mais avançados.

Também existe o risco de novos usuários ou produtos possuírem poucos dados, dificultando a geração de recomendações para eles.

**Mitigação:** utilizar inicialmente os dados disponíveis no conjunto escolhido e considerar recomendações mais gerais, como produtos populares ou relacionados, quando não houver histórico suficiente.

## Possíveis Fontes de Dados

- Kaggle - Conjunto de dados sobre comportamento no comércio eletrônico
- Kaggle - Conjunto de dados de varejo online
- Dados simulados de compras e produtos

## Lista de Pendências Atualizada

- [x] Criar o repositório no GitHub.
- [x] Buscar possíveis conjuntos de dados de e-commerce.
- [x] Definir o tipo de problema como recomendação.
- [x] Pesquisar soluções semelhantes.
- [x] Comparar possíveis abordagens de IA.
- [x] Definir o Aprendizado de Máquina como abordagem escolhida.
- [ ] Analisar o conjunto de dados escolhido.
- [ ] Realizar o tratamento e limpeza dos dados.
- [ ] Explorar os dados e identificar padrões de compra.
- [ ] Desenvolver um algoritmo de recomendação de produtos.
- [ ] Testar o modelo utilizando o Google Colab.
- [ ] Avaliar a qualidade das recomendações.
- [ ] Documentar o projeto e os resultados obtidos.
