# Comparative Analysis of Algorithmic Strategies for the 0/1 Knapsack Problem  

This repository contains the implementation and analysis from my **Bachelor Thesis at Università della Svizzera italiana (USI), Faculty of Informatics**.  
The project investigates multiple algorithmic strategies for solving the **0/1 Knapsack Problem**, a classic NP-hard combinatorial optimization problem.  

---

## Thesis Abstract  

The work compares **exact, heuristic, and metaheuristic approaches** to the knapsack problem, evaluating them on efficiency, scalability, and solution quality.  

Implemented algorithms include:  
- **Dynamic Programming (DP)**  
- **Greedy Algorithm**  
- **Branch and Bound (BnB)**  
- **Martello–Toth Algorithm (MT)**  
- **Simulated Annealing (SA)**  
- **Ant Colony Optimization (ACO)**  
- **Integer Linear Programming (ILP, GLPK)**  

Benchmarks were generated (5,000 synthetic + 3,000 research benchmarks) and analyzed using Python, while the algorithms themselves were implemented in C for performance.  

Evaluation metrics:  
- Execution time (mean, median, quartiles, variance)  
- Memory usage  
- Deviation from optimal solution  
- Scalability trends across increasing problem sizes  

---


---

## Implementation Details  

- **Languages**  
  - **C** → for algorithm implementations (high performance)  
  - **Python** → for benchmark generation, statistical analysis, and visualization  

- **Benchmarks**  
  - Problem sizes: 10 → 10,000 items  
  - Capacities: 10 → 1000 (synthetic) + very large capacities in external benchmarks  
  - Uniform input format across all benchmarks  

- **Evaluation**  
  - Benchmarks run under timeout and memory constraints  
  - Special cases handled (`timeout → -1`, `full memory → -1`)  
  - Results stored in tabular format for comparison  

---

## Key Findings  

- **Dynamic Programming (DP)** and **ILP** → guarantee optimal solutions but require large memory and scale poorly.  
- **Greedy Algorithm** → extremely fast with <1% average error across many cases.  
- **Branch and Bound** and **Martello–Toth** → prune search spaces effectively, but performance varies with instance size.  
- **Simulated Annealing (SA)** and **ACO** → probabilistic search; SA achieved good accuracy while ACO underperformed in this implementation.  
- **Scalability** → Execution time strongly correlates with problem size (SA: 0.9897, ACO: 0.9799).  

---

## Installation  

### Requirements  
- **C compiler** (GCC or Clang)  
- **Python 3.8+** with `numpy`, `pandas`, `matplotlib`  
- **GLPK** (for ILP)  

### Build  

Compile the algorithms individually:  
```bash
gcc knapsack_greedy.c -o dp
gcc knapsack_dynamic.c -o greedy
...
```
Run an algorithm on a benchmark set:
./dp structured_benchmarks/benchmark_1/test.in

Run stats.py and stats_online.py to get the statistics for both benchmarks types

## References  

This thesis builds upon foundational and recent research in knapsack optimization:  

- Martello & Toth, *Knapsack Problems: Algorithms and Computer Implementations* (1990)  
- Della Croce & Salassa, *Exact approaches for 0–1 Knapsack* (2017)  
- Zhao et al., *ACO for Knapsack Problem* (2006)  
- Moradi et al., *Population-based Simulated Annealing* (2022)  

---

## Author  

**Valentino Belotcaci**  
Bachelor Thesis, Faculty of Informatics, USI  
Advisor: Prof. Antonio Carzaniga  




