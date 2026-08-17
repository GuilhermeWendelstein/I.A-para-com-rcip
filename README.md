# SmartShop AI - Sistema Inteligente de Recomendação de Produtos

## Descrição do Problema

Atualmente, muitas lojas virtuais exibem os mesmos produtos para todos os clientes, sem considerar seus interesses, preferências ou histórico de compras. Essa abordagem reduz a personalização da experiência de compra, dificultando que os consumidores encontrem produtos relevantes de forma rápida e eficiente.

Como consequência, muitos clientes deixam de adquirir produtos que poderiam ser de seu interesse, aumentando a taxa de abandono da plataforma e reduzindo as vendas do comércio eletrônico. Esse problema afeta principalmente pequenas e médias lojas, que muitas vezes não possuem ferramentas inteligentes para personalizar as recomendações oferecidas aos seus usuários.

O SmartShop AI propõe o desenvolvimento de um sistema de recomendação de produtos utilizando Inteligência Artificial. A solução será capaz de analisar dados de compras e comportamento dos clientes para identificar padrões de consumo e sugerir produtos personalizados, melhorando a experiência do usuário e auxiliando o aumento das vendas.

## Público / Contexto

O projeto é voltado para lojas virtuais de pequeno e médio porte que desejam oferecer recomendações personalizadas aos seus clientes.

O sistema será utilizado durante a navegação dos consumidores na plataforma de vendas, apresentando sugestões de produtos com base em seu histórico de compras ou em padrões identificados no comportamento de clientes semelhantes.

## Por que é tratável com IA?

O problema é adequado para a aplicação de Inteligência Artificial porque envolve a identificação de padrões em dados de compras e navegação dos usuários. Algoritmos de recomendação podem analisar esses dados para identificar quais produtos costumam ser adquiridos em conjunto e quais clientes apresentam comportamentos semelhantes.

No Google Colab serão utilizadas bibliotecas de Python para analisar os dados e desenvolver um modelo de recomendação. O sistema utilizará dados públicos ou simulados, sem utilizar informações pessoais dos usuários, respeitando princípios éticos e de privacidade.

## Tipo de Problema

O SmartShop AI se encaixa principalmente no tipo de **recomendação**, pois seu objetivo é sugerir produtos que podem ser relevantes para cada cliente.

O sistema poderá analisar informações sobre histórico de compras e comportamento dos usuários para encontrar padrões e gerar recomendações personalizadas. O agrupamento de clientes com comportamentos semelhantes pode ser utilizado como apoio, mas o objetivo principal continua sendo recomendar produtos.

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

**Exemplo:** Entrada: histórico de compras e comportamento de um cliente. Saída: produtos que podem ser interessantes para esse cliente.

## Soluções Disponíveis

**Amazon**  
Link: https://www.amazon.com/

A Amazon utiliza sistemas de recomendação para apresentar produtos de acordo com os interesses e o comportamento dos clientes. A proposta é semelhante ao SmartShop AI por também utilizar informações dos usuários para oferecer sugestões personalizadas. A principal diferença é que a Amazon possui uma estrutura comercial de grande escala, enquanto o SmartShop AI será desenvolvido como um projeto acadêmico utilizando dados públicos ou simulados.

**Recombee**  
Link: https://www.recombee.com/

A Recombee oferece soluções de recomendação utilizando Inteligência Artificial e dados de comportamento dos usuários para gerar sugestões personalizadas. É semelhante ao SmartShop AI por possuir uma proposta de recomendação de produtos ou conteúdos de acordo com cada usuário. A diferença é que o SmartShop AI será desenvolvido como um protótipo acadêmico utilizando Python e Google Colab, enquanto a Recombee oferece uma solução comercial.

## Limitações Iniciais

Uma das principais limitações pode ser encontrar um conjunto de dados com quantidade e qualidade suficientes de informações. Caso a base seja pequena ou não possua informações suficientes sobre o comportamento dos clientes, as recomendações podem não ser tão precisas.

