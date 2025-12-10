Documentação do Projeto – Predição de Elegibilidade de Empréstimos

Visão Geral
Este projeto usa modelos de Árvore de Decisão e Floresta Aleatória para prever se um cliente provavelmente terá um empréstimo aprovado. A ideia é identificar os fatores que influenciam essa decisão e comparar diferentes modelos.

Objetivo
Criar um fluxo completo de Machine Learning: preparar dados, explorar informações, treinar modelos, avaliar resultados e interpretar o que realmente importa para a tomada de decisão.

O Conjunto de Dados
O dataset contém dados de clientes, incluindo:
- renda anual
- valor solicitado
- tempo do empréstimo
- score de crédito
- finalidade do empréstimo
- situação habitacional
- relação dívida/renda
- tempo de emprego
A coluna alvo indica quem teve aprovação (1) ou não (0).

Pré-processamento
Para os modelos funcionarem bem, foram realizados:
- tratamento de valores ausentes
- padronização de variáveis numéricas
- transformação de variáveis categóricas (OneHotEncoding)
- separação entre treino e teste
- criação de um pipeline para organizar tudo e evitar vazamento de informação

Análise Exploratória
Alguns padrões identificados:
- maior score de crédito → maior chance de aprovação
- renda mais alta também aumenta probabilidade
- valor solicitado e dti influenciam o risco
- diferentes finalidades de empréstimo possuem taxas distintas de aprovação

Modelagem
Árvores de Decisão: simples de interpretar, mas podem gerar overfitting dependendo da profundidade.
Florestas Aleatórias: conjunto de várias árvores, resultando em previsões mais estáveis. Diferentes quantidades de árvores e profundidades foram testadas.

Avaliação
Métricas utilizadas:
- acurácia
- precisão
- recall
- f1-score
- matriz de confusão
A Floresta Aleatória apresentou melhor desempenho geral.

O Que Mais Importou para o Modelo
1. score de crédito
2. renda
3. valor solicitado
4. dti
5. tempo de emprego

Conclusões
A Floresta Aleatória é o modelo recomendado. Ela tem melhor capacidade de generalização e maior consistência nos resultados. O pipeline criado facilita melhorias futuras e adaptações em produção.

Próximos Passos
- otimização avançada via GridSearchCV ou Optuna
- balanceamento de classes com SMOTE
- criação de API para deploy
- monitoramento contínuo do modelo
