# Exploring Natural Products Through Biological Representations

A computational exploration of natural products and biosynthetic gene clusters (BGCs) using sequence analysis, machine learning, and learned representations.

The project investigates whether information encoded at different biological levels — **proteins, biosynthetic gene clusters, and natural products** — can be represented computationally and used to identify meaningful patterns in biosynthetic systems.

> **Project status:** Exploratory research / ongoing development

---

## Overview

Natural products are produced through complex biosynthetic systems in which multiple proteins and genes work together to generate chemically diverse compounds.

This creates a hierarchical relationship:

**Protein → Biosynthetic Gene Cluster → Natural Product**

Individual proteins contribute to the function of a BGC, while one or more BGCs can contribute to the biosynthesis of a natural product. Understanding these relationships computationally could help identify patterns associated with biosynthetic pathways and support genome-guided natural-product discovery.

This repository contains exploratory analyses of these relationships using sequence-derived representations, dimensionality reduction, and machine-learning approaches.

---

## Research Questions

The project explores several related questions:

1. **Can protein sequence representations capture meaningful patterns associated with biosynthetic function?**

2. **Can representations of individual proteins be aggregated to describe biosynthetic gene clusters?**

3. **Do BGC representations organize according to known biosynthetic classes or other biological properties?**

4. **Can relationships between BGCs and their associated natural products be captured computationally?**

5. **Can independently learned representations at the protein, BGC, and natural-product levels eventually be aligned into a shared representation space?**

The longer-term objective is to investigate whether these representations can support **cross-modal inference and discovery of previously uncharacterized biosynthetic systems**.

---

## Data

The project makes use of information associated with characterized biosynthetic gene clusters and natural products, including:

* Protein sequences
* DNA sequences
* Biosynthetic gene cluster identifiers
* Biosynthetic classes
* Natural-product information
* Sequence-derived representations

Characterized BGC information is linked to **MIBiG**, which provides standardized information about experimentally characterized biosynthetic gene clusters.

---

## Analysis Strategy

The project is organized around multiple analytical layers.

### Layer 1 — Sequence-based exploration

The initial analyses explore sequence-derived representations of proteins associated with biosynthetic gene clusters.

The goal is to determine whether proteins associated with related biosynthetic systems exhibit structure in their representation space and whether this structure can be associated with known biosynthetic classes.

---

### Layer 2 — Protein representations → BGC representations

The second layer moves from individual proteins toward representations of complete biosynthetic gene clusters.

Protein sequences are represented using learned protein embeddings, including representations generated with transformer-based protein language models such as **ESM-2**.

Protein-level representations are then associated with their corresponding BGCs to construct BGC-level representations.

These representations are explored using dimensionality reduction and visualization techniques such as **UMAP**.

The resulting embedding space can be examined in relation to known MIBiG biosynthetic classes.

---

### Layer 3 — BGCs → Natural Products

The third layer investigates relationships between biosynthetic gene clusters and the natural products associated with them.

The analysis explores whether BGC representations exhibit structure related to:

* Biosynthetic class
* Natural-product identity
* Compound-level relationships
* Other biological or chemical annotations

Interactive visualizations are used to explore these relationships in representation space.

---

## Representation Hierarchy

A central idea behind the project is that biosynthetic systems can be viewed at multiple levels of representation:

```text
                 Natural Products
                       ▲
                       │
                 Biosynthetic
                  Gene Clusters
                       ▲
                       │
                    Proteins
```

Each level contains information that is related to, but not necessarily equivalent to, the level below it.

A key research direction is therefore to distinguish between:

* **Similarity** — whether two biological entities have similar representations
* **Composition** — whether lower-level entities can be combined to represent a higher-level biological system

This distinction becomes particularly important when moving from protein embeddings to BGC representations and ultimately to natural-product representations.

---

## Methods and Technologies

The project currently uses a combination of:

* **Python**
* **PyTorch**
* **Hugging Face Transformers**
* **ESM-2 protein language models**
* **scikit-learn**
* **UMAP**
* **pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Plotly**
* **Biopython**
* **pyMIBiG**

Methods explored include:

* Protein sequence representation
* Transformer-based protein embeddings
* Representation aggregation
* Principal component analysis
* UMAP
* Statistical exploration
* Machine-learning classification
* Visualization of biological representation spaces

---

## Repository Structure

```text
explore-natural-products/
│
├── src/
│   ├── processing.ipynb
│   ├── dna.ipynb
│   ├── compounds.ipynb
│   ├── analysis_layer_one.ipynb
│   ├── analysis_layer_two.ipynb
│   └── analysis_layer_three.ipynb
│
├── LICENSE
└── README.md
```

### `processing.ipynb`

Data preparation and preprocessing.

### `dna.ipynb`

Exploration of DNA-level information associated with biosynthetic systems.

### `compounds.ipynb`

Exploration of natural-product and compound-level information.

### `analysis_layer_one.ipynb`

Initial representation and machine-learning analyses.

### `analysis_layer_two.ipynb`

Protein-language-model representations and BGC-level embedding analysis.

### `analysis_layer_three.ipynb`

Exploration of relationships between BGC representations and natural products.

---

## From Classification to Representation Learning

The project originated from an interest in using machine learning to classify and discover biosynthetic gene clusters.

The original implementation, **ML-Miner**, explored whether protein sequences associated with characterized BGCs could be used to learn patterns associated with different biosynthetic classes and then applied to previously uncharacterized clusters.

**Original project:** [ML-Miner](https://github.com/poloarol/biosynthetic-cluster-ml)

This work led to a broader question:

> **Rather than using representations only to classify BGCs, can they be used to describe the biological and chemical relationships between proteins, BGCs, and natural products?**

This shift moves the project from a conventional classification problem toward **representation learning and biological discovery**.

---

## Future Directions

Several directions could extend this work.

### Multimodal representation learning

Develop aligned representations for:

```text
Protein sequences
       ↓
BGC representations
       ↓
Natural-product representations
```

and investigate whether these representations can be mapped into a shared latent space.

### Cross-modal prediction

Explore whether information at one level can predict properties at another:

* Protein → BGC
* BGC → Natural product
* Natural product → candidate BGC
* BGC → biosynthetic class

### Compositional representations

Investigate whether BGC representations can capture the composition of multiple proteins and biosynthetic components rather than treating a BGC as a single undifferentiated sequence.

### Novel BGC discovery

Apply learned representations to previously uncharacterized BGCs and investigate whether their position in representation space can provide clues about:

* Biosynthetic class
* Functional similarity
* Potential natural-product relationships
* Novel biosynthetic architectures

### Integration with genome-mining tools

A future implementation could combine learned representations with genome-mining systems such as **antiSMASH** to prioritize candidate BGCs for further investigation.

---

## Why This Project?

Natural-product discovery sits at the intersection of:

**Genomics × Protein Biology × Machine Learning × Chemistry**

The computational challenge is not simply to classify sequences. It is to understand how information is organized across biological levels and whether computational representations can capture relationships that are useful for discovery.

This project is an exploration of that problem.

---

## Status

This repository represents an ongoing research and development effort.

The current analyses are primarily exploratory and are intended to investigate the structure and usefulness of learned representations rather than present a finalized predictive system.

---

## License

This project is released under the MIT License.
