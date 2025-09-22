# Engenharia de Atributos (Feature Engineering)

A **Engenharia de Atributos** é o processo de **preparar, transformar e criar características (features)** a partir dos dados brutos, de forma a melhorar o desempenho de modelos de aprendizado de máquina.  

É uma das etapas mais importantes no fluxo de trabalho de **Machine Learning**, pois dados bem tratados e bem representados geralmente têm mais impacto no resultado final do que apenas escolher um algoritmo sofisticado.

---

## 1. Pré-processamento

- **Tratamento de valores faltantes:**  
  - Remover registros incompletos.  
  - Preencher valores ausentes (média, mediana, moda ou técnicas avançadas como KNN imputer).  

- **Tratamento de outliers:**  
  - Detectar valores anômalos (boxplot, desvio padrão, z-score).  
  - Corrigir, remover ou ajustar (dependendo do problema).  

- **Transformações básicas:**  
  - Conversão de tipos (string → numérico).  
  - Padronização de formatos (datas, unidades, escalas).  

---

## 2. Codificação de Categorias

Transformar variáveis categóricas em representações numéricas para que os algoritmos consigam utilizá-las.

- **Label Encoding:** atribui um número inteiro para cada categoria.  
- **One-Hot Encoding:** cria colunas binárias (0/1) para cada categoria.  
- **Target Encoding:** substitui a categoria pela média da variável-alvo.  
- **Embedding:** representações vetoriais usadas em deep learning.  

---

## 3. Dimensionamento de Características

Os atributos podem estar em **escalas diferentes** (ex.: idade em anos, salário em milhares).  
Isso pode afetar modelos baseados em distância ou gradiente.  

- **Normalização (Min-Max):** transforma valores para o intervalo [0, 1].  
- **Padronização (Z-Score):** transforma para média = 0 e desvio padrão = 1.  
- **Robust Scaling:** menos sensível a outliers (usa mediana e IQR).  

---

## 4. Geração e Extração de Características

Criar ou derivar novas variáveis a partir das já existentes.

- **Binning:** transformar variáveis numéricas contínuas em categorias (ex.: faixa etária: jovem, adulto, idoso).  
- **Decomposição de datas:** extrair partes de uma data (dia, mês, ano, dia da semana, feriado).  
- **Extração de texto:** contagem de palavras, TF-IDF, embeddings.  
- **Redução de dimensionalidade (PCA):** transforma variáveis correlacionadas em componentes principais.  
- **Transformações matemáticas:** log, raiz quadrada, exponencial para ajustar distribuições.  

---

## 5. Seleção de Características Importantes

Selecionar apenas os atributos mais relevantes melhora a **eficiência** e reduz **overfitting**.

- **Métodos estatísticos:** correlação, ANOVA, qui-quadrado.  
- **Métodos baseados em modelos:** feature importance (árvores, Random Forest, XGBoost).  
- **Métodos de seleção sequencial:** forward selection, backward elimination.  
- **Regularização:** Lasso (L1) elimina coeficientes pouco relevantes.  

---

## 6. Benefícios da Engenharia de Atributos

- Melhora o desempenho dos modelos.  
- Reduz complexidade e tempo de treinamento.  
- Ajuda a evitar overfitting.  
- Permite interpretar melhor os resultados.  

---
