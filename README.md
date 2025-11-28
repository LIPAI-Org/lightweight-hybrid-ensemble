# Lightweight Hybrid Ensemble for Ameloblastoma and Ameloblastic Carcinoma Classification

This repository accompanies the SIBGRAPI 2025 paper "Lightweight Hybrid Ensemble for Ameloblastoma and Ameloblastic Carcinoma Classification" and provides the CSV files with the experimental results reported in the manuscript.  
The source code and processed dataset will be released here after the AM/AC dataset is publicly available.

- Paper: https://ieeexplore.ieee.org/document/11223358


---

## 1. Models and Ensemble

The work investigates a set of convolutional, Transformer, and hybrid CNN–Transformer models and proposes a Lightweight Hybrid Ensemble (LHE):

### 1.1. Individual Models
- **CNNs**
  - VGG16  
  - ResNet50  
  - DenseNet121  

- **Transformers**
  - ViT Base  
  - Swin Transformer Base  

- **Lightweight hybrid CNN–Transformer models**
  - LeViT conv-128 
  - EfficientViT-B0 
  - EdgeNeXt XX-Small

These lightweight hybrids are chosen to keep the computational cost low while still capturing both local (CNN) and global (attention) features, which is crucial when processing thousands of histology patches per WSI.

### 1.2. Lightweight Hybrid Ensemble (LHE)

The LHE combines the probabilistic outputs of three lightweight hybrid models:

- EdgeNeXt XX-Small  
- EfficientViT-B0  
- LeViT conv-128  

The ensemble uses a weighted average of class probabilities, where each model’s weight is proportional to its F1-score on the validation set. Intuitively:

- Models with higher validation F1-score contribute more to the final decision.
- Models with lower validation F1-score contribute less, improving robustness.

The CSV files in this repository summarize the performance of each individual model and of the LHE across all magnifications and datasets considered in the paper.

---

## 3. Datasets

### 3.1. AM/AC Multi-Magnification Dataset

The primary dataset was created for the classification of:

- Ameloblastoma (AM)
- Ameloblastic Carcinoma (AC)

The AM/AC dataset is currently **not yet public**. We plan to:

- Host the dataset on a public platform (e.g., Zenodo or similar).
- Provide direct download links and split definitions in this README.

### 3.2. OralEpitheliumDB (OEDB)

As an external validation dataset, we use OralEpitheliumDB (OEDB), originally proposed for dysplasia analysis in mouse tongue histology:

Public dataset link (segmentation & classification tasks):  
- OralEpitheliumDB – https://zenodo.org/records/17693395  

---


## 4. Result Files (CSV)

The CSV file in this repository provide the numerical values reported in the paper’s tables. 

---

## 5. Code and Dataset Availability

At the moment:

- **Result file (CSV)** are available in this repository.  
- **Source code** and **processed ROIs** of the AM/AC dataset will be released **once the dataset becomes publicly available**.


This README will be updated with detailed installation and usage instructions as soon as the code is made public.

---

## 6. Citation

If you use the results, methodology, or future code from this repository, please cite:

### BibTeX

```bibtex
@INPROCEEDINGS{11223358,
  author={de Oliveira, Domingos L. L. and de Castro, Hanna B. C. M. F. and Tosta, Thaína A. A. and Neves, Leandro A. and Oliveira, Pedro A. A. and de Faria, Paulo R. and do Nascimento, Marcelo Z.},
  booktitle={2025 38th SIBGRAPI Conference on Graphics, Patterns and Images (SIBGRAPI)}, 
  title={Lightweight Hybrid Ensemble for Ameloblastoma and Ameloblastic Carcinoma Classification}, 
  year={2025},
  volume={},
  number={},
  pages={1-6},
  keywords={Training;Solid modeling;Accuracy;Systematics;Computational modeling;Image edge detection;Performance gain;Robustness;Computational efficiency;Tumors},
  doi={10.1109/SIBGRAPI67909.2025.11223358}}
```

### Plain Text

```
D. L. L. de Oliveira et al., "Lightweight Hybrid Ensemble for Ameloblastoma and Ameloblastic Carcinoma Classification," 2025 38th SIBGRAPI Conference on Graphics, Patterns and Images (SIBGRAPI), Salvador, Brazil, 2025, pp. 1-6, doi: 10.1109/SIBGRAPI67909.2025.11223358.
```
