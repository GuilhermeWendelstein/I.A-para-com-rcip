1. Pontos fortes

Ponto forte 1 — Base de dados bem documentada
A base foi apresentada com fonte, licença, período, DOI e dicionário de dados. Isso facilita a preparação dos dados e reduz dúvidas sobre o significado das variáveis nas próximas etapas.

Ponto forte 2 — Diagnóstico de qualidade dos dados
O projeto identificou problemas concretos da base, como os 135.080 registros sem CustomerID, 5.268 duplicatas exatas, 10.624 registros com Quantity <= 0, 2.517 com UnitPrice <= 0 e 9.288 cancelamentos. Esse diagnóstico servirá para definir o tratamento antes do treinamento do modelo.

2. Pontos que precisam melhorar

Ponto de melhoria 1 — Definição do tipo de aprendizado
Na AP1, o projeto estava formulado como recomendação sem uma variável de saída definida, levando à classificação como não supervisionado. Isso não atende ao caminho de modelos supervisionados previsto para a AP2.

Consequência: não seria possível trabalhar adequadamente com matriz de confusão, precisão, recall e F1.

Ação: reformular o problema como classificação de recompra: prever se determinado cliente comprará determinado produto no período seguinte. Essa definição será aplicada na preparação dos dados e no treinamento do modelo da AP2.

Ponto de melhoria 2 — Tratamento dos registros sem CustomerID
A AP1 identificou 135.080 registros sem identificação de cliente, mas a decisão de tratamento ainda estava em aberto.

Consequência: esses registros não permitem relacionar a compra a um cliente específico, prejudicando a criação dos pares cliente-produto necessários ao novo problema de classificação.

Ação: retirar esses registros da etapa de modelagem, registrando a justificativa técnica no tratamento dos dados.

3. Limitação dos dados

Uma limitação importante é a ausência de CustomerID em 135.080 registros (24,93%).

Como o novo modelo precisa prever a recompra de um cliente, esses registros não podem ser utilizados para criar corretamente as relações entre cliente e produto. Isso pode reduzir a quantidade de dados disponível para treinamento e fazer com que parte do comportamento de compra da base não seja representada pelo modelo.

Decisão: mitigar a limitação removendo esses registros da etapa de modelagem e documentando a perda de dados e sua justificativa. Os demais registros identificados no diagnóstico também serão tratados antes do treinamento.

4. Backlog da AP2
Tarefa	Status	Encontro
Definir o problema como classificação de recompra	Concluído	Encontro 7
Definir pares cliente-produto e criar o rótulo de recompra	A fazer	Encontro 8
Tratar registros sem CustomerID, cancelamentos, duplicatas e valores inválidos	A fazer	Encontro 8
Preparar as variáveis para o modelo	A fazer	Encontro 8
Fazer divisão cronológica entre desenvolvimento e avaliação	A fazer	Encontro 9
Treinar o primeiro modelo de classificação	A fazer	Encontro 9
Testar o modelo	A fazer	Encontro 10
Calcular matriz de confusão, precisão, recall e F1	A fazer	Encontro 10
Interpretar os resultados e identificar pontos de melhoria	A fazer	Encontro 10
Consolidar resultados e preparar a AP2	A fazer	Encontro 11
