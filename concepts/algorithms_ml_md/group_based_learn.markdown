# Aprendizado Baseado em Grupo (Ensemble Learning)

## Definição

O **aprendizado baseado em grupo**, também chamado de **ensemble learning**, é uma técnica que combina vários classificadores (ou modelos) independentes para melhorar a performance em relação a um classificador único.  
A ideia principal é que diferentes modelos, quando reunidos, podem **corrigir os erros uns dos outros** e produzir previsões mais robustas e precisas.

As variações geralmente ocorrem por meio de:
- Alteração na **parametrização** dos classificadores (hiperparâmetros).  
- Escolha de **subconjuntos de atributos** diferentes para cada modelo.  
- Uso de **amostras diferentes dos dados de treinamento** (com ou sem reposição).  

---

## Exemplos de Ensemble

- **Random Forest:**  
  Ao invés de induzir uma única árvore de decisão, o Random Forest induz **várias árvores** a partir de amostras diferentes dos dados e subconjuntos de atributos.  
  Na previsão, cada árvore dá sua classificação, e o resultado final é obtido por **votação da maioria** (para classificação) ou **média** (para regressão).  

- **Bagging (Bootstrap Aggregating):**  
  Cria múltiplos modelos treinados em **subconjuntos aleatórios dos dados (com reposição)**. Depois, combina os resultados (votação ou média). É a base do Random Forest.  

- **Boosting:**  
  Treina modelos de forma sequencial, onde cada novo modelo dá mais peso aos erros cometidos pelos anteriores. Exemplos: **AdaBoost**, **Gradient Boosting**, **XGBoost**, **LightGBM**.  

- **Stacking:**  
  Combina modelos diferentes (ex.: árvores, regressão, redes neurais) e utiliza um **meta-modelo** para aprender a melhor forma de combinar as previsões.  

---

## Múltiplas Árvores

- Em algoritmos como **Random Forest**, as árvores são criadas a partir dos **mesmos dados originais**, mas com **amostras aleatórias** e subconjuntos de atributos distintos.  
- Isso garante diversidade entre as árvores, evitando que todas aprendam os mesmos padrões.  

---

## Previsão

O processo de previsão em ensembles geralmente funciona assim:

1. Cada modelo no conjunto gera uma previsão para a nova instância.  
2. Os resultados individuais são **combinados**:  
   - **Classificação:** votação da maioria.  
   - **Regressão:** cálculo da média (ou mediana) das previsões.  
3. O resultado final tende a ser **mais estável e preciso** do que o de um único modelo.  

---
