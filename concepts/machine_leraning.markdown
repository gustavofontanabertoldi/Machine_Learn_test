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

## 📏 Métricas de Erro

Usadas principalmente em **regressão** para avaliar a diferença entre valores previstos (ŷᵢ) e valores reais (yᵢ).

- **ME (Mean Error):**  
  Média simples dos erros. Pode ser positiva ou negativa (depende da escala e direção do erro).  
  `Fórmula: ME = (Σ (yᵢ - ŷᵢ)) / n`

- **MAE (Mean Absolute Error):**  
  Média do valor absoluto dos erros. Mede o erro médio sem considerar sinal. (Dependente da escala)  
  `Fórmula: MAE = (Σ |yᵢ - ŷᵢ|) / n`

- **MSE (Mean Squared Error):**  
  Média dos erros elevados ao quadrado. Penaliza mais erros grandes. (Dependente da escala)  
  `Fórmula: MSE = (Σ (yᵢ - ŷᵢ)²) / n`

- **RMSE (Root Mean Squared Error):**  
  Raiz quadrada do MSE. Interpretação mais intuitiva porque retorna à mesma unidade dos dados originais. (Dependente da escala)  
  `Fórmula: RMSE = √((Σ (yᵢ - ŷᵢ)²) / n)`

- **MPE (Mean Percentage Error):**  
  Média percentual dos erros em relação aos valores reais. Pode ser positiva ou negativa, o que dificulta a interpretação em alguns casos. (não depende de escala)
  `Fórmula: MPE = (Σ ((yᵢ - ŷᵢ) / yᵢ)) / n × 100`

- **MAPE (Mean Absolute Percentage Error):**  
  Média percentual **absoluta** dos erros. É a métrica mais usada para avaliar erro relativo, pois sempre retorna valores positivos. (não depende de escala)
  `Fórmula: MAPE = (Σ (|yᵢ - ŷᵢ| / |yᵢ|)) / n × 100`

- **R² (Coeficiente de Determinação):**  
  Mede o quanto o modelo explica da variabilidade dos dados (varia de 0 a 1).  
  `Fórmula: R² = 1 - (Σ (yᵢ - ŷᵢ)² / Σ (yᵢ - ȳ)²)`

---

## 🔠 Categorical Encoding

Muitos algoritmos de Machine Learning não conseguem lidar diretamente com variáveis **categóricas** (ex.: cores, nomes, cidades).  
Por isso, é necessário transformá-las em **números** para que os modelos possam processar os dados.  
Esse processo é chamado de **codificação categórica (categorical encoding).**

Existem várias técnicas, sendo as mais comuns:

---

### 🎯 Label Encoding

O **Label Encoding** transforma cada categoria em um número inteiro.  

Exemplo:  

| Cor     | Codificação |
|---------|-------------|
| Vermelho | 0 |
| Azul     | 1 |
| Verde    | 2 |

✅ **Vantagens:**  

- Simples e rápido.  
- Não aumenta o número de colunas.  

⚠️ **Desvantagens:**

- Introduz uma ordem numérica que pode **não existir** (o modelo pode “achar” que Verde > Azul, por exemplo).  
- Pode causar problemas em algoritmos baseados em distância ou regressão.  

📌 **Quando usar:**

- Em variáveis ordinais (ex.: pequeno, médio, grande).  

---

### 🟦 One-Hot Encoding

O **One-Hot Encoding** cria uma nova coluna para cada categoria, preenchendo com **0 ou 1** para indicar a presença da categoria.  

Exemplo:

| Cor     | Azul | Verde | Vermelho |
|---------|------|-------|----------|
| Vermelho | 0 | 0 | 1 |
| Azul     | 1 | 0 | 0 |
| Verde    | 0 | 1 | 0 |

✅ **Vantagens:**

- Evita a falsa ordem numérica.  
- Funciona bem na maioria dos algoritmos.  

⚠️ **Desvantagens:**

- Aumenta o número de colunas (especialmente se houver muitas categorias → problema de *dimensionalidade*).  
- Pode deixar o modelo mais lento com dados de alta cardinalidade.  

📌 **Quando usar:**

- Em variáveis nominais (sem ordem natural, ex.: cidade, cor, produto).  

---

👉 Além dessas, existem outras técnicas (como **Target Encoding, Binary Encoding, Frequency Encoding**) usadas em casos mais específicos, mas **Label** e **One-Hot** são as bases que você mais vai encontrar no dia a dia.

---

## 🔢 Transformação de Dados Numéricos

Em Machine Learning, muitas vezes lidamos com variáveis em **escalas diferentes**.  
Exemplo: uma coluna pode representar **idade (anos)** e outra **salário (R$)**.  

Se não tratarmos isso, as variáveis com valores maiores podem **dominar** o treinamento do modelo, contribuindo de forma **desbalanceada**.

Além disso, em algoritmos que usam **Gradient Descent**, o escalonamento ajuda a **convergir mais rapidamente** para o mínimo local/global.

---

### ⚖️ Padronização (Z-score)

A **Padronização** transforma os dados para que tenham **média = 0** e **desvio padrão = 1**.  
Ou seja, cada valor passa a representar quantos desvios padrão está distante da média.

📌 **Fórmula:** z = (x - μ) / σ

- `x`: valor original  
- `μ`: média da variável  
- `σ`: desvio padrão da variável  

✅ Bom para dados que seguem (ou quase seguem) uma **distribuição normal (gaussiana)**.  

---

### 📏 Normalização (Min-Max Scaling)

