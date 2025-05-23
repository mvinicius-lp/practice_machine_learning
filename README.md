# Análise e Classificação de Dados Acadêmicos

Este projeto realiza a análise exploratória, pré-processamento e aplicação de modelos de classificação (KNN, Regressão Logística e Random Forest) em um conjunto de dados acadêmicos para prever o status final dos estudantes.

## Índice

- [Visão Geral](#visão-geral)
- [Conjunto de Dados](#conjunto-de-dados)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Pré-processamento](#pré-processamento)
- [Modelos de Classificação](#modelos-de-classificação)
- [Análise Comparativa](#análise-comparativa)
- [Como Executar](#como-executar)
- [Bibliotecas Utilizadas](#bibliotecas-utilizadas)

## Visão Geral

O objetivo principal deste projeto é construir e comparar diferentes modelos de machine learning para classificar o estado final de estudantes (Dropout, Enrolled, Graduated) com base em diversas características. O fluxo de trabalho inclui a importação dos dados, análise exploratória, pré-processamento para lidar com dados categóricos e numéricos, e a aplicação de três algoritmos de classificação: K-Nearest Neighbors (KNN), Regressão Logística e Random Forest. Uma análise comparativa das métricas de desempenho é realizada para determinar o modelo mais adequado.

## Conjunto de Dados

O conjunto de dados utilizado é o "predict students' dropout and academic success" do UCI Machine Learning Repository (ID 697). Este dataset contém diversas informações sobre estudantes, incluindo dados demográficos, fatores sociais, econômicos e acadêmicos.

## Estrutura do Projeto

O projeto está organizado em um notebook Python e segue as seguintes etapas:

1.  **Importação dos Dados:** Carregamento do dataset utilizando a biblioteca `ucimlrepo`.
2.  **Análise dos Dados:** Exploração inicial dos dados, incluindo visualização das primeiras linhas, tipos de dados, contagem de valores ausentes e distribuição da variável alvo.
3.  **Pré-processamento:** Preparação dos dados para o treinamento dos modelos, incluindo:
    *   Identificação de colunas categóricas e numéricas.
    *   Aplicação de One-Hot Encoding para variáveis categóricas.
    *   Aplicação de Standard Scaling para variáveis numéricas.
    *   Divisão dos dados em conjuntos de treino e teste.
4.  **Modelos de Classificação:** Implementação e treinamento dos modelos de KNN, Regressão Logística e Random Forest. É realizada uma busca por hiperparâmetros utilizando `GridSearchCV` e validação cruzada estratificada.
5.  **Análise Comparativa:** Comparação do desempenho dos modelos com e sem escalonamento, utilizando métricas como Acurácia, Precisão, Recall e F1-Score.

## Pré-processamento

O pré-processamento dos dados é crucial para o bom desempenho dos modelos. As etapas realizadas incluem:

*   **Codificação de Variáveis Categóricas:** Utilização de `OneHotEncoder` para transformar variáveis categóricas em representações numéricas adequadas para os algoritmos.
*   **Escalonamento de Variáveis Numéricas:** Aplicação de `StandardScaler` para normalizar as variáveis numéricas, garantindo que nenhuma feature domine o modelo devido à sua escala.
*   **Divisão Treino/Teste:** O dataset é dividido em 80% para treino e 20% para teste, garantindo uma avaliação imparcial do modelo.

## Modelos de Classificação

Os seguintes modelos de classificação foram implementados:

*   **K-Nearest Neighbors (KNN):** Modelo baseado na proximidade dos pontos de dados.
*   **Regressão Logística:** Modelo linear utilizado para problemas de classificação binária e multiclasse.
*   **Random Forest:** Ensemble de árvores de decisão, robusto e geralmente com bom desempenho.

Para cada modelo, foi realizada uma busca exaustiva pelos melhores hiperparâmetros utilizando `GridSearchCV` e `StratifiedKFold` para garantir a validação cruzada adequada.

## Análise Comparativa

Após o treinamento e avaliação de cada modelo, uma análise comparativa é apresentada, exibindo as principais métricas de desempenho (Acurácia, Precisão, Recall, F1-Score) no conjunto de teste. Gráficos são gerados para facilitar a visualização da performance relativa de cada algoritmo.

Também é apresentada uma comparação do impacto do escalonamento nos modelos.

## Como Executar

Para executar este projeto, você precisará de um ambiente Python com as bibliotecas listadas na seção [Bibliotecas Utilizadas](#bibliotecas-utilizadas). Recomenda-se a utilização do Google Colab ou Jupyter Notebook.

1.  Clone o repositório (se aplicável) ou crie um novo notebook no Google Colab.
2.  Copie o código fornecido para as células do notebook.
3.  Instale as bibliotecas necessárias executando a célula com `pip install ucimlrepo`.
4.  Execute as células sequencialmente para realizar as etapas de importação, análise, pré-processamento, treinamento e avaliação dos modelos.

## Bibliotecas Utilizadas

*   `ucimlrepo` (versão especificada no código)
*   `pandas`
*   `numpy`
*   `scikit-learn`
*   `matplotlib`
*   `seaborn`
*   `missingno`
*   `IPython`