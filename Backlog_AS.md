# Backlog atualizado — SmartShop AI
## Planejamento até a AS — Encontro 17

Este backlog reúne as tarefas concluídas, as melhorias pendentes e os artefatos necessários para a entrega final. Os status devem ser atualizados conforme cada atividade for realmente executada.

## 1. Atividades concluídas

| Tarefa | Status | Evidência |
|---|---|---|
| Criar o repositório e organizar o projeto | Concluído | Repositório do SmartShop AI |
| Selecionar e documentar o dataset Online Retail | Concluído | Fonte e descrição dos dados no projeto |
| Realizar limpeza e preparação dos dados | Concluído | `Limpeza.ipynb` e `dados_tratados.csv` |
| Construir características para representar os clientes | Concluído | Notebook do modelo |
| Treinar o baseline e a Árvore de Decisão | Concluído | Notebook da Atividade 10 |
| Comparar o modelo com o baseline | Concluído | Acurácia de 72,40% contra 61,61% |
| Analisar métricas e matriz de confusão | Concluído | Resultados do teste e slides da AP2 |
| Documentar o recall baixo e os falsos negativos | Concluído | Análise da classe `Comprou novamente` |
| Preparar os slides da AP2 | Concluído | PDF da apresentação |
| Atualizar a documentação do projeto com os resultados da AP2 | Concluído | README do projeto |

## 2. Melhorias técnicas pendentes

| Tarefa | Status | Prazo planejado | Critério de conclusão |
|---|---|---|---|
| Testar a árvore com `class_weight='balanced'` | A fazer | Encontros 12–13 | Experimento executado e métricas registradas |
| Avaliar outras configurações da Árvore de Decisão | A fazer | Encontros 12–13 | Resultados comparados com a árvore atual |
| Investigar características adicionais de clientes | A fazer | Encontros 12–14 | Características documentadas e avaliadas sem vazamento |
| Comparar os modelos e escolher uma configuração final | A fazer | Encontros 13–14 | Justificativa baseada nas métricas e na matriz de confusão |
| Definir uma forma de avaliar a recomendação de produtos | A fazer | Encontros 14–15 | Critério de avaliação documentado |
| Desenvolver a etapa de recomendação de produtos | A fazer | Encontros 14–16 | Sistema produzindo uma lista de produtos recomendados |
| Avaliar e documentar a qualidade das recomendações | A fazer | Encontros 15–16 | Resultados e limitações descritos |

## 3. Documentação e entrega final

| Tarefa | Status | Prazo planejado | Critério de conclusão |
|---|---|---|---|
| Executar o notebook final do início ao fim | A fazer | Encontro 16 | Execução concluída sem erros e resultados reproduzíveis |
| Revisar e completar o README | A fazer | Encontro 16 | Projeto, dados, método, resultados, limitações e instruções documentados |
| Elaborar o relatório final da AS | A fazer | Encontro 16 | Relatório com método, resultados, discussão e conclusão |
| Escrever a análise ética e crítica | A fazer | Encontro 16 | Riscos, limitações e cuidados de uso documentados |
| Documentar limitações e melhorias futuras | A fazer | Encontro 16 | Limitações atuais e próximos passos descritos |
| Organizar evidências de execução | A fazer | Encontro 16 | Prints ou outros registros dos resultados finais |
| Conferir dependências, arquivos e links do repositório | A fazer | Encontro 16 | Arquivos acessíveis e instruções verificadas |
| Preparar a apresentação e treinar perguntas técnicas | Em andamento | Encontros 12–16 | Explicação sem leitura e respostas sobre decisões técnicas |
| Conferir a entrega completa e os critérios da AS | A fazer | Antes do Encontro 17 | Checklist final revisado |

## 4. Plano de trabalho

**Encontros 12–13:** testar configurações do modelo e registrar os resultados, mantendo a árvore atual como referência.

**Encontros 13–14:** avaliar características adicionais, comparar experimentos e justificar a configuração escolhida.

**Encontros 14–16:** desenvolver e avaliar a recomendação de produtos, revisar a documentação e preparar os artefatos finais.

**Encontro 16:** executar o notebook integralmente, conferir o repositório, organizar as evidências e finalizar a apresentação.

**Encontro 17:** apresentar a versão final da AS, com resultados, limitações, decisões técnicas e recomendações devidamente documentados.

Este cronograma é uma proposta de organização e deve ser ajustado caso o cronograma oficial da disciplina tenha prazos diferentes.

## 5. Prioridades para evitar pendências

- [ ] Melhorar ou justificar tecnicamente o recall do classificador.
- [ ] Registrar os resultados dos experimentos, inclusive os que não trouxerem melhora.
- [ ] Desenvolver a etapa de recomendação de produtos.
- [ ] Executar o notebook final do início ao fim.
- [ ] Finalizar README e relatório.
- [ ] Incluir análise ética, limitações e melhorias futuras.
- [ ] Organizar evidências de execução.
- [ ] Praticar a explicação do modelo, da data de corte, de `stratify`, do baseline e das métricas.
- [ ] Conferir todos os itens exigidos para a AS.

---

# TRECHO PARA ADICIONAR AO README

## Revisão técnica e planejamento da AS

A revisão técnica da AP2 identificou resultados positivos na comparação com o baseline e na preparação dos dados, além de limitações que precisam ser investigadas antes da entrega final. O principal problema de desempenho é o recall de 38,56% para a classe `Comprou novamente`, com 188 falsos negativos. Também foi identificada a necessidade de reforçar o domínio das decisões técnicas para a apresentação final.

Os próximos passos são testar configurações e características adicionais, comparar resultados, desenvolver e avaliar a etapa de recomendação de produtos e finalizar os artefatos da AS.

### Documentos

- [Revisão técnica da AP2](docs/Atividade11_Revisao_Tecnica.md)
- [Backlog atualizado da AS](docs/Backlog_AS.md)

### Observação

Os status do backlog devem refletir o estado real do projeto. As tarefas ainda não executadas permanecem marcadas como **A fazer**.
