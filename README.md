# DEPTH
DEPTH evaluates the tumor heterogeneity level of each tumor sample based on gene expression profiles Heterogeneity score vignette

Cite the code: 

# DEPTH

DEPTH evaluates the tumor heterogeneity level of each tumor sample based on gene expression profiles Heterogeneity score vignette


## Description

This vignette shows an example of how to use the DEPTH algorithm to calculate tumor heterogeneity level in R. 

DEPTH evaluates the tumor heterogeneity level of each tumor sample based on gene expression profiles.


## Details

### Input Two files need to be input into the DEPTH function: 

1) **exp:** gene expression profiles in both tumor and normal samples (microarray or RNA-Seq data, normalized);    


                                  Table 1. RNA expression of input data

|Identification|TCGA-A6-2671-11A-01R-A32Z-07|TCGA-A6-2675-11A-01R-1723-07|TCGA-A6-2675-01A-02R-1723-07|
| :-----: | :------: | :------: | :-----: |
| SKAP1 |  6.22  |  4.36  |  6.00 |
|TPSB2|9.39|9.45|9.21|
|PLXNB3|6.09|8.45|4.95|
|VAT1L|7.45|7.76|6.13|
|VIP|9.43|10.99|7.71|
|WNT5B|7.52|7.80|6.29|
|ZAP70|6.43|5.13|5.94|
|TNFRSF10C|3.67|3.90|5.46|
|ZNF167|4.46|6.10|5.88
|KIF26B|3.62|4.61|7.68|
|STRA6|2.26|1.08|6.57|


2) **match**: sample type ("tumor" or "normal") in "exp".   
 
 
 Table2. Identification of tumor sample and normal sample 

|State|Identification|
| :-----: | :-----: | 
|Normal|TCGA-A6-2671-11A-01R-A32Z-07|
|Normal|TCGA-A6-2675-11A-01R-1723-07|
|Tumor|TCGA-A6-2675-01A-02R-1723-07|
|Normal|TCGA-A6-2678-11A-01R-A32Z-07|
|Normal|TCGA-A6-2679-11A-01R-A32Z-07|
|Normal|TCGA-A6-2680-11A-01R-A32Z-07|
|Normal|TCGA-A6-2682-11A-01R-A32Z-07|
|Tumor|TCGA-A6-2682-01A-01R-1410-07|


**Table 1** is an example of **"exp"** and **Table 2** is an example of **"match"**.  

Example **"exp"**: gene expression profiles in cholangiocarcinoma from the genomic data commons data portal (https://portal.gdc.cancer.gov/). There are 45 samples (36 tumor and 9 normal samples) and 20,531 genes in **"exp"**. The DEPTH function will output the heterogeneity score for each of the 36 tumor samples as shown in **Table 3**.  


 Table 3. heterogeneity score of tumor samples in output data 

|Samp|heterogeneity score|
| :-----: | :-----: | 
|TCGA-A6-2675-01A-02R-1723-07|2.954321|
|TCGA-A6-2682-01A-01R-1410-07|4.307523|
|TCGA-A6-2684-01A-01R-1410-07|3.916457|
|TCGA-A6-2685-01A-01R-1410-07|2.85864|


## Installation
You can install the released version of ‘DEPTH’ with:

```  
if (!requireNamespace("devtools", quietly = TRUE))
    install.packages("devtools")
    
devtools::install_github("WangX-Lab/DEPTH/DEPTH")
```

## Examples

```  
library(DEPTH)
DEPTH(exp, match) 
```



