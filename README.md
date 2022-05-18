# MLBOX
MLBox : a fully automated pipeline.

# Features:
* Fast reading and distributed data preprocessing/cleaning/formatting.
* Highly robust feature selection and leak detection.
* Accurate hyper-parameter optimization in high-dimensional space.
* State-of-the-art predictive models for classification and regression (Deep Learning, Stacking, LightGBM, etc).
* Prediction with model interpretation.
 
# MLBox in comparison to the other Machine Learning Libraries
MLBox focuses on the below three points in particular in comparison to the other libraries
* Drift Identification – A method to make the distribution of train data similar to the test data.
* Entity Embedding – A categorical features encoding technique inspired from word2vec.
* Hyperparameter Optimization

# Pipeline of MLBox

![Screenshot-from-2017-07-03-23-05-23](https://user-images.githubusercontent.com/55275843/169100444-959d3017-7087-4297-b70e-bf9e4b97c080.png)
The entire pipeline of MLBox has been divided into 3 sections/sub-packages.
1) Pre-Processing / Initialisation
2) Optimisation / Validation
3) Prediction

Step 1: Initialisation
From a raw dataset to a cleaned dataset with numerical features.
* Files reading:
    * Reading of several files(csv,xls,json and hdf5)
    * Task detection(binary/multiclass classification or regression)
    * Auto-merging of all the sources-information crunching
    * Split between train and test size.
    * Creation of the training data set and the test data set.
* Preprocessing/cleaning:
    * Dropping duplicates and constant features
    * Dropping drifting features
* Encoding:
    * Converting features to a unique format(float if possible or str)
    * Converting lists
    * Converting dates into timestamp
    * Target encoding for classification task only.
    * Categorical features encoding
    * Missing values encoding

Step 2 : Validation
Several models are tested and cross-validated and the best one is fitted.
* On Features:
    * Feature engineering:neural network features engineering
    * Feature Selection: filter methods,wrapper methods and l1 regularization.
* On estimator:
    * Testing of a wide range of accurate estimators:Linear model,Random Forest,XGBoost,LightGBM….
    * Hyper-parameters tuning(using TPE algorithm)
* On Validation :
    * Choice of several metrics: accuracy,log-loss,AUC,f1-score,MSE,MAE…
    * Validation Parameters: no folds,random state……

Step 3 : Application
We fit the whole pipeline and predict the target on the test set.
* Prediction:
    * Target prediction(class probabilities for classification)
    * Dumping fitted models and final predictions(.csv file)
* CPU time display
    * Models Interpretations:
    * Features importance
    * Leak detection

# Pros and Cons of MLBox

The pros are –
* Automatic task identification i.e Classification or Regression
* Basic Pre-processing while reading the data
* Removal of Drifting variables
* Extremely fast and accurate hyperparameter optimisation.
* A wide variety of Feature Selection Methods.
* Minimal lines of code.
* Feature Engineering via Entity Embeddings


The cons are-
* It is still under active development and things may break or make at any point in time.
* No support for Unsupervised Learning
* Basic Feature Engineering. You still have to create your own features.
* Purely mathematical based feature selection method. This method may remove variables which make sense from the business perspective.
* Not truly an Automated Machine Learning Library.
