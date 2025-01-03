# DZ_ML
This page provides code examples for synthetic experiments performed in "Classifying Detrital Zircon U-Pb Age Distributions using Automated Machine Learning." You can use this ReadMe as a guide to creating, downloading, and testing detrital zircon age distribution datasets in machine learning pipelines. 

## Creating or Downloading Data
First, we must create a dataset using the code above or download an example dataset from the Zenodo repository listed below.

### Zenodo Repository
Use the link below to download the example synthetic dataset:

https://zenodo.org/records/14532918

Zenodo DOI: 10.5281/zenodo.14532918

![Description]((https://github.com/jackfekete01/DZ_ML/blob/assests/Images/Zenodo_final.png))

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

## AutoML Pipeline Development using TPOT
Here, we provide an example of the AutoML optimization process using TPOT. This example can be found in:
- 'TPOT Example.ipynb'

To begin, we select a similarity interval of data to test this on; in our example, this is the 0.95-0.99 similarity interval. We then select a subset of this data to create an individual model by selecting the number of sources included and the number of analyses per sample. In our case, we select five sources with 115 analyses per synthetic KDE. This data is then formatted and preprocessed for the TPOT classifier.

Finally, we select hyperparameters for the TPOT classifier. In this example, we keep the number of iterations and run time low to limit the optimization time. However, these hyperparameters can be increased for better results. 

Once TPOT has finished running, we export an optimized pipeline:
- 'Optimized TPOT Pipeline Example.py'

An example pipeline has been generated if users want to skip this step.

## Synthetic Data Modeling
Here, we provide a complete code for modeling all synthetic scenarios using either given or generated data. This example code can be found here:
- 'Synthetic Data Modeling Loops.ipynb'

Users can alter some code parameters (e.g., the number of model repeats and AutoML pipeline), but most parameters should not be changed. Once finished, this code will create dictionaries of stored results. Depending on the number of model repeats specified, this code can become time-consuming, so premade results can be found in the asset branch.

## Plotting Results
Using the following code, users can plot all data results as a heatmap:
- 'Graphing Matrix.ipynb'

Graphing the results in heatmaps allows users to visualize the many model results previously generated easily. Here, we plot the AutoML (top), Random Forest (middle), and R2 results (bottom) for every similarity interval, analyses per sample, and sources included. Note how the model results can have considerable variations from model to model. To create less variability in heatmap plots, increase the number of model repetitions in the previous code.   

