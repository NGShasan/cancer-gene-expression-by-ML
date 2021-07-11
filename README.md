#  Cancer Gene Expression by Machine Learning

<img width="822" alt="1" src="https://user-images.githubusercontent.com/65890522/124380532-5650d600-dcbd-11eb-8bfa-a7dd198d6e3a.png">

This project aims to predict people who will survive breast cancer using machine learning models with the help of clinical data
and gene expression profiles of the patients. Using machine learning models on gene data helps us better understand the disease 
and determine how well treatment methods work.

# What is Breast Cancer?

Breast cancer is a type of cancer that occurs when some cells in the breast grow excessively. This type of cancer causes the greatest number 
of cancer-related deaths among women. There are 5 known types of breast cancer based on the occurrence of the tumor as you can see in the figure. 
These genes can be also passed from parent to child. Therefore, breast cancer is also a genetically transmitted cancer type.

<img width="573" alt="2" src="https://user-images.githubusercontent.com/65890522/124380579-b6e01300-dcbd-11eb-9df7-ea0666399326.png">


# Dataset

This dataset includes 31 clinical attributes, mRNA levels z-score for 331 genes, and mutation in 175 genes for 1904 breast cancer patients. 

# Importance of the Genes

**BRCA1 and BRCA2:** The most common cause of hereditary breast cancer is an inherited mutation in the BRCA1 or BRCA2 gene. In normal cells, these genes 
help make proteins that repair damaged DNA. Mutated versions of these genes can lead to abnormal cell growth, which can lead to cancer.

**Other Genes:** These gene mutations are much less common, and most of them do not increase the risk of breast cancer as much as the BRCA genes. 
Some of them are ATM, TP53, CHEK2, PTEN, CDH1, STK11 and PALB2.

# Data Preprocessing
 
In the preprocessing part, first I cleaned the data and according to skew-distribution fill the missing values with the mode of them. 
After that, I applied Label Encoding and One-Hot Encoding to the categorical clinic data respectively.

## Label Encoding:

The following categorical features are ordinal data encoded with the label encoding method.

* cellularity
* cancer_type_detailed
* type_of_breast_surgery
* her2_status_measured_by_snp6
* pam50_+_claudin-low_subtype
* her2_status_measured_by_snp6
* tumor_other_histologic_subtype
* integrative_cluster
* 3-gene_classifier_subtype
* death_from_cancer

## One-Hot Encoding:

The following categorical features are nominal data encoded with the one-hot encoding method.

* er_status_measured_by_ihc
* er_status, her2_status
* inferred_menopausal_state
* primary_tumor_laterality
* pr_status
* oncotree_code

# Data Visualization

In order to better understand the data and make some inferences, I analyzed using the following data visualization techniques.

## Correlation Matrix

![31](https://user-images.githubusercontent.com/65890522/124380625-f3137380-dcbd-11eb-9924-efb5eae87320.png)


## Treatment Types & Survivals

![36](https://user-images.githubusercontent.com/65890522/124380645-0a526100-dcbe-11eb-8b48-c045a2745805.png)

## Survived Patients by Treatment Groups

![43](https://user-images.githubusercontent.com/65890522/124380653-1e965e00-dcbe-11eb-830b-1fa113325b93.png)


# Choosing Best PCA

PCA is an algorithm that reduces the dimension of datasets that have a high number of features. When dealing with the PCA, the scikit-learn library can be used
to determine the number of components of the newly created data set. As you can see in the below plot, to get 95% of variance explained I need 375 
principal components.

![52](https://user-images.githubusercontent.com/65890522/124380674-42f23a80-dcbe-11eb-8229-7adb23ce54c6.png)


# Accuracy Scores


   | Model                | Train Score  | Test Score   |
   | :-------------:      | :----------: | :-----------:|
   |  KNN                 | 0.75         | 0.73         |
   |  Logistic Regression | 0.82         | 0.89         |
   |  Random Forest       | 1.0          | 0.62         |
   |  Decision Tree       | 0.69         | 0.62         |
   |  Extra Trees         | 0.93         | 0.58         |
   |  AdaBoost            | 1.0          | 0.65         |



  ![63](https://user-images.githubusercontent.com/65890522/124380682-543b4700-dcbe-11eb-84e8-e9c92e0e76d0.png)
  

# References:

1) https://www.nature.com/articles/s41523-018-0056-8
2) https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5461908/

