# MATA53 - Teoria dos Grafos (2026.1)

## Análise Estrutural e Algorítmica do Grafo G27

Discente: Bruno Henrique dos Santos Luz Santos

Matrícula: 222115773

Universidade Federal da Bahia (UFBA)

---

## Determinação do Grafo

Matrícula:

222115773

Soma dos dígitos:

2 + 2 + 2 + 1 + 1 + 5 + 7 + 7 + 3 = 30

Últimos dois dígitos:

73 + 1 = 74

Aplicando a fórmula:

(30 × 74) mod 129

2220 mod 129 = 27

Portanto, o grafo atribuído foi:

G27

---

## Dataset

O conjunto de dados utilizado corresponde à rede social Orkut disponibilizada pelo Stanford Network Analysis Project (SNAP):

https://snap.stanford.edu/data/com-Orkut.html

Arquivos utilizados:

* com-orkut.ungraph.txt
* com-orkut.top5000.cmty.txt

Os arquivos brutos não estão versionados neste repositório devido ao seu tamanho superior aos limites suportados pelo GitHub.

---

## Tratamento Realizado

Devido ao tamanho do grafo original (3.702.441 vértices e 117.185.083 arestas), optou-se por realizar uma redução baseada nas comunidades disponibilizadas pelo SNAP.

Foi selecionada a maior comunidade presente no arquivo `com-orkut.top5000.cmty.txt`, contendo 4785 vértices.

A partir dela foi construído um subgrafo induzido contendo:

* 4785 vértices
* 119891 arestas

Esse subgrafo foi utilizado em todas as análises subsequentes.

---

## Resultados da Análise Estrutural

Subgrafo analisado:

- Vértices: 4785
- Arestas: 119891
- Grau mínimo: 1
- Grau máximo: 425
- Grau médio: 50.11
- Densidade: 0.01047
- Componentes conexas: 1
- Coeficiente médio de clusterização: 0.313
- Número de triângulos: 1.053.848
- Diâmetro: 12
- Raio: 6
- Comprimento médio dos caminhos: 3.284

Figuras geradas:

- figures/degree_distribution.png
- figures/degree_distribution_loglog.png
- figures/subgraph_visualization.png

---

## Algoritmos Implementados

Os seguintes algoritmos foram implementados e avaliados experimentalmente:

- BFS (Busca em Largura)
- DFS (Busca em Profundidade)
- Verificação de Eulerianidade
- Dijkstra
- Bellman-Ford
- Tarjan (Pontos de Articulação)
- Prim
- Kruskal

Para cada algoritmo foram medidos:

- Tempo médio
- Desvio padrão
- Intervalo de confiança de 95%

O algoritmo Floyd-Warshall não foi executado devido à complexidade O(n³), considerada inviável para o subgrafo analisado.

---

## Redes Complexas

Foram investigadas duas propriedades clássicas de redes complexas:

### Small-World

Resultados obtidos:

- Clusterização real: 0.313
- Caminho médio real: 3.284
- Clusterização aleatória: 0.0105
- Caminho médio aleatório: 2.575
- Sigma: 23.42

Como σ > 1, o grafo apresenta forte evidência da propriedade Small-World.

### Lei de Potência

Resultados obtidos:

- Expoente α = 1.313

A distribuição de graus apresenta comportamento altamente assimétrico, indicando a existência de hubs e concentração de conexões em poucos vértices.

---

## Robustez Estrutural

Foram realizados dois experimentos de robustez:

### Remoção Aleatória de 5%

Remoção aleatória de 5% dos vértices do subgrafo.

Resultado:

- Maior componente original: 4785 vértices
- Maior componente após remoção: 4527 vértices

### Remoção dos 5% Vértices Mais Centrais

Remoção dos vértices com maior centralidade de grau.

Resultado:

- Maior componente original: 4785 vértices
- Maior componente após remoção: 4505 vértices

Observou-se que a rede permaneceu majoritariamente conectada em ambos os cenários, indicando elevada robustez estrutural da comunidade analisada.

---

### Notebooks concluídos

* [x] 01_dataset_exploration.ipynb
* [x] 02_graph_extraction.ipynb
* [x] 03_structural_analysis.ipynb
* [x] 04_algorithms.ipynb
* [x] 05_smallworld_powerlaw.ipynb
* [x] 06_robustness.ipynb

---

## Estrutura do Projeto

```text
projetos-grafos/

├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_dataset_exploration.ipynb
│   ├── 02_graph_extraction.ipynb
│   ├── 03_structural_analysis.ipynb
│   ├── 04_algorithms.ipynb
│   ├── 05_smallworld_powerlaw.ipynb
│   └── 06_robustness.ipynb
│
├── figures/
├── results/
├── relatorio.tex
└── README.md
```

---

## Ambiente

* Python 3.x
* Jupyter Notebook
* VSCode
* NetworkX
* NumPy
* Pandas
* Matplotlib

---

## Instalação

```bash
pip install networkx pandas numpy matplotlib scipy jupyter
```

---

## Execução

### 1. Exploração do Dataset

```bash
01_dataset_exploration.ipynb
```

Responsável por analisar as comunidades disponibilizadas pelo SNAP.

### 2. Extração do Subgrafo

```bash
02_graph_extraction.ipynb
```

Responsável por extrair a maior comunidade e gerar o subgrafo utilizado nas análises.

### 3. Análise Estrutural

```bash
03_structural_analysis.ipynb
```

Cálculo das métricas estruturais obrigatórias.

### 4. Algoritmos

```bash
04_algorithms.ipynb
```

Implementação dos algoritmos estudados na disciplina.

### 5. Small-World e Lei de Potência

```bash
05_smallworld_powerlaw.ipynb
```

Avaliação das propriedades de redes complexas.

### 6. Robustez

```bash
06_robustness.ipynb
```

Análise da robustez estrutural do grafo.