# K-Means

## Conceito

O **K-Means** é um algoritmo de **clustering** (agrupamento) do tipo **não supervisionado**, usado para dividir um conjunto de dados em **k grupos (clusters)**.  
A ideia é simples: pontos semelhantes ficam no mesmo grupo, enquanto pontos diferentes são separados em grupos distintos.

- **k:** número de clusters que queremos formar (definido pelo usuário).  
- **Centróides:** cada cluster é representado por um ponto central (média dos pontos do grupo).  
- Cada instância do conjunto de dados é atribuída ao cluster cujo centróide está mais próximo.  

---

## Funcionamento do Algoritmo

1. **Escolher k:** definir o número de clusters desejados.  
2. **Inicializar centróides:** escolher aleatoriamente k pontos para servir como centróides iniciais.  
3. **Atribuição:** cada ponto de dado é associado ao centróide mais próximo (formando clusters).  
4. **Atualização:** os centróides de cada cluster são recalculados como a **média dos pontos** daquele cluster.  
5. **Repetição:** os passos 3 e 4 se repetem até que:  
   - os centróides parem de mudar significativamente, ou  
   - um número máximo de iterações seja atingido.  

---

## Exemplo Intuitivo

Imagine que você quer agrupar clientes de um mercado em **3 perfis de consumo**: econômico, regular e premium.  
O K-Means vai agrupar os clientes de acordo com o **padrão de compras**, e cada grupo será representado por um **centróide médio** daquele perfil.  

---

## Vantagens

- Simples de entender e implementar.  
- Rápido para grandes volumes de dados.  
- Funciona bem quando os clusters têm formato esférico e tamanhos semelhantes.  

---

## Limitações

- É necessário **definir k** (número de clusters) antes de rodar o algoritmo.  
- Sensível a **valores iniciais dos centróides** (pode convergir para soluções ruins).  
- Supõe que todos os clusters tenham formato circular/esférico.  
- Sensível a **outliers**, que podem distorcer os centróides.  

---

## Como escolher o valor de k?

Uma técnica comum é o **Método do Cotovelo (Elbow Method):**

- Calcula-se o erro (SSE – soma dos quadrados das distâncias) para diferentes valores de k.  
- O ponto onde o gráfico "dobra" (como um cotovelo) é considerado o valor ideal de k.  

---
