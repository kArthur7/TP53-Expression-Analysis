TP53 Expression Analysis (Tumor vs Normal)
Overview
This project analyzes the expression of the TP53 gene in tumor and normal breast tissue samples using a synthetic TCGA‑style dataset.
The goal is to demonstrate a clean, reproducible workflow for basic gene expression analysis, including data loading, group separation, visualization, statistical testing, and interpretation.
The dataset is synthetic to avoid RAM limitations from the original BRCA dataset while preserving realistic gene × sample structure.

Aim
To compare TP53 expression between tumor and normal breast tissue samples and determine whether a statistically significant difference exists.

Methods
Data:
- Synthetic BRCA‑like gene expression matrix
- Genes × samples with tumor and normal labels
- TP53 selected as the gene of interest
Workflow:
- Loaded the expression matrix and sample labels
- Verified tumor and normal sample counts
- Extracted TP53 expression values
- Visualized distributions (boxplot, violin plot)
- Performed a two‑sample statistical test (t‑test or Wilcoxon)
- Interpreted the p‑value relative to α = 0.05

Hypotheses
Null hypothesis (H₀):
TP53 expression is the same in tumor and normal samples.
Alternative hypothesis (H₁):
TP53 expression differs between tumor and normal samples.

Results & Interpretation
The statistical comparison of TP53 expression between tumor and normal samples in this synthetic dataset produced a p‑value(0.2602) greater than the significance threshold (α = 0.05). This indicates that the observed difference in TP53 expression is not statistically significant, meaning the variation between groups is consistent with random fluctuation rather than a true underlying difference.
This outcome is biologically reasonable. In breast cancer, TP53 is best known for its high mutation frequency, while its mRNA expression levels do not consistently differ between tumor and normal tissue across all subtypes. Because of this, a non‑significant expression difference is entirely plausible and does not contradict established TP53 biology.

Conclusion
- The p‑value exceeded α, so we fail to reject the null hypothesis.
- Within this synthetic dataset, TP53 expression does not show a statistically significant difference between tumor and normal samples.
- This result aligns with real‑world understanding that TP53’s role in cancer is driven more by mutation status than by consistent changes in expression level.
- The analysis successfully demonstrates a correct, reproducible workflow for tumor‑vs‑normal gene expression comparison.

Challenges
Challenge 1: Dataset size and RAM limits
The original BRCA dataset was too large, causing memory crashes.
Solution:
A smaller synthetic dataset was generated with a similar structure to ensure reproducibility on typical hardware.

Challenge 2: Maintaining realistic behavior in synthetic data
Synthetic data can be too simple.
Solution:
Expression values were generated using distributions that mimic RNA-seq-like behavior, ensuring that the analysis steps behave realistically.

 Challenge 3: Data type inconsistencies
The TP53 expression values were stored as object (string) rather than numeric, which prevented plotting and statistical testing.
Solution: 
This required explicit conversion to numeric types to ensure correct visualization and analysis.

Data Management and Reproducibility Note

The raw synthetic data folder (brca_synthetic_expression) was removed from this repository to keep the project lightweight and stay within GitHub file size limits.
