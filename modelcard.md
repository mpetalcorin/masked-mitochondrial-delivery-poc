# Model Card

## Model name

**Masked Mitochondrial Delivery Proof-of-Concept Models**

## One-line summary

A suite of statistical and machine-learning models built on synthetic mitochondrial rescue data to classify cellular rescue and predict organism-level survival in a masked mitochondrial delivery framework.

## Model scope

This repository does not contain a single deployed predictive model. Instead, it includes a small set of analytical models applied within a computational proof-of-concept workflow:

- **Logistic regression** for rescue classification.
- **Random forest classifier** for rescue classification and feature ranking.
- **Ridge regression** for survival prediction.
- Additional comparison regressors such as random forest regression and gradient boosting regression.

These models are used to test whether simulated biological features can distinguish rescued from non-rescued states and predict survival outcomes.

## Intended use

These models are intended for:

- educational demonstration,
- computational hypothesis generation,
- analytical prototyping,
- manuscript and figure development,
- benchmarking end-to-end machine-learning workflows in a mitochondrial therapeutics setting.

These models are **not intended** for:

- clinical diagnosis,
- treatment selection,
- regulatory use,
- direct biological decision-making,
- patient risk prediction.

## Input features

### Cell-level classification features

The rescue classification workflow uses features such as:

- uptake_index
- ATP_nmol_mg
- MMP_ratio
- ROS_rel
- OCR_pmol_min
- apoptosis_pct
- inflam_rel
- viability_pct

### Mouse-level regression features

The survival prediction workflow uses features such as:

- tissue_uptake
- tissue_ATP
- tissue_ROS
- neuromotor_score
- weight_change_pct

## Target variables

### Rescue classifier target

- **rescue_binary**
  - 1 = rescued
  - 0 = not rescued

### Survival regression target

- **survival_days**

## Data source

The models were trained and evaluated on **synthetic datasets** generated from biologically plausible parameter ranges inspired by peer-reviewed mitochondrial transplantation literature. These data are not patient-derived, animal-derived, or experimentally measured in this repository.

## Training and evaluation approach

### Classification

Data were split into training and test sets. Rescue classification performance was assessed using:

- accuracy,
- precision,
- recall,
- F1 score,
- ROC AUC,
- confusion matrix.

### Regression

Survival prediction performance was assessed using:

- mean absolute error, MAE,
- root mean squared error, RMSE,
- coefficient of determination, R²,
- observed versus predicted plots.

## Reported behavior

In this proof-of-concept setting:

- rescue status was strongly separable in feature space,
- ATP, ROS, and apoptosis emerged as dominant features for rescue prediction,
- integrated tissue features predicted survival with good regression performance.

These outcomes reflect the designed structure of the synthetic dataset and should not be interpreted as validated biological or therapeutic performance claims.

## Assumptions

The models assume:

- masked mitochondrial delivery improves effective uptake,
- higher uptake improves ATP restoration,
- better ATP and membrane potential reduce ROS,
- lower ROS reduces apoptosis and inflammatory burden,
- improved tissue-level bioenergetics contributes to longer survival.

## Limitations

- All training and test data are synthetic.
- The modeled dependencies are simplified relative to real mitochondrial biology.
- Performance metrics are influenced by the simulated separability of treatment groups.
- The models have not been externally validated on real experimental datasets.
- No fairness or demographic analysis applies because the data do not represent human populations.

## Risks

Potential misuse includes:

- overstating the predictive or therapeutic validity of the models,
- treating the outputs as biological evidence rather than simulation outputs,
- applying the workflow directly to clinical questions without real validation.

## Ethical considerations

Because the models are trained on synthetic data, they avoid direct privacy and consent issues. However, transparent communication is essential so users understand that the models are conceptual and not clinically actionable.

## Maintenance

This model card should be updated if:

- real experimental data are added,
- new model architectures are introduced,
- feature definitions change,
- model evaluation procedures are expanded.
