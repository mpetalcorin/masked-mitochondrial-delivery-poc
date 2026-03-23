# masked-mitochondrial-delivery-proof-of-concept

Computational proof of concept for masked mitochondrial delivery, integrating literature-benchmarked synthetic datasets, statistical analysis, machine learning, and survival modeling to evaluate enhanced bioenergetic rescue.

## Overview

This repository presents a computational proof of concept for a **masked mitochondrial delivery** strategy designed to improve mitochondrial uptake and downstream rescue of cellular and organism-level bioenergetic function. The project uses **synthetic datasets** inspired by biologically plausible trends reported across the mitochondrial transplantation literature and evaluates treatment performance using classical statistics, multivariate analysis, machine learning, and survival modeling.

The framework compares four groups:

- **Healthy**
- **Disease_Vehicle**
- **Disease_UnmaskedMito**
- **Disease_MaskedMito**

The central hypothesis is that a masking strategy can improve effective mitochondrial delivery, leading to stronger restoration of ATP production, lower oxidative stress, higher viability, improved tissue function, and longer survival.

## Objectives

This repository was built to:

1. Simulate literature-aligned cell-level and mouse-level datasets for mitochondrial rescue.
2. Evaluate whether masked mitochondrial delivery outperforms unmasked mitochondrial transfer.
3. Demonstrate a complete analytical workflow, from simulation to figures, tables, and predictive modeling.
4. Provide a reusable scaffold for future experimental, translational, or educational work in mitochondrial therapeutics.

## Repository contents

```text
masked_mito_transplantation_poc.ipynb
masked_mito_transplantation_poc_executed.ipynb
figures/
fig1_cell_uptake.png
fig2_cell_atp.png
fig3_cell_ros.png
fig4_cell_viability.png
fig5_mouse_survival_box.png
fig6_cell_correlation_matrix.png
fig7_pca_cells.png
fig8_confusion_matrix_best_classifier.png
fig9_classifier_feature_importance.png
fig10_survival_regression_observed_vs_predicted.png
fig11_km_survival_curves.png
tables/
table1_cell_group_summary.csv
table2_cell_anova.csv
table3_cell_correlations.csv
table4_pca_loadings.csv
table5_classifier_metrics.csv
table6_feature_importance.csv
table7_mouse_group_summary.csv
table8_mouse_anova.csv
table9_regression_metrics.csv
README.md
modelcard.md
datasheet.md
```

## Datasets

### Cell-level dataset

The cell-level synthetic dataset represents mitochondrial rescue phenotypes across four treatment groups. Variables include:

- uptake_index
- ATP_nmol_mg
- MMP_ratio
- ROS_rel
- OCR_pmol_min
- apoptosis_pct
- inflam_rel
- viability_pct
- rescue_binary

### Mouse-level dataset

The mouse-level synthetic dataset represents tissue and organism outcomes. Variables include:

- tissue_uptake
- tissue_ATP
- tissue_ROS
- neuromotor_score
- weight_change_pct
- survival_days

## Methods summary

The workflow includes:

- biologically structured synthetic data generation,
- descriptive statistics,
- one-way ANOVA,
- Pearson correlation analysis,
- principal component analysis, PCA,
- k-means clustering,
- rescue classification using logistic regression and random forest,
- survival prediction using ridge regression and other regressors,
- Kaplan-Meier-like survival visualization,
- export of manuscript-style figures and tables.

## Main outputs

### Figures

The notebook generates and saves publishable PNG figures including:

- cellular uptake,
- ATP,
- ROS,
- viability,
- mouse survival,
- correlation matrix,
- PCA embedding,
- confusion matrix,
- classifier feature importance,
- observed versus predicted survival,
- Kaplan-Meier-like survival curves.

### Tables

CSV tables are exported for:

- group summaries,
- ANOVA results,
- PCA loadings,
- classifier performance,
- feature importance,
- regression performance.

## How to run

### Requirements

Recommended Python version: **3.10+**

Install dependencies:

```bash
pip install numpy pandas scipy scikit-learn matplotlib jupyter
```

### Run the notebook

```bash
jupyter notebook masked_mito_transplantation_poc.ipynb
```

## Interpretation

This repository is a **computational proof of concept**, not a real preclinical efficacy study. The datasets are synthetic and designed to be biologically plausible, literature-aligned, and analytically useful. Statistical significance and model performance reflect the properties of the simulated data, not direct empirical validation.

## Intended use

This repository may be useful for:

- hypothesis generation,
- teaching and training,
- manuscript prototyping,
- AI and ML workflow demonstrations,
- planning experimental mitochondrial delivery studies.

## Limitations

- The data are simulated rather than measured.
- The framework does not capture all biological complexities of mitochondrial isolation, transport, compatibility, biodistribution, or immune response.
- Survival curves are Kaplan-Meier-like visualizations derived from simulated event times.
- The workflow is meant to support conceptual and analytical development, not clinical inference.

## Suggested citation
Petalcorin, M.I.R. (2026). Masked Mitochondrial Delivery as a Computational Proof of Concept for Enhanced Cellular Bioenergetic Rescue and Survival Benefit. https://github.com/mpetalcorin/masked-mitochondrial-delivery-poc

## References
- Chen, E. (2026, March 19). Masked mitochondria slip into cells to treat disease in mice. Nature. https://doi.org/10.1038/d41586-026-00869-2
- Du, S., et al. (2026). Transplantation of encapsulated mitochondria alleviates dysfunction in mitochondrial and Parkinson’s disease models. Cell. Advance online publication. https://doi.org/10.1016/j.cell.2026.02.023
 
If you adapt this repository for academic or educational use, cite it as a computational proof of concept for masked mitochondrial delivery and clearly state that the datasets are synthetic.

## License
MIT 

