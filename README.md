# SmartShop AI - Sistema Inteligente de Recomendação de Produtos
## Descrição do Problema

Atualmente, muitas lojas virtuais exibem os mesmos produtos para todos os clientes, sem considerar seus interesses, preferências ou histórico de compras. Essa abordagem reduz a personalização da experiência de compra, dificultando que os consumidores encontrem produtos relevantes de forma rápida e eficiente.

Como consequência, muitos clientes deixam de adquirir produtos que poderiam ser de seu interesse, aumentando a taxa de abandono da plataforma e reduzindo as vendas do comércio eletrônico. Esse problema afeta principalmente pequenas e médias lojas, que muitas vezes não possuem ferramentas inteligentes para personalizar as recomendações oferecidas aos seus usuários.

O SmartShop AI propõe o desenvolvimento de um sistema de recomendação de produtos utilizando Inteligência Artificial. A solução será capaz de analisar dados de compras e comportamento dos clientes para identificar padrões de consumo e sugerir produtos personalizados, melhorando a experiência do usuário e auxiliando o aumento das vendas.
---------------------
## Público / Contexto

O projeto é destinado a lojas virtuais de pequeno e médio porte que desejam oferecer recomendações personalizadas aos seus clientes.

O sistema será utilizado durante a navegação dos consumidores na plataforma de vendas, apresentando sugestões de produtos com base em seu histórico de compras ou em padrões identificados no comportamento de clientes semelhantes.
---------------------
## Por que é tratável com IA?

O problema é adequado para a aplicação de Inteligência Artificial porque envolve a identificação de padrões em dados de compras e navegação dos usuários. Algoritmos de recomendação conseguem analisar esses dados para identificar quais produtos costumam ser adquiridos em conjunto e quais clientes apresentam comportamentos semelhantes.

No Google Colab serão utilizadas bibliotecas de Python para analisar os dados e desenvolver um modelo de recomendação. O sistema utilizará dados públicos ou simulados, sem utilizar informações pessoais dos usuários, respeitando princípios éticos e de privacidade.
--------------------
## Tipo de Problema

O SmartShop AI se encaixa principalmente no tipo Recomendação, pois seu objetivo é sugerir produtos que possam ser relevantes para cada cliente.

O sistema poderá analisar informações como histórico de compras e comportamento dos usuários para encontrar padrões e gerar recomendações personalizadas. O agrupamento de clientes com comportamentos semelhantes pode ser utilizado como apoio, mas o objetivo principal continua sendo recomendar produtos.

Entradas e Saídas Esperadas

Entradas:

Histórico de compras dos clientes;
Produtos comprados;
Produtos visualizados, caso estejam disponíveis no dataset;
Categorias dos produtos;
Preços dos produtos;
Relação entre produtos comprados em conjunto.

Saídas:

Lista de produtos recomendados;
Ranking dos produtos mais relevantes para cada cliente.

Exemplo:
Entrada: histórico de compras e comportamento de um cliente.
Saída: produtos que podem ser interessantes para esse cliente.

Soluções Semelhantes

Amazon
Link: https://www.amazon.com/
A Amazon utiliza sistemas de recomendação para apresentar produtos de acordo com os interesses e o comportamento dos clientes. A proposta é semelhante ao SmartShop AI por buscar oferecer sugestões personalizadas para cada usuário.

Recombee
Link: https://www.recombee.com/
A Recombee oferece soluções de recomendação baseadas em Inteligência Artificial, utilizando dados de comportamento para gerar sugestões personalizadas. É semelhante ao SmartShop AI por possuir uma proposta de recomendar produtos ou conteúdos de acordo com cada usuário.

Limitações Iniciais

Uma das principais limitações pode ser encontrar um dataset com quantidade e qualidade suficientes de dados. Caso a base seja pequena ou não possua informações suficientes sobre o comportamento dos clientes, as recomendações podem não ser tão precisas.

Outra limitação é o caso de novos usuários ou produtos. Quando ainda não existem dados suficientes sobre eles, pode ser difícil para o sistema identificar quais produtos seriam mais adequados para recomendar.

Também será necessário ter cuidado com a privacidade dos dados. Por isso, inicialmente serão utilizados datasets públicos ou dados simulados, evitando informações pessoais reais dos usuários.

## Possíveis Fontes de Dados
Kaggle - E-commerce Behavior Dataset
Kaggle - Online Retail Dataset
Dados simulados de compras e produtos
## Backlog Atualizado

- [x] Crie o repositório no GitHub.
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
Kaggle - E-commerce Behavior Dataset
Kaggle - Online Retail Dataset
Dados simulados de compras e produtos
