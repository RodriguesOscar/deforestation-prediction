# Dataset Characteristics

## Overview

In this milestone, you are required to explore and analyze the dataset you are using for your project. Understanding your dataset is a critical component of any machine learning project.  
Utilize statistical graphics, plots, and information tables to summarize the dataset's main characteristics.

## Guidelines

Provide information on the following issues:

- **Dataset Overview**  
  The dataset contains 992 samples, each corresponding to a municipality-year pair in Amazonas (2007–2022). Each sample includes pixel counts of MapBiomas land cover classes (e.g., forest, pasture, urban). Data was extracted by clipping yearly raster files to IBGE municipality geometries. This structured format supports time-series modeling of deforestation.

- **Missing Values**  
  Some land cover classes (e.g., 30, 39, 20) have missing values (NaNs), which likely represent a true absence of that class in a given municipality-year. These can be safely filled with 0 to preserve the semantic meaning of “no coverage.”

- **Feature Distributions**  
  The distribution of pixel counts across features is highly skewed. Forest (class 3) dominates most samples, while several anthropic classes appear infrequently. This reflects the largely preserved nature of the Amazonas biome and may require feature scaling or transformations for certain models.

- **Possible Biases**  
  Spatial and temporal coverage is uniform (62 municipalities × 16 years). However, there is a class imbalance: natural vegetation is dominant, while deforestation-related classes are underrepresented. This bias must be accounted for in model evaluation using metrics beyond accuracy, like F1-score or AUC.

- **Correlations**
We computed the Pearson correlation between land cover classes across all municipalities and years. The heatmap reveals several useful patterns:

- Strong positive correlations between natural vegetation classes (e.g., classes 11, 6, 33).
- A strong negative correlation between forest (class 3) and anthropic classes like pasture (class 15), which supports the expected deforestation dynamic.
- Sparse classes such as 39, 31, and 20 show weak or no correlation due to their limited presence in the data.

These insights are useful to identify redundant features or underlying relationships for future model selection.

Follow the instructions provided in brackets in the [Jupyter/Colab notebook](exploratory_data_analysis.ipynb) in this folder.

## Submission

Complete the [Jupyter/Colab notebook](exploratory_data_analysis.ipynb) to conduct your analysis of the dataset characteristics.