A **Normalização** ajusta os dados para um intervalo fixo, geralmente **[0, 1]**.  
Dessa forma, o menor valor vira **0** e o maior vira **1**, com os demais proporcionais.

📌 **Fórmula:** x' = (x - x_min) / (x_max - x_min)

- `x`: valor original  
- `x_min`: menor valor da variável  
- `x_max`: maior valor da variável  

✅ Útil quando os dados não seguem distribuição normal ou quando queremos manter a escala proporcional.  

⚠️ Pode ser **fortemente impactada por outliers**.  

---

### 🚨 Outliers

**Outliers** são valores que fogem muito do padrão dos dados (ex.: salário de R$ 1.000.000 em um conjunto onde a média é R$ 3.000).  

- Podem **distorter padronização e normalização**, puxando os dados para extremos.  
- Estratégias para lidar com outliers:  
  - Remoção (quando são erros claros de coleta).  
  - Transformações estatísticas (log, raiz quadrada).  
  - Escalonamento robusto (ex.: **RobustScaler** no sklearn, que usa mediana em vez da média).  

---

📌 **Resumo:**

- **Padronização (Z-score):** melhor quando os dados têm distribuição próxima da normal.
- **Normalização (Min-Max):** melhor quando queremos dados em uma escala fixa, mas cuidado com outliers.  
- **Outliers:** precisam ser analisados, pois podem comprometer ambos os métodos.

---

## 🔀 Clustering (Agrupamento)

O **Clustering** é uma técnica de aprendizado **não supervisionado** cujo objetivo é **agrupar dados semelhantes em conjuntos**, chamados de **clusters**.  
Diferente de métodos supervisionados, o clustering não usa rótulos (labels): o próprio algoritmo encontra a **estrutura** e os **padrões** escondidos nos dados.

---

### 📌 Tipos de Agrupamento

Existem diferentes abordagens de agrupamento, dependendo de como os dados são tratados:

- **Agrupamento completo:**  
  Cada instância é atribuída a **apenas um cluster**. Nenhum dado fica de fora.  

- **Agrupamento parcial:**  
  Uma instância pode pertencer a mais de um cluster, ou até não pertencer a nenhum. Útil quando existe **sobreposição** entre grupos.  

- **Modelo difuso (Fuzzy Clustering):**  
  Em vez de atribuir rigidamente cada ponto a um cluster, cada instância recebe um **grau de pertinência** (ex.: 80% no Cluster A, 20% no Cluster B).  

- **Modelo hierárquico:**  
  Cria uma estrutura em forma de árvore (*dendrograma*), permitindo **subgrupos dentro de clusters maiores**.  
  Não exige definir o número de clusters antecipadamente.  

Além disso, os algoritmos podem lidar com os dados de duas formas:  

- **Agrupam todos os pontos:** Ex.: **K-Means**.
- **Podem deixar ruídos de fora:** Ex.: **DBSCAN**, que identifica pontos que não pertencem a nenhum cluster.  

---

### ⚙️ Algoritmos de Clustering

- **K-Means:**  
  - Divide os dados em **k clusters**.  
  - Cada ponto é atribuído ao centroide mais próximo.  
  - Iterativamente, os centroides são recalculados.  
  - ⚠️ É necessário definir o valor de **k** previamente.  

- **K-Medoids:**  
  - Semelhante ao K-Means, mas usa um **ponto real do cluster** como representante (medoide).  
  - ✅ Mais robusto a ruídos e *outliers*.  

- **DBSCAN (Density-Based Spatial Clustering of Applications with Noise):**  
  - Agrupa pontos com base na **densidade local**.  
  - ✅ Detecta clusters de formatos arbitrários.  
  - ✅ Identifica automaticamente **outliers** como ruídos.  
  - ✅ Não precisa definir **k** previamente.  

---

## 🔗 Regras de Associação

As **Regras de Associação** são técnicas de aprendizado não supervisionado usadas para encontrar **relações frequentes entre itens** em grandes bases de dados.  

📌 Exemplo clássico: análise de cestas de supermercado.  
> “Quem compra **pão** também costuma comprar **leite**.”  

Essas regras são expressas na forma: Se {Item A} → Então {Item B}

---

### 📊 Métricas principais

- **Suporte:**  
  Mede a **frequência** com que os itens aparecem juntos no conjunto de dados.  

- **Confiança:**  
  Mede a **probabilidade** de comprar o item B, dado que o item A já foi comprado.  
  - Fórmula:  

    ```Confiança(A → B) = Suporte(A ∧ B) / Suporte(A)```

  - Ex.: Uma confiança de **80%** significa que, em 80% das vezes em que A foi comprado, B também foi.  

- **Lift (Elevação):**  
  Mede se a relação é mais forte do que o esperado por acaso.  
  - Fórmula:  

    ```Lift(A → B) = Confiança(A → B) / Suporte(B)```

  - Interpretação:  
    - **Lift > 1:** Associação positiva (forte).  
    - **Lift = 1:** Independência.  
    - **Lift < 1:** Associação negativa (a presença de A reduz chance de B).  

---

## 🛒 Algoritmos: Apriori e FP-Growth

- **Apriori:**  
  - Gera conjuntos de itens frequentes a partir do suporte mínimo.  
  - Constrói regras de associação com base nesses conjuntos.  
  - ✅ Simples e intuitivo, mas pode ser **computacionalmente caro** em grandes bases.  

- **FP-Growth (Frequent Pattern Growth):**  
  - Mais eficiente que o Apriori.  
  - Usa uma estrutura chamada **FP-tree** para compactar os dados.  
  - ✅ Escalável e rápido em grandes volumes de transações.  
