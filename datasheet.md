# Datasheet for Datasets

## Dataset name

**Masked Mitochondrial Delivery Synthetic Benchmark Datasets**

## One-line summary

Synthetic cell-level and mouse-level datasets designed to benchmark a computational proof of concept for masked mitochondrial delivery and downstream bioenergetic rescue.

## Motivation

These datasets were created to support a computational proof-of-concept study exploring whether a masked mitochondrial delivery strategy could improve uptake and rescue mitochondrial dysfunction more effectively than unmasked mitochondrial transfer. The datasets were designed to enable statistical analysis, multivariate analysis, machine learning, and visualization in a reproducible notebook workflow.

## Composition

The dataset collection contains two primary components:

### 1. Cell-level dataset

The cell-level dataset contains simulated observations representing cellular mitochondrial rescue phenotypes across four groups:

- Healthy
- Disease_Vehicle
- Disease_UnmaskedMito
- Disease_MaskedMito

Typical variables include:

- uptake_index
- ATP_nmol_mg
- MMP_ratio
- ROS_rel
- OCR_pmol_min
- apoptosis_pct
- inflam_rel
- viability_pct
- rescue_binary

### 2. Mouse-level dataset

The mouse-level dataset contains simulated observations representing organism-level outcomes across the same four groups. Variables include:

- tissue_uptake
- tissue_ATP
- tissue_ROS
- neuromotor_score
- weight_change_pct
- survival_days

## Instance counts

Typical simulation settings used in the notebook are:

- **400 cell-level observations**, approximately 100 per group.
- **160 mouse-level observations**, approximately 40 per group.

These counts may be adjusted if the notebook is rerun with modified parameters.

## Source of data

These datasets are **synthetic**. They were generated computationally using group-specific means, noise terms, and biologically motivated dependency structures. Parameter values were chosen to be literature-aligned in direction and plausible in scale, but they are not direct measurements from a published experimental study.

## Collection process

There was no real-world data collection. Instead, the notebook generated data using stochastic simulation based on assumptions such as:

- disease reduces uptake, ATP, membrane potential, respiration, and viability,
- disease increases ROS, apoptosis, and inflammatory burden,
- unmasked mitochondrial transfer partially restores function,
- masked mitochondrial delivery provides stronger restoration than unmasked transfer.

## Preprocessing and cleaning

The synthetic data generation process included:

- random sampling from group-specific normal distributions,
- clipping of variables to preserve biologically plausible bounds,
- derivation of rescue labels from rule-based thresholds,
- standardization of selected features before PCA and some machine-learning models.

## Recommended uses

These datasets are appropriate for:

- teaching statistics and machine learning,
- building manuscript-style figures and tables,
- prototyping computational biology workflows,
- testing code for visualization or model evaluation,
- exploring mitochondrial therapeutics concepts.

## Non-recommended uses

These datasets should not be used for:

- biological inference about real treatment efficacy,
- clinical prediction,
- translational decision-making,
- regulatory submission,
- claims about exact experimental magnitudes.

## Distribution and access

The datasets are distributed through the notebook outputs and exported CSV tables. They are lightweight and easy to reproduce by rerunning the notebook with the same random seed.

## Reproducibility

A fixed random seed was used in the notebook to make the generated datasets reproducible. If users change the seed or simulation parameters, the exact values will differ while preserving the overall conceptual structure.

## Known limitations

- The data are synthetic and therefore do not capture full biological complexity.
- Noise structure is simplified compared with real experimental systems.
- Inter-variable relationships were intentionally designed and may be stronger or cleaner than real biology.
- Mouse survival data are simulated continuous outcomes, with Kaplan-Meier-like curves derived from these event times.
- The datasets do not contain metadata such as sex, strain, age, batch effects, isolation protocol, or mitochondrial donor source unless explicitly added by the user.

## Sensitive information

The datasets contain no personal, clinical, or identifiable information.

## Labels and targets

### Cell-level target

- **rescue_binary**
  - Derived from thresholds on ATP, viability, ROS, and apoptosis.

### Mouse-level target

- **survival_days**
  - Simulated as a function of tissue uptake, tissue ATP, ROS, neuromotor score, and weight change.

## Dataset maintenance

This datasheet should be revised if:

- real measured datasets are incorporated,
- variable definitions are changed,
- sample sizes or generation rules are modified,
- additional metadata or labels are added.

## Citation guidance

When using these datasets, explicitly describe them as **synthetic, literature-inspired benchmark datasets** created for a computational proof of concept in masked mitochondrial delivery.
