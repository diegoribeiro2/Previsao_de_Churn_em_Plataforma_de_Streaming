# Estudo de Caso: Previsão de Churn em Plataforma de Streaming

## Introdução

Neste projeto, trabalhei com uma plataforma de streaming que enfrenta desafios significativos devido ao alto índice de cancelamentos de assinaturas pelos usuários. A diretoria acredita que é possível prever quais usuários estão mais propensos a deixar a plataforma, permitindo que ações sejam tomadas para reduzir o churn. O objetivo é desenvolver um modelo de classificação que identifique esses usuários com base em seu perfil.

## Dados Utilizados

A base de dados foi obtida a partir de uma adaptação de um problema de e-commerce disponível no Kaggle. Os dados, armazenados em um arquivo CSV, contêm informações detalhadas sobre as contas dos clientes na plataforma de streaming, divididas entre contas Basic, Standard e Premium. As colunas incluem:

| Coluna                  | Descrição                                           | Tipo   |
|-------------------------|----------------------------------------------------|--------|
| client_id               | Código de identificação do cliente                  | Int    |
| age                     | Idade do cliente                                   | Int    |
| gender                  | Gênero do cliente                                  | String |
| region                  | Região de origem do cliente                         | String |
| subscription_days       | Dias de assinatura ativa do cliente                 | Int    |
| subscription_type       | Tipo de conta                                      | String |
| num_contents            | Quantidade de conteúdos assistidos                  | Int    |
| avg_rating              | Avaliação média dos conteúdos da plataforma         | Int    |
| num_active_profiles      | Número de perfis ativos na plataforma               | Int    |
| num_streaming_services  | Quantidade de serviços de streaming que o cliente possui | Int |
| devices_connected        | Quantidade de dispositivos conectados à conta       | Int    |
| churned                 | Se o cliente cancelou a conta ou não               | Int    |

## Etapas de Desenvolvimento

### Etapa 01: Análise Exploratória dos Dados (Data Understanding)

Comecei carregando a base de dados e realizando uma descrição estatística para entender melhor as variáveis disponíveis. Utilize as funções `.info()` e `.isna().sum()` para verificar a quantidade de valores faltantes e a distribuição dos dados.

### Etapa 02: Tratamento dos Dados (Data Preparation)

- Substituí valores “NaN” por 0 nas colunas relevantes (`subscription_days`, `num_streaming_services`, `churned`, `avg_rating`, `devices_connected`).
- Removi linhas nulas nas colunas `gender`, `subscription_type` e `age`.
- Transformei os valores de `churned` de 0 e 1 para "No" e "Yes" para facilitar a interpretação.
- Converti valores flutuantes em inteiros, assegurando que os dados estivessem no formato adequado.

### Etapa 03: Modelagem dos Dados - Regressão Logística

Desenvolvi o modelo de classificação utilizando regressão logística:

- Defini as variáveis X e y.
- Realizei o ajuste do modelo (`.fit`).
- Separei os dados em conjuntos de treino e teste.
- Plotei a matriz de confusão para avaliar a performance do modelo.
- Imprimi métricas de desempenho como precisão e recall.

### Etapa 04: Modelagem dos Dados - Tuning

Realizei o ajuste fino do modelo para melhorar a performance. As etapas foram semelhantes àquelas da regressão logística, incluindo a separação dos dados e a plotagem da matriz de confusão.

### Etapa 05: Modelagem dos Dados - Random Forest

Implementando um modelo de Random Forest, executei as seguintes etapas:

- Montei o grid search para otimizar os hiperparâmetros.
- Realizei o ajuste do modelo (`.fit`).
- Conduzi o tuning e, finalmente, apliquei a modelagem.
- Plotei a matriz de confusão e imprimi as métricas de performance.

## Conclusão

Ao final deste projeto, obtive um modelo de classificação capaz de prever quais usuários têm maior probabilidade de cancelar suas assinaturas. Esses insights são essenciais para a equipe de gestão da plataforma de streaming, pois podem informar ações estratégicas para reduzir o churn e melhorar a retenção de clientes.
