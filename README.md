# 🧪 SMILES, Morgan Fingerprints, and Tanimoto Similarity

This project demonstrates how to **compute molecular fingerprints** using **RDKit** and measure **molecular similarity** using the **Tanimoto coefficient**.

---

## 📌 Key Concepts

### **1️⃣ SMILES (Simplified Molecular Input Line Entry System)**
**SMILES** is a string notation that represents chemical structures in a **compact, machine-readable format**.

✅ **Examples of SMILES Representations**:
| Molecule  | SMILES |
|-----------|--------|
| Ethanol   | `CCO`  |
| Propanol  | `CCCO` |
| Butanol   | `CCCCO` |

SMILES can be **converted into molecular structures** in RDKit, enabling **fingerprint generation and similarity calculations**.

---

### **2️⃣ Morgan Fingerprints (ECFP)**
**Morgan Fingerprints**, also called **Extended Connectivity Fingerprints (ECFP)**, encode molecular substructures as **binary vectors**.

✅ **Key Parameters**:
- **Radius**: Defines the **neighborhood** around each atom.
  - `radius=2` → ECFP4 (up to 2 bonds away).
  - `radius=4` → ECFP6 (up to 4 bonds away).
- **Fingerprint Length**: Typically **1024 or 2048 bits**.

✅ **How They Work**:
Morgan fingerprints identify **unique substructures** within a molecule and **convert them into bit vectors** for similarity analysis.

---

### **3️⃣ Tanimoto Similarity**
**Tanimoto Similarity** (also called the **Jaccard index**) measures how similar two molecules are **based on their fingerprints**.

✅ **Formula**:
\[
Tanimoto\ Similarity = \frac{A \cap B}{A \cup B}
\]
Where:
- **A** and **B** are binary fingerprints.
- **1.0** → Molecules are **identical**.
- **0.0** → Molecules **share no common substructure**.

✅ **Example Use Case**:
- Comparing drug molecules to find **structurally similar compounds**.
- Screening databases for **potential drug candidates**.

---

## 🚀 Technologies Used
- **Python**
- **RDKit** (Molecular processing)
- **NumPy** (Array operations)
- **Pandas** (Data handling)

---

## 📌 Getting Started

### 1️⃣ **Clone the Repository**
```bash
git clone https://github.com/yourusername/smiles-morgan-fingerprints.git
cd smiles-morgan-fingerprints


2️⃣ Install Dependencies
pip install rdkit pandas numpy
3️⃣ Run the Python Script
python compute_similarity.py
🧪 Example Code
from rdkit import Chem
from rdkit.Chem import AllChem, DataStructs

# Example molecules
smiles_list = ["CCO", "CCCO", "CCCCO"]  # Ethanol, Propanol, Butanol

# Convert SMILES to RDKit molecules
mols = [Chem.MolFromSmiles(smiles) for smiles in smiles_list]

# Generate Morgan Fingerprints (ECFP4)
fingerprints = [AllChem.GetMorganFingerprintAsBitVect(mol, radius=2, nBits=1024) for mol in mols]

# Compute Tanimoto Similarity
similarity = DataStructs.TanimotoSimilarity(fingerprints[0], fingerprints[1])
print(f"Tanimoto Similarity between Ethanol & Propanol: {similarity:.4f}")
📊 Example Output
Tanimoto Similarity between Ethanol & Propanol: 0.6667
Tanimoto Similarity between Ethanol & Butanol: 0.5000
Tanimoto Similarity between Propanol & Butanol: 0.7500
✅ Higher values mean molecules are more similar.
✅ Lower values mean molecules are structurally different.






