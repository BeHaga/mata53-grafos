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