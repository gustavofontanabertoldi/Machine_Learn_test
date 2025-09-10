# Regressão Linear

A **Regressão Linear** é um dos modelos mais fundamentais em aprendizado de máquina e estatística.  
É uma técnica supervisionada usada para prever um valor contínuo (como preço, idade ou temperatura) com base em um ou mais outros valores.  

A ideia principal é encontrar a **melhor linha reta** que se ajuste aos dados, permitindo usar essa linha como base para realizar previsões.  
No caso da **regressão linear simples**, essa linha pode ser representada pela equação:

\[
y = \beta_0 + \beta_1 x
\]

- \( y \): variável dependente (o valor que queremos prever)  
- \( x \): variável independente (a entrada)  
- \( \beta_0 \): intercepto da linha (valor de \( y \) quando \( x = 0 \))  
- \( \beta_1 \): coeficiente angular (mostra quanto \( y \) varia para cada unidade de \( x \))  

Em regressões lineares múltiplas, existem vários \( x \), cada um com seu próprio coeficiente.

---

## Correlação (R)

A **Correlação (R)**, ou **Coeficiente de Correlação**, mede a força e a direção da relação linear entre duas variáveis.

- **Valores:** O valor de R varia de -1 a +1.  
- **Interpretação:**
  - **R = +1:** Correlação linear perfeita e positiva. Quando uma variável aumenta, a outra também aumenta.  
  - **R = -1:** Correlação linear perfeita e negativa. Quando uma variável aumenta, a outra diminui.  
  - **R = 0:** Não há correlação linear entre as variáveis.  

⚠️ **Importante:** A correlação não implica causalidade. Ou seja, o fato de duas variáveis estarem correlacionadas não significa que uma causa a outra.

---

## Coeficiente de Determinação (R²)

O **Coeficiente de Determinação (R²)**, ou **R-quadrado**, é uma métrica que indica a proporção da variância na variável dependente que pode ser explicada pela(s) variável(is) independente(s) no modelo de regressão.

- **Valores:** O valor de R² varia de 0 a 1 (ou 0% a 100%).  
- **Fórmula:**  
\[
R² = (Correlação)^2
\]  

- **Interpretação:**  
  - **R² = 0.75:** 75% da variação na variável dependente é explicada pelo modelo.  
  - **R² = 0:** O modelo não explica nada da variância dos dados.  
  - **R² = 1:** O modelo explica 100% da variação. A linha de regressão se ajusta perfeitamente aos dados.  

O R² nos dá uma ideia de quão bem o modelo de regressão se ajusta aos dados. Quanto maior o R², melhor o ajuste da linha.

---

## Como prever?

Para prever novos valores com regressão linear, basta substituir o valor de entrada \( x \) na equação ajustada:

\[
\hat{y} = \beta_0 + \beta_1 x
\]

- Onde \( \hat{y} \) é o valor previsto.  
- Em regressões múltiplas, a fórmula se estende para incluir todos os coeficientes e variáveis independentes:

\[
\hat{y} = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \dots + \beta_n x_n
\]

---
