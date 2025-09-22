# Árvores de Decisão

## Conceito

As **árvores de decisão** são modelos de aprendizado supervisionado usados tanto para **classificação** quanto para **regressão**.  
Elas funcionam de forma semelhante a um fluxograma, onde as decisões são tomadas com base em perguntas sucessivas sobre os atributos dos dados.

Uma árvore de decisão é composta por:

- **Nó raiz:** Ponto inicial da árvore, onde ocorre a primeira divisão.  
- **Nós internos (partições):** Representam testes/condições em atributos, que dividem os dados.  
- **Nós folhas:** Representam os resultados finais da classificação ou regressão (as classes ou valores previstos).  

---

## Complexidade

A complexidade de uma árvore de decisão está relacionada a dois fatores principais:

- **Profundidade:** Número de níveis entre a raiz e as folhas. Quanto maior, mais complexa e específica a árvore se torna.  
- **Largura:** Número de nós presentes em cada nível da árvore.  

Árvores muito profundas podem sofrer de **overfitting** (memorizar os dados de treino) e perder capacidade de generalização.

---

## Atributos

As árvores podem lidar com diferentes tipos de atributos:

- **Discretos:** São atributos categóricos (ex.: "Cor" = {vermelho, azul, verde}).  
- **Contínuos:** São atributos numéricos (ex.: "Idade", "Salário"). Para usá-los, a árvore cria **limiares** (ex.: "Idade > 30?").  

---

## Processo de Classificação

1. Inicia no **nó raiz**.  
2. Em cada nó interno, é feita uma **pergunta/teste** sobre um atributo.  
3. De acordo com a resposta, segue-se para a ramificação correspondente.  
4. O processo continua até chegar em um **nó folha**, que fornece a **classe ou valor previsto**.  

---

## Indução da Árvore

A **indução da árvore de decisão** é o processo de construir a árvore a partir dos dados.  
O algoritmo mais usado para isso é o **ID3/C4.5** (e suas variações como CART).  
O objetivo é escolher, em cada divisão, o atributo que **melhor separa os dados**.

---

## Divisão (Split)

O processo de divisão consiste em **selecionar o atributo que mais reduz a incerteza** dos dados em cada passo.  
As métricas mais usadas são:

- **Entropia e Ganho de Informação (ID3, C4.5):** Medem a pureza dos grupos formados.  
- **Índice Gini (CART):** Mede a probabilidade de classificação incorreta se os elementos fossem distribuídos aleatoriamente.  
- **Redução de Variância (Regressão):** Para problemas de regressão, mede como a divisão reduz a variabilidade dos valores.

---

## Condição de Parada

A árvore não cresce indefinidamente. O crescimento para quando:

- Todos os dados em um nó pertencem à mesma classe.  
- Não há mais atributos disponíveis para dividir.  
- O número mínimo de instâncias em um nó é atingido.  
- A profundidade máxima definida é alcançada.  

---

## Poda (Pruning)

A **poda** é uma técnica para simplificar a árvore e evitar **overfitting**.  
Ela remove nós ou ramos desnecessários que não contribuem significativamente para o desempenho.

- **Poda pré-pruning:** O crescimento da árvore é limitado já durante a construção (ex.: limitar profundidade).  
- **Poda pós-pruning:** A árvore é construída até o fim e depois simplificada removendo divisões pouco relevantes.  

Isso melhora a **generalização** do modelo.

---
