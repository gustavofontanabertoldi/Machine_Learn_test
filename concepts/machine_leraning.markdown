# **Machine Learning**

## 📌 Como a máquina aprende?

> **Dados → Processamento → Modelo**

---

## 📊 Tipos de dados

Em Machine Learning, os dados mais comuns são **tabulares (tabelas)**.  
Essas tabelas possuem três elementos principais:

- **Atributos:** colunas dos dados tabulares.  
- **Instâncias:** linhas (exceto o cabeçalho).  
- **Classes:** objetivo ou rótulo que se deseja prever.  

---

## 🧩 Tarefas em Machine Learning

| **Classificação** | **Regressão** | **Agrupamento** | **Regras de Associação** |
| ----------------- | ------------- | ---------------- | ------------------------- |
| Predizer um atributo especial chamado “classe”. | Prever valores numéricos contínuos. | Agrupar dados com base em características matemáticas. | Identificar relações frequentes entre itens de um conjunto. |
| Supervisionado | Supervisionado | Não supervisionado | Supervisionado ou não supervisionado |

---

## 📐 Medindo o desempenho do modelo

- **Treino:** algoritmo processa os dados e gera um modelo.  
- **Validação:** dados usados para ajuste fino do modelo.  
- **Teste:** dados usados para avaliar a performance final.  

---

## ⚙️ Técnicas de treino

- **Hold-out:** separa 70% dos dados para treino e 30% para teste.  
- **Validação Cruzada (k-fold):** divide os dados em *k* subconjuntos; cada subconjunto é usado como teste uma vez.  
- **Leave-one-out:** variação da validação cruzada, mas deixa apenas **1 instância** de fora por vez.  
- **Subamostragem:** semelhante ao hold-out, mas repetido várias vezes com amostras aleatórias.  

---

## 📏 Generalização x Overfitting x Underfitting

- **Generalização (ideal):** bom desempenho tanto em treino quanto em produção.  
- **Overfitting (superajuste):** modelo aprende *demais* os dados de treino e não generaliza bem.  
  - **Causas:** poucos dados, modelo complexo, inconsistência nos dados, má seleção de atributos, falta de validação cruzada.  
- **Underfitting (subajuste):** modelo muito simples, incapaz de capturar padrões.  
  - **Causas:** simplicidade excessiva, poucos dados, má seleção de atributos, hiperparâmetros mal ajustados.  

---

## 🧮 Matriz de Confusão (Classificação)

|  | Classe real positiva | Classe real negativa |
| - | ------------------ | --------------------- |
| **Classe prevista positiva** | Verdadeiros Positivos (VP) | Falsos Positivos (FP) |
| **Classe prevista negativa** | Falsos Negativos (FN) | Verdadeiros Negativos (VN) |

### Métricas principais

- **Acurácia:** `(VP + VN) / (VP + VN + FP + FN)`  
- **Precisão:** `VP / (VP + FP)`  
- **Recall (Sensibilidade):** `VP / (VP + FN)`  
- **Especificidade:** `VN / (VN + FP)`  
- **F1 Score:** `2 × (Precisão × Recall) / (Precisão + Recall)`  

---

## 📈 ROC e AUC

A **ROC (Receiver Operating Characteristic)** é uma curva usada para avaliar classificadores binários.  
A métrica **AUC-ROC** mede a área sob essa curva:

- Valor entre **0 e 1**.  
- Quanto mais próximo de **1**, melhor a performance do classificador.  

---
