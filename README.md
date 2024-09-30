# SMILES-Morgan-Fingerprints-and-Tanimoto-Similarity
Demonstrates how to compute molecular fingerprints using the RDKit library and measure the similarity between molecules using the Tanimoto coefficient. 
Key Concepts
1. SMILES (Simplified Molecular Input Line Entry System)
SMILES is a string notation that encodes the structure of molecules using a series of characters. It is a compact and machine-readable way to represent chemical structures.

Examples:

Ethanol (C2H5OH): CCO
Propanol (C3H7OH): CCCO
Butanol (C4H9OH): CCCCO
SMILES strings can be converted into molecular structures that RDKit can interpret, allowing for further analysis like fingerprint generation and similarity calculations.

2. Morgan Fingerprints (ECFP)
Morgan Fingerprints, also called Extended Connectivity Fingerprints (ECFP), are a type of molecular fingerprint used to represent the topological structure of a molecule. These fingerprints encode substructures (like atoms and their neighboring bonds) as fixed-length binary vectors.

Key Parameters:
Radius: Defines the neighborhood around each atom considered when generating the fingerprint.
Radius 2: Corresponds to ECFP4 (up to 2 bonds away from each atom).
Radius 4: Corresponds to ECFP6 (up to 4 bonds away from each atom).
Length: The length of the fingerprint, typically set to 1024 or 2048 bits.

3. Tanimoto Similarity
The Tanimoto Similarity (also known as the Jaccard index) is a widely used measure for comparing molecular fingerprints. It is a ratio of the intersection to the union of the fingerprints.

Similarity = 1: The molecules are identical.
Similarity = 0: The molecules share no common substructure.
Formula:

Tanimoto Similarity
=
𝐴
∩
𝐵
𝐴
∪
𝐵
Tanimoto Similarity= 
A∪B
A∩B
​
 
Where:

𝐴
A and 
𝐵
B are binary fingerprints of two molecules.
