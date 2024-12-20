# DZ_ML
This page provides code examples for synthetic experiments performed in "Classifying Detrital Zircon U-Pb Age Distributions using Automated Machine Learning." You can use this ReadMe as a guide to creating, downloading, and testing detrital zircon age distribution datasets in machine learning pipelines. 

## Creating or Downloading Data
First, we must create a dataset using the code above or download an example dataset from the Zenodo repository listed below.

### Zenodo Repository
Use the link below to download the example synthetic dataset:

https://zenodo.org/records/14532918

Zenodo DOI: 10.5281/zenodo.14532918

This dataset represents a 50-sample model for fixed age proportion data. Each file contains all the data for each source from a set interval and the number of analyses used to create each synthetic kernel density estimate (KDE). 

### Creating a Dataset
Fixed and variable age mode datasets can be created using the following Jupyter Notebook scripts:
- Fixed Age Mode Synthetic KDE Creation.ipynb
- Variable Age Mode Synthetic KDE Creation.ipynb

For each Jupyter Notebook above, you must download the source age distributions (i.e., 'New 0.15-0.25 Sources.p') to create synthetic samples from each source. Within the Jupyter Notebook, parameters of the data creation can be changed, including:
- KDE bandwidth
- KDE partitioning
- number of samples created from each source

This data will then automatically be saved as a dictionary (i.e., '0.15-0.25 0 Sources') for each source from each similarity interval. 

