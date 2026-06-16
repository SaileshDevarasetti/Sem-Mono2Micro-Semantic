# Sem-Mono2Micro 
Semantic-Aware Monolith to Microservice Decomposition using Static Analysis and Transformer-Based Code Embeddings

## 📌 Problem Statement
Modern enterprise applications are predominantly developed as monolithic systems, which become difficult to scale, maintain, and evolve over time. Migrating such systems to microservice architectures is challenging due to tightly coupled components, unclear service boundaries, and lack of architectural documentation. Existing decomposition techniques either rely on runtime execution traces or ignore semantic relationships between code entities.

Sem-Mono2Micro addresses this problem by proposing a static, semantic-aware, and explainable framework for automated microservice decomposition.

---

## 🧠 Machine Learning Approach
The proposed framework combines:

- **Static Structural Analysis**
  - Abstract Syntax Tree (AST) parsing using `javalang`
  - Extraction of inheritance, implementation, field, and method dependencies
  - Weighted dependency graph construction

- **Semantic Code Understanding**
  - Transformer-based code embeddings using CodeBERT
  - Cosine similarity and KNN-based semantic graph augmentation

- **Graph Optimization & Clustering**
  - Hybrid weighted graph (structural + semantic)
  - God Class pruning using centrality analysis
  - Leiden community detection for microservice identification

- **Explainability**
  - CodeT5-based service labeling
  - Interpretable service boundaries

---

## 📂 Dataset Description
### Primary Dataset: JPetStore
- Open-source Java monolithic e-commerce application
- ~24 core Java classes
- Commonly used benchmark in monolith-to-microservice research

### Secondary Dataset: DayTrader
- Large-scale enterprise Java trading application
- Used for scalability validation

---

## 🧪 Experiments
- Structural-only vs Semantic-only vs Hybrid decomposition
- Resolution sweep for Leiden clustering
- Ablation studies:
  - Without semantic edges
  - Without God Class pruning
  - Uniform vs weighted dependencies

---

## 📊 Results
- Achieved modularity scores between **0.41 – 0.48**
- Hybrid approach outperformed structural-only baselines
- Improved cohesion and reduced inter-service coupling
- Generated meaningful, explainable microservice groupings

---

## 🖼 Visuals
- Dependency graphs before and after pruning
- Microservice cluster visualization
- System architecture diagram

(All figures available in `results/figures/`)

---

## 🛠 Tech Stack
- **Language:** Python 3.10+
- **Static Analysis:** javalang
- **Graph Processing:** NetworkX, igraph
- **Machine Learning:** PyTorch, HuggingFace Transformers
- **Clustering:** Leiden Algorithm
- **Visualization:** Matplotlib, Seaborn

---

## 📌 Future Work
- Graph Neural Networks (GCN / GraphSAGE)
- Larger-scale evaluation on industrial monoliths
- Automated refactoring recommendations

---

## 📄 License
MIT License
