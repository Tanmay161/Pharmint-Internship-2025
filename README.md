# Overview
During the course of this internship with Pharmint Pte Ltd., I worked on creating a model to predict **survival rates** based on **gene expression data** on breast cancer patients. 
I used tools such as scikit-survival (Constructing models), pandas (Data preprocessing / handling), numpy (Transformations), and seaborn (Data visualization)

# Data
Due to the vast amount of data, the file size was too large for GitHub uploads. You can find the datasets here:
 * [Dataset 1 (df_survival)](https://xenabrowser.net/datapages/?dataset=survival%2FBRCA_survival.txt&host=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443)
 * [Dataset 2 (df_gene_expression)](https://xenabrowser.net/datapages/?dataset=TCGA.BRCA.sampleMap%2FHiSeqV2&host=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443)

# Pipeline:
1. I loaded both datasets I used
2. Filtered the datasets to only include the columns I needed.
3. Preprocessed data
   - Dropped duplicates
   - Dropped null values
   - Transposed a dataframe, so it could be merged with the other dataframe
   - Converted string values to numericals
   - Combined the dataframes into one
4. Conducted a logrank test to only keep statistically significant genes
5. Created a CoxPHFitter to filter out genes
6. Used PCA to reduce dimensionality (My variance threshold was 85%)
7. Created a Cox Proportional Hazards Model, and trained it using my cleaned data
8. Predicted risk scores for all samples
9. Categorized the risk scores into Low and High using the median
10. Conducted the same process, instead using a Random Survival Forest
11. Found the c-index of both models to assess model performance
12. Constructed Kaplan-Meier curves for both models
13. Loaded gene sets, and selected two genes with significant contributions to survival rates (UBA7, RNF31)
14. Analysed the effect of a higher gene expression of each respective gene using Kaplan-Meier curves.

# Conclusion
I reported my findings in the slideshow.

[View Research Presentation (PDF)](./Internship%20Presentation.pdf)