Outra limitação é o caso de novos usuários ou produtos. Quando ainda não existem dados suficientes sobre eles, pode ser difícil para o sistema identificar quais produtos serão mais adequados para recomendação.

Também será necessário ter cuidado com a privacidade dos dados. Por isso, inicialmente serão utilizados conjuntos de dados públicos ou dados simulados, evitando informações pessoais reais dos usuários.

## Abordagens de IA

### Tabela Comparativa

| Abordagem | Como funcionaria no projeto | Vantagens | Desvantagens | Viabilidade no semestre |
|---|---|---|---|---|
| Aprendizado de Máquina | Analisaria os dados de compras e comportamento dos clientes para encontrar padrões e gerar recomendações de produtos. | Consegue identificar padrões nos dados e gerar recomendações mais personalizadas. | Depende da quantidade e qualidade dos dados disponíveis. | Alta, utilizando Python e Google Colab. |
| Sistemas Especialistas | Utilizaria regras definidas manualmente, como recomendar um produto específico quando o cliente comprar outro. | É simples de entender e desenvolver. | Depende de muitas regras criadas manualmente e pode ficar limitado com muitos produtos e comportamentos. | Alta, mas com recomendações mais limitadas. |

## Abordagem Escolhida

A abordagem escolhida para o SmartShop AI é o **Aprendizado de Máquina**.

Essa escolha foi feita porque o projeto precisa analisar dados de compras e comportamento dos clientes para encontrar padrões e gerar recomendações. Em vez de criar manualmente uma regra para cada situação, o modelo poderá utilizar os dados disponíveis para identificar relações entre produtos e clientes.

Além disso, o uso de Python e Google Colab torna essa abordagem viável dentro do prazo do semestre.

## Regras suficientes?

Uma solução baseada somente em regras seria possível, mas seria limitada para o objetivo do SmartShop AI.

Por exemplo, seria possível criar uma regra como "se o cliente comprar um celular, recomendar uma capinha". Porém, conforme aumenta a quantidade de produtos e clientes, seria necessário criar muitas regras manualmente.

Por isso, o Aprendizado de Máquina é mais adequado, pois pode encontrar padrões nos dados sem que todas as relações precisem ser definidas manualmente.

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

O projeto não terá como objetivo criar uma loja virtual completa, realizar recomendações em tempo real para usuários reais ou utilizar dados pessoais reais de clientes.

## Riscos Técnicos Iniciais

Uma das principais dificuldades pode ser a qualidade e quantidade dos dados. Caso o conjunto de dados seja pequeno ou tenha muitos dados incompletos, o modelo pode gerar recomendações menos precisas.

Outro risco é a complexidade do modelo em relação ao prazo do semestre. Um sistema de recomendação muito avançado poderia exigir mais tempo e conhecimento para ser desenvolvido, por isso a proposta será mantida dentro de um nível adequado ao projeto.

Também existe o risco de novos usuários ou produtos possuírem poucos dados, dificultando a geração de recomendações para eles.

## Possíveis Fontes de Dados

- Kaggle - Conjunto de dados sobre comportamento no comércio eletrônico
- Kaggle - Conjunto de dados de varejo online
- Dados simulados de compras e produtos

## Lista de Pendências Atualizada

- [x] Criar o repositório no GitHub.
- [x] Buscar possíveis conjuntos de dados de e-commerce.
- [x] Definir o tipo de problema como recomendação.
- [x] Pesquisar soluções semelhantes.
- [ ] Analisar o conjunto de dados escolhido.
- [ ] Realizar o tratamento e limpeza dos dados.
- [ ] Explorar os dados e identificar padrões de compra.
- [ ] Desenvolver um algoritmo de recomendação de produtos.
- [ ] Testar o modelo utilizando o Google Colab.
- [ ] Avaliar a qualidade das recomendações.
- [ ] Documentar o projeto e os resultados obtidos.
