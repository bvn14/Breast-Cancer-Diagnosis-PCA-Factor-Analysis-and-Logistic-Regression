# Breast Cancer Diagnosis: PCA, Factor Analysis and Logistic Regression

Take-home R practical exam (DA2451 - Multivariate Methods in Business)
Author: Bavindu Gunasinghe

## What this project does

I used the Breast Cancer Wisconsin (Diagnostic) dataset to predict whether a tumor is benign (B) or malignant (M). The dataset has 569 tumors and 30 measurements for each one. I reduced the number of variables in two ways (PCA and Factor Analysis) and then used each result in a logistic regression model.

## Steps

1. **Data preparation**
   - Loaded the data and named the columns.
   - Checked for missing values and duplicates (none found).
   - Removed the ID column and standardized all 30 features.
   - Made summary statistics, histograms, a correlation heatmap, box plots and a pair plot.

2. **Principal Component Analysis (PCA)**
   - Found how many components explain about 90% of the variance.
   - Made a scree plot (PC1 explains 44.3%, PC2 explains 19%).
   - Looked at the loadings.
   - Plotted the tumors on PC1 and PC2, coloured by diagnosis. The two groups separate fairly well.

3. **Factor Analysis (FA)**
   - Used parallel analysis and a scree plot to choose the number of factors.
   - Fitted the factor model and applied varimax and promax rotation.
   - Described the factors from their loadings (for example, a "size" factor made of radius, perimeter and area).

4. **Logistic regression**
   - Split the data 80% training and 20% testing.
   - Trained lasso logistic regression on the PCA scores and on the FA scores.
   - Checked accuracy, precision, recall and F1-score.

5. **Summary**
   - Compared PCA and FA on performance and interpretability.
   - Wrote the strengths and limitations of each method.

## Results

| Model | Accuracy | Precision | Recall | F1 |
|-------|----------|-----------|--------|-------|
| PCA   | 0.982    | 0.968     | 1.000  | 0.984 |
| FA    | 0.974    | 0.968     | 0.984  | 0.976 |

Both models predict the diagnosis very well. PCA was slightly more accurate, and FA was easier to interpret.

## R packages used

tidyverse, ggplot2, corrplot, GGally, FactoMineR, factoextra, psych, GPArotation, glmnet, caret

## Files

- `Take-Home R Practical Examination.Rmd` - the R Markdown code and answers
- PDF output - the knitted report
