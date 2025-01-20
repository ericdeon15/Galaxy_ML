# Galaxy_ML

A series of Jupyter Notebooks with methods and models to predict the local density of galaxies.

## Overview

This research aims to train a model to accurately predict the local density of galaxies in the **2MRS (2 Micron Redshift Survey)** catalog, which provides almost full sky coverage but sacrifices the ability to detect faint galaxies. To address this limitation, we combine data from the **SDSS (Sloan Digital Sky Survey)** catalog, which captures faint galaxies but only covers a limited portion of the sky. The model is trained on the overlap region between the two catalogs, leveraging the more accurate galaxy density calculations from SDSS data.

## Main Jupyter Notebooks

### 1. **Galaxy ML Testing**

This is the first attempt in this research, focusing on preliminary testing and understanding of the data and models. The analysis relies solely on data from the following CSV files:

- `EnvironmentsFrom2MRS.csv`
- `EnvironmentsFromSDSS.csv`

### 2. **V2 Galaxy ML Testing**

In the second iteration of the research, the original, limited dataset was augmented with additional columns from the full 2MRS dataset. The extended dataset can be accessed [here](http://tdc-www.cfa.harvard.edu/2mrs/).

### 3. **V3 Galaxy ML Testing**

The third iteration introduced more features to improve the model’s predictive performance. Data from the **Tully 2015** paper was integrated, specifically the **T5 galaxy-groups table**. As of the end of Fall 2024, preliminary tests have been conducted on some of these features, showing promising results. The dataset is stored in the `overlap_t5_file.csv` file, and further exploration of this data is planned. You can access the Tully 2015 paper [here](https://ui.adsabs.harvard.edu/abs/2015AJ....149..171T/abstract).

## Current Data Pipeline

The data processing pipeline includes the following steps:

- **Outlier Pruning:** Using the IQR (Interquartile Range) method to remove outliers.
- **Log Transformation:** Logarithmic transformation of the local density columns.
- **Train/Test Splits:** Creation of training and testing datasets.
- **Normalization:** Scaling the data using Scikit-learn's scalers for feature normalization.

## Other Notes

- The CSV files used in the project are stored as pointers in the repository via **Git LFS**. To view them outside of GitHub, you will need to download them using Git LFS.
