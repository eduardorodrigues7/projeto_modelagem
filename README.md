🍷 Wine Quality Red — Machine Learning

Projeto de Machine Learning para analisar e prever a qualidade de vinhos tintos usando características físico-químicas.
Inclui etapas de EDA, pré-processamento, regressão, classificação e AutoML com PyCaret.

📌 Integrantes

Eduardo Rodrigues

Igor Cecim

🎯 Objetivo do Projeto

O projeto tem dois focos principais:

Regressão: prever a nota de qualidade (quality) de um vinho tinto.

Classificação: transformar quality em uma classe binária (“bom” vs “não bom”) e treinar modelos classificadores.

Além disso, foi feita uma comparação entre:

Pipeline manual (scikit-learn)

Pipeline automático (PyCaret / AutoML)

🧾 Dataset

Arquivo utilizado: winequality-red.csv

Linhas: 1599

Colunas: 12

Separador: ;

Sem valores nulos

Target: quality (nota inteira)

🧠 Etapas do Projeto
1. Pré-processamento

Padronização de nomes de colunas.

Remoção de duplicatas.

Tratamento de outliers usando IQR (winsorização/clip).

Normalização com StandardScaler.

2. EDA (Análise Exploratória)

Estatísticas descritivas (describe, info).

Heatmap de correlação.

Pairplot com variáveis mais relevantes.

Observação de relações positivas/negativas com quality.

3. Modelos de Regressão

Regressão Linear (LinearRegression)

Regressão Polinomial grau 2 (PolynomialFeatures + LinearRegression)

Métricas usadas:

MAE

RMSE

R²

4. Modelos de Classificação

Criação de classe binária:

good = 1 para vinhos de qualidade alta (ex.: ≥ 7)

good = 0 caso contrário

Modelos:

Naive Bayes Gaussiano (GaussianNB)

Regressão Logística (LogisticRegression)

Otimização com GridSearchCV

Métricas usadas:

Accuracy

F1-Score

ROC-AUC

Matriz de confusão

5. AutoML com PyCaret

compare_models() para benchmark automático.

tune_model() para otimização.

Executado tanto para Regressão quanto para Classificação.

Principais Resultados (resumo)
Regressão

Regressão Linear teve desempenho razoável (erro médio ~0.5 ponto).

Regressão Polinomial não trouxe ganho significativo.

Classificação

Logística: maior accuracy geral.

Naive Bayes: melhor F1 (mais sensível à classe “bom”).

GridSearch trouxe melhora pequena.

AutoML

PyCaret facilitou a comparação de vários modelos e confirma o desempenho próximo ao obtido manualmente.

🛠 Tecnologias e Bibliotecas

Python 3.x

Pandas / NumPy

Matplotlib / Seaborn

Scikit-learn

PyCaret

📌 Observações

O dataset é desbalanceado em notas altas, o que dificulta a predição da classe “vinho bom”.

Resultados podem ter pequenas variações conforme o random_state e splits.
