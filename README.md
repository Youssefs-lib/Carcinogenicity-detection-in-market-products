<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=28&duration=4000&color=FF5733&center=true&vCenter=true&width=900&lines=Carcinogenicity+Prediction+Model;SMILES+%E2%9D%A4%EF%B8%8F+Deep+Learning;Chemical+Risk+Detection+in+Market+Products" />
</p>

---

## 📖 Project Overview  

This project builds a **deep learning model** to predict whether a compound has **carcinogenic potential**, based on its **SMILES chemical formula**.  

It leverages:  
- **RDKit** → Molecular descriptor calculation (`MolecularWeight`, `NumHeavyAtoms`)  
- **Keras Sequential Model** → Multi-layer Perceptron with Dropout & LeakyReLU  
- **Tox21-style dataset** → `class_tox21` as binary label  
- **Evaluation Metrics:** Accuracy, Precision, F1 Score  

✅ **Test Accuracy:** `82.4%`  
✅ **Precision:** `43.3%`  
✅ **F1 Score:** `58.7%`  

---

## 🛠️ Tech Stack  

<p>
  <img src="https://skillicons.dev/icons?i=python,tensorflow" />
  <img src="https://img.shields.io/badge/RDKit-003366?style=for-the-badge&logo=chemrxiv&logoColor=white" />
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
</p>

---

## 🔬 Methodology  

### 1️⃣ Data Preparation  
- Dataset: **SMILES formulas + compound labels**  
- Features:  
  - Encoded compound name (`LabelEncoder`)  
  - `MolecularWeight`, `NumHeavyAtoms` (from RDKit)  
- Target: `class_tox21` (toxic vs non-toxic)  

### 2️⃣ Model Architecture  
- Input layer → 32 neurons, LeakyReLU  
- Hidden layers → 128 → 64 → 32 → 16 neurons (LeakyReLU)  
- Dropout(0.5) for regularization  
- Output → 1 neuron, **Sigmoid** activation  

### 3️⃣ Training & Evaluation  
- Optimizer: `Adam(0.001)`  
- Loss: `Binary Crossentropy`  
- Metrics: Accuracy, Precision, F1  
- Best results:  
  - **Accuracy:** 82.4%  
  - **Precision:** 43.3%  
  - **F1:** 58.7%  

---

## 📊 Results  

<p align="center">
  <img src="https://img.shields.io/badge/Accuracy-82.4%25-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Precision-43.3%25-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/F1_Score-58.7%25-blue?style=for-the-badge" />
</p>

---

## 🚀 Application  

We applied the trained model on a **real dataset of food & vape additives**.  

**Predictions Example:**  

| Compound             | MolecularWeight | NumHeavyAtoms | Predicted Risk |
|----------------------|-----------------|---------------|----------------|
| Maltodextrin         | 342.29          | 23            | 0.016 (Safe)   |
| Disodium Inosinate   | 392.17          | 25            | 0.008 (Safe)   |
| Monosodium Glutamate | 169.11          | 11            | 0.166 (Susp.)  |
| Monoglyceride        | 120.10          | 8             | 0.285 (Susp.)  |
| Diglyceride          | 176.12          | 12            | 0.149 (Susp.)  |
| Malic Acid           | 134.08          | 9             | 0.241 (Susp.)  |

⚠️ **Interpretation:** While most compounds showed low predicted risk, certain additives (e.g., *Monoglyceride, Malic Acid*) were flagged as *suspicious*.  
<img width="781" height="462" alt="example of cancer causing product" src="https://github.com/user-attachments/assets/7fd966fd-7317-4ccb-963e-7564d8a72ae2" />


---
