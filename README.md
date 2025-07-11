# Efficient Protein Structure Modeling and Analysis Using Graph Neural Networks

This project presents a lightweight and interpretable approach to protein structure analysis by leveraging Graph Neural Networks (GNNs). It offers a faster, resource-efficient alternative to models like AlphaFold2 for analyzing residue-level 3D structures.

---

## 🚀 Motivation

While AlphaFold2 has revolutionized protein structure prediction, it:
- Requires significant computational resources
- Functions as a black-box model with limited interpretability

This project addresses these limitations by:
- Modeling protein structures as graphs
- Using GNNs to learn spatial relationships between residues
- Providing explainable, fast, and scalable predictions

---

## 🎯 Objectives

- Extract residue-level graphs from AlphaFold-generated PDB files
- Train a GNN model to predict:
  - 3D coordinates
  - Confidence scores (pLDDT)
- Compare performance against AlphaFold2 using:
  - Execution time
  - Memory usage
  - Statistical correlations (Pearson, Spearman)
  - RMSD and pLDDT metrics

---

## 📚 Dataset

- **Source**: [UniProt](https://www.uniprot.org/)
- **Structure Labels**: AlphaFold2 PDB outputs
- **Format**: Protein sequences with annotated 3D structures and pLDDT confidence scores

---

## 🛠️ Tools & Libraries

- Python
- PyTorch Geometric
- Biopython
- NetworkX
- NumPy, Pandas
- Matplotlib
- Jupyter Notebook

---

## 🧪 Methodology

1. **Data Processing**
   - Parse PDB files to extract amino acid positions
   - Construct graphs:
     - **Nodes**: Residues (with features like pLDDT, coordinates)
     - **Edges**: Spatial proximity

2. **Model Architecture**
   - GCNConv → ReLU → Dropout → GCNConv → Linear layer
   - Output: 3D coordinates or pLDDT prediction per residue

3. **Training**
   - Loss based on coordinate regression or distance matrix difference
   - Evaluated on statistical alignment with AlphaFold2 outputs

---

## 📊 Results

- **Pearson Correlation (pLDDT)**: 0.98
- **Spearman Correlation (pLDDT)**: 0.99
- **Memory usage**: < 850MB (vs several GB for AlphaFold2)
- **Execution time**: < 10 seconds (vs hundreds for AlphaFold2)

### ✔️ GNN Advantages:
- Interpretable
- Fast inference
- Lightweight hardware requirements
- Easy integration with downstream bioinformatics workflows

---

## 📁 Folder Structure

