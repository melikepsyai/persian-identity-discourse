# persian-identity-discourse
Code and data for "Us vs. Them" in Persian Twitter
========================================
SBP-BRiMS 2026 Submission Package
========================================

Title: Us vs. Them: Identity Dimensions and In-group/Out-group Orientation 
       in Persian Twitter Discourse

Author: Melikeh Mirzaei
Email: mirzaeimelike@gmail.com
Affiliation: Islamic Azad University, Ashtian Branch, Iran

========================================
FILES INCLUDED
========================================

1. mirzaei_sbp2026.pdf
   - Main manuscript formatted for Springer LNCS
   - 10 pages including all tables and references

2. mirzaei_sbp2026.tex
   - LaTeX source file of the manuscript
   - Can be compiled with pdflatex + bibtex

3. labeled_data.xlsx
   - Final annotated dataset (621 tweets)
   - Columns: Identity_Dimension, Group_Orientation, text
   - Identity codes: P, N, R, G, I, O, S_C, M, U
   - Orientation codes: IN, NE, OUT

4. README.txt
   - This file

========================================
REQUIREMENTS
========================================

To compile the LaTeX source or run the analysis:

LaTeX compilation:
- TeX Live 2020 or later
- Packages: llncs class, amsmath, graphicx, booktabs, hyperref

Python environment (for data analysis):
- Python 3.9 or higher
- pandas >= 2.0.0
- scipy >= 1.10.0
- numpy >= 1.22.0
- openpyxl >= 3.0.0

Install Python dependencies:
pip install pandas scipy numpy openpyxl jupyter

========================================
REPRODUCING THE RESULTS
========================================

1. Open the dataset (labeled_data.xlsx) in any spreadsheet software
   or load it with pandas: df = pd.read_excel("labeled_data.xlsx")

2. The statistical analysis reported in the paper was performed using:
   - Chi-square test of independence
   - Fisher's exact test (pairwise comparisons)

3. To verify the results, run the following Python code:

import pandas as pd
from scipy.stats import chi2_contingency, fisher_exact

df = pd.read_excel("labeled_data.xlsx")
contingency = pd.crosstab(df['Identity_Dimension'], df['Group_Orientation'])
chi2, p, dof, expected = chi2_contingency(contingency)
print(f"Chi-square: {chi2}, p: {p}")

========================================
NOTES
========================================

- The raw 748k tweet dataset is not included due to its large size
- The annotated dataset (labeled_data.xlsx) contains only the 621 tweets
  used for statistical analysis
- All tweets are anonymized; no personally identifiable information
  is included

========================================
CONTACT
========================================

For any questions regarding this submission or the accompanying data:
Melikeh Mirzaei - mirzaeimelike@gmail.com

========================================
DATE
========================================
June 2026
