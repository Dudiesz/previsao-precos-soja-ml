# Análise Exploratória de Dados e Modelagem Preditiva de Preços Diários da Soja no Brasil

## 📝 Objetivo do Projeto

Este projeto tem como objetivo principal desenvolver um **modelo de Machine Learning (Regressão Linear)** para prever o preço diário da soja no Brasil, utilizando dados históricos reais. A aplicação de conceitos de Ciência de Dados e Machine Learning visa fornecer insights sobre o comportamento dos preços de uma commodity fundamental para o agronegócio brasileiro.

---

## 📊 Contexto e Justificativa

O agronegócio é um pilar da economia nacional, e a volatilidade dos preços de commodities agrícolas como a soja impacta diretamente produtores, distribuidores e consumidores. A capacidade de prever esses preços pode ser uma ferramenta valiosa para **tomada de decisões estratégicas**, planejamento de safra e gestão de riscos no mercado.

---

## 📁 Dados Utilizados

* **Nome do Arquivo:** `preco_soja_10anos.xlsx`
* **Formato:** Arquivo Excel (.xlsx)
* **Conteúdo:** Dados diários de preços da soja no Brasil, abrangendo um período de aproximadamente 10 anos (desde 2015).
* **Estrutura:** Duas colunas principais - `Data` (formato de data) e `Preço` (formato numérico).
* **Status:** Os dados foram considerados tratados, sem valores ausentes significativos ou erros de formato que impedissem a leitura inicial.

---

## 🛠️ Tecnologias e Bibliotecas

O projeto foi desenvolvido em **Python**, utilizando as seguintes bibliotecas principais:

* **`pandas`**: Essencial para manipulação e análise eficiente de dados tabulares (DataFrames).
* **`numpy`**: Utilizado para operações numéricas de alto desempenho, especialmente no cálculo de métricas.
* **`matplotlib`** e **`seaborn`**: Para a criação de visualizações de dados, como a série temporal dos preços e a comparação entre valores reais e previstos, tornando a análise mais intuitiva.
* **`scikit-learn`**: A biblioteca padrão para Machine Learning em Python, utilizada para:
    * `LinearRegression`: O algoritmo de regressão linear para construir o modelo preditivo.
    * Métricas de avaliação: `mean_absolute_error`, `mean_squared_error`, `r2_score`, para quantificar o desempenho do modelo.

---

## 🚀 Principais Etapas da Análise

O desenvolvimento do modelo seguiu os seguintes passos detalhados:

1.  **Carregamento dos Dados:** O arquivo Excel foi lido e as colunas `Data` e `Preço` foram convertidas para os tipos de dados apropriados (`datetime` e `float`).
2.  **Análise Exploratória de Dados (EDA):** Foi realizada uma inspeção inicial dos dados (`.head()`, `.tail()`, `.info()`, `.describe()`) e uma visualização da série temporal para identificar tendências e padrões.
3.  **Engenharia de Features:** Criadas novas variáveis preditoras cruciais para o modelo de série temporal:
    * **Features de Data:** `Mes`, `Dia_do_Ano`, `Ano`, `Dia_da_Semana`, para capturar efeitos sazonais e tendências de longo prazo.
    * **Features de Atraso (Lagged Features) do Preço:** `Preco_Ontem`, `Preco_2_Dias_Atras`, `Preco_7_Dias_Atras`. Estas features são vitais, pois o preço atual da soja é fortemente influenciado pelos preços passados. Linhas com valores `NaN` resultantes dos lags foram removidas.
4.  **Preparação para o Modelo:** As variáveis preditoras (X) e a variável alvo (y) foram definidas. A divisão dos dados em conjuntos de treino (80%) e teste (20%) foi feita **cronologicamente**, garantindo que o modelo fosse treinado com dados passados e avaliado em dados futuros, simulando um cenário real de previsão.
5.  **Construção e Treinamento do Modelo:** Um modelo de **Regressão Linear** foi instanciado e treinado utilizando os dados de treino (`X_treino` e `y_treino`).
6.  **Avaliação do Modelo:** Foram realizadas previsões no conjunto de teste (`X_teste`) e calculadas as seguintes métricas de avaliação para quantificar o desempenho do modelo:
    * **MAE (Mean Absolute Error)**: Mede o erro médio absoluto das previsões.
    * **MSE (Mean Squared Error)**: Mede o erro médio quadrático, penalizando erros maiores.
    * **RMSE (Root Mean Squared Error)**: A raiz quadrada do MSE, fornecendo o erro médio na mesma unidade do preço da soja (R$).
    * **R² (R-squared score)**: Indica a proporção da variância na variável alvo que é explicada pelo modelo.
7.  **Visualização dos Resultados:** Um gráfico de linha foi gerado comparando os preços reais do conjunto de teste com os preços previstos pelo modelo, permitindo uma análise visual clara do ajuste.

---

## 📈 Conclusões e Observações

*(Este é um espaço **importante** para você preencher após executar todas as células do seu Jupyter Notebook e analisar os resultados do seu modelo. Comente sobre o que você observou nas métricas e no gráfico de comparação.)*

* **Desempenho do Modelo:** Qual foi o MAE, RMSE e R² que você obteve? Explique o que esses valores significam. Por exemplo: "O modelo de Regressão Linear apresentou um MAE de X R$ e um RMSE de Y R$, indicando que, em média, as previsões estão a Y R$ de distância do preço real. O R² de Z% sugere que o modelo explica Z% da variabilidade nos preços da soja."
* **Ajuste Visual:** Descreva o que você notou ao comparar as linhas de "Preço Real" e "Preço Previsto" no gráfico. "O gráfico demonstra que o modelo consegue capturar a tendência geral dos preços ao longo do tempo, embora possa apresentar desvios em momentos de alta volatilidade ou mudanças abruptas de preço."
* **Limitações e Próximos Passos (Opcional):** Você pode mencionar as limitações de um modelo de Regressão Linear para séries temporais e sugerir ideias para melhorias futuras, como:
    * Explorar modelos mais avançados para séries temporais (e.g., ARIMA, Prophet, ou modelos de Deep Learning como LSTMs).
    * Incorporar mais variáveis externas (e.g., cotação do dólar, indicadores de mercado de commodities globais, dados climáticos).
    * Realizar uma otimização de hiperparâmetros mais profunda para o modelo.

---

## 🤝 Como Contribuir

Sinta-se à vontade para clonar este repositório, explorar o código, reproduzir a análise e sugerir melhorias. Todas as **pull requests** são bem-vindas!

---

---

Com este `README.md`, seu projeto no GitHub estará muito bem documentado e será fácil para outras pessoas entenderem seus objetivos, metodologia e resultados.

Você precisa de ajuda com mais alguma parte do projeto de programação?
