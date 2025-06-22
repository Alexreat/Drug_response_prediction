# Drug Response Prediction Using Gene Expression

This project explores the prediction of drug efficacy using gene expression profiles from cell lines. The goal is to build and compare regression models (linear, Ridge, and XGBoost) to predict the sensitivity of a specific drug based on transcriptomic features.

## Data Sources

- **Gene Expression:** `OmicsExpressionProteinCodingGenesTPMLogp1.csv`  
  Log-transformed TPM values for protein-coding genes across cell lines.
- **Drug Response:** `Repurposing_Public_24Q2_Extended_Primary_Data_Matrix.csv`  
  Drug efficacy scores across cell lines.

## Target Drug

The analysis focuses on the drug: BRD:BRD-K00003313-001-01-9
This was selected based on highest combined coverage and variance across samples.

## Workflow

1. **Data Preprocessing**
   - Filter cell lines present in both datasets
   - Handle missing values (NaN)
   - Clip outliers in drug response using IQR-based winsorization

2. **Feature Selection**
   - Compute correlation between each gene and drug efficacy
   - Select top 50 genes by absolute correlation

3. **Modeling**
   - Baseline: Linear Regression
   - Regularized: RidgeCV
   - Nonlinear: XGBoost

4. **Evaluation**
   - R² score
   - RMSE
   - Scatter plots and learning curves
   
## Results (R² Score)

| Model             | R² Score |
|------------------|----------|
| Linear Regression| ~0.086   |
| Ridge Regression | ~0.117   |
| XGBoost          | ~-0.39   |

## Next Steps

- Explore alternative models: Random Forests, SVMs
- Integrate pathway knowledge or gene networks (e.g., GNNs)
- Compare model generalization on different drugs

#  Author

Alex Reategui | MSc in Machine Learning & Deep Learning  | Computational Biologist

