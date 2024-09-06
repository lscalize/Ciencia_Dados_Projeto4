# Projeto de Previsão dos Sobreviventes do Titanic

## 1. Descrição Geral
Este projeto tem como objetivo prever a sobrevivência dos passageiros a bordo do Titanic com base em suas características pessoais e variáveis associadas à viagem. A partir da análise dos dados fornecidos, foram aplicadas técnicas de análise exploratória, pré-processamento e modelagem de machine learning para desenvolver o modelo mais eficiente.

## 2. Objetivo
O objetivo do projeto é construir e comparar diversos modelos de machine learning para identificar qual deles é capaz de prever com maior precisão se um passageiro do Titanic sobreviveu ou não, utilizando as variáveis disponíveis no dataset.

## 3. Estrutura do Projeto
O projeto segue as etapas tradicionais de ciência de dados, como importação de dados, análise exploratória, pré-processamento e modelagem de machine learning. O trabalho foi dividido em etapas claras para garantir a clareza e replicabilidade do processo.

## 4. Ferramentas/Bibliotecas Utilizadas
- **Linguagem de Programação**: Python
- **Bibliotecas**:
  - Pandas
  - NumPy
  - Matplotlib
  - Seaborn
  - Scikit-learn
  - XGBoost

## 5. Base de Dados
O dataset utilizado neste projeto foi o conjunto de dados do Titanic fornecido pelo Kaggle na competição "[Titanic: Machine Learning from Disaster](https://www.kaggle.com/c/titanic)". Ele contém informações sobre 891 passageiros, incluindo dados como idade, sexo, classe de bilhete, tarifa, etc., e a variável alvo **Survived**, que indica se o passageiro sobreviveu ou não (1 = Sobreviveu, 0 = Não Sobreviveu).

---

## 6. Etapas do Projeto

### Passo 1: Importação das bibliotecas e visualização inicial dos dados
Iniciamos importando as principais bibliotecas que auxiliam na manipulação, visualização e modelagem dos dados. Realizamos também uma inspeção inicial do dataset, analisando as primeiras linhas e identificando possíveis inconsistências ou dados faltantes.

### Passo 2: Estatísticas Descritivas e Cardinalidade
Nesta etapa, analisamos as estatísticas descritivas das variáveis numéricas, como média, mediana e desvio padrão. Além disso, verificamos a cardinalidade das variáveis categóricas para garantir que não tenhamos colunas com valores excessivamente distintos, o que pode prejudicar a modelagem.

### Passo 3: Visualização Gráfica da Cardinalidade
Para entender melhor a distribuição dos dados, criamos gráficos de barras para visualizar a cardinalidade das variáveis categóricas. Isso nos ajuda a identificar desequilíbrios e decidir sobre possíveis tratamentos.

### Passo 4: Histograma das Tarifas e Idades
Utilizamos histogramas para observar a distribuição das variáveis contínuas, como **Fare** (Tarifa) e **Age** (Idade). Através dessa análise, conseguimos identificar padrões importantes para os próximos passos.

### Passo 5: Boxplot para Identificação de Outliers
Nesta fase, utilizamos boxplots para identificar possíveis outliers nas variáveis contínuas, focando principalmente em **Age** e **Fare**. A remoção ou tratamento de outliers pode melhorar a performance dos modelos de machine learning.

### Passo 6: Correlação entre Variáveis e Visualização com Heatmap
Para entender as relações entre as variáveis numéricas, geramos uma matriz de correlação e a visualizamos por meio de um heatmap. Esta análise nos ajuda a identificar variáveis que podem ter uma correlação positiva ou negativa com o target **Survived**.

### Passo 7: Pré-processamento - Tratamento de variáveis categóricas e valores nulos
Aqui, tratamos os dados faltantes e as variáveis categóricas. Preenchemos os valores nulos com base em médias ou mediana para variáveis numéricas e realizamos imputação de modo para variáveis categóricas.

### Passo 8: Codificação de Variáveis Categóricas
As variáveis categóricas foram convertidas em números através da técnica de **One-Hot Encoding**. Esse processo é essencial para que os modelos de machine learning possam trabalhar com essas variáveis.

### Passo 9: Escalonamento dos Dados Numéricos
Aplicamos a normalização dos dados numéricos para garantir que todas as variáveis estejam na mesma escala, o que é importante para algoritmos que utilizam distâncias (como KNN e SVM).

### Passo 10: Remoção de Colunas de Alta Cardinalidade
Nesta etapa, removemos as colunas que tinham alta cardinalidade ou pouca relevância para a modelagem, como o nome dos passageiros e o número do bilhete.

### Passo 11: Divisão dos Dados em Conjunto de Treinamento e Validação
Dividimos o dataset em conjunto de treinamento (80%) e conjunto de validação (20%) para treinar e avaliar os modelos.

### Passo 12: Treinamento e Avaliação dos Modelos
Vários algoritmos de machine learning foram treinados e avaliados:
- **Regressão Logística**
- **K-Nearest Neighbors (KNN)**
- **Árvore de Decisão**
- **Random Forest**
- **Support Vector Machine (SVM)**
- **Gradient Boosting (XGBoost)**

A métrica de avaliação principal utilizada foi a **acurácia**.

### Passo 13: Ajuste de Hiperparâmetros (Hyperparameter Tuning)
Realizamos a otimização dos hiperparâmetros usando **GridSearchCV** para o modelo de XGBoost, que mostrou-se o mais promissor. Isso nos permitiu ajustar os parâmetros para melhorar a performance final.

---

## 7. Resultados da Análise e Modelagem
Após a comparação de todos os modelos, o **XGBoost** apresentou o melhor desempenho com uma acurácia de **~83%** no conjunto de validação. Abaixo estão as acurácias dos principais modelos testados:

| Modelo                | Acurácia (%) |
|-----------------------|--------------|
| Regressão Logística    | 79.6         |
| K-Nearest Neighbors    | 78.2         |
| Árvore de Decisão      | 80.4         |
| Random Forest          | 82.0         |
| Support Vector Machine | 81.7         |
| **XGBoost**            | **83.0**     |

## 8. Conclusão
O projeto demonstrou a importância do pré-processamento e do ajuste de hiperparâmetros para obter o melhor desempenho dos modelos. O **XGBoost** se destacou como o modelo mais eficaz, devido à sua capacidade de lidar com interações complexas entre as variáveis e realizar ajustes automáticos.

## 9. Sugestão de Próximos Passos
- **Feature Engineering**: Investigar a criação de novas variáveis a partir dos dados existentes, como agrupamento de idades ou tarifas, pode trazer melhorias adicionais.
- **Stacking de Modelos**: Experimente a técnica de ensemble combinando os resultados de múltiplos modelos para aumentar a acurácia.
- **Validação Cruzada**: Implementar uma validação cruzada mais robusta para garantir que os resultados sejam consistentes em diferentes subconjuntos de dados.
