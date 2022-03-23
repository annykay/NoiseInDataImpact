# Missing values, noise and their effects

## Welcome to #team 10 project!

Here we investigated the impact of noise and missing values on the quality of different machine learning models. Our aim was to explore how different classification models respond to noise and give some practical recommendations.To do it we took 4 different datasets, corrupted them, trained models on corrupted datasets and investigated the performance. We tried to spoil different parts of our datasets: features, targets, important features – and   see how the models will respond to it.

![изображение](https://user-images.githubusercontent.com/52636876/159592306-d514c143-9acf-47b1-ac90-3ef97aaf046b.png)


------------------
## Dataset Preprocessing 
For our analysis we used 4 datasets from kaggle. Below you can see their description. Each dataset was preprocessed before our experiments. All steps that were done with the data are written in the DataPreprocessing.ipynb

![изображение](https://user-images.githubusercontent.com/52636876/159603176-39f9b9df-2b2b-4385-813b-7ef2477b15ce.png)


## Data Corruptions Experiments 

There are two main ways to corrupt the data: add noise to it and drop some values 

For noise simulation we used three different approaches:
1) Random Change;
   Each value in the dataset can be replaced by a random value with some probability. The noise level, in this case is the probability to be changed. 
   Example of provided experiment and results can be seen at ALEXANDERS_NOTEBOOK_PATH 
2) Gaussian Noise;
   Can be added to numerical features only. We generate samples from random gaussian distribution and add them to our data. 
   See how it worked with our dataset in AIRAT_NOTEBOOK_PATH
3) Flipping
  Flip the values of some feature for a pair of samples. Noise level here is the amount of flips, so it can be more than one. The most specific case of noise adding, because it does not change the data itself, just permut it. 
  Want to try? Examples are already at EGOR_NOTEBOOK_PATH 
  
For dropping values from the data set we had only one approach - missing at random - each value has equal probability to be missed. But! We tried different approaches for data imputation. That were: 
1) Statistical approaches 
   Zero, Mean, Median - simple and intuitive. How we implemented them - see in VISHAL_NOTEBOOK_PATH
2) Regression ML-based approaches 
   A little bit more complex, but possible.  See examples in /MLbasedImputation directory. Here different parts of data corruption splitted to different notebooks. 

   MLbasedImputation/MissingFeaturesAndImputation.ipynb - contains faeature corruption experiments
   MLbasedImputation/MissingImportantFeaturesAndImputation.ipynb- experiments with important feature corruptions
   MLbasedImputation/MissingTargetsAndImputation.ipynb - target corruption.

All this notebooks can be run with colab. 

--------------------
## Brief Results
 - The XGB model can handle random noise in train data better, which seems like overfitting. But for the test date, random noise affects all models equally badly;
 - Highly Imbalanced datasets react to gaussian noise much less than balanced ones;
 - Influence of gaussian noise to Multiclass datasets greater;
 - Gradient models and imbalanced datasets turned out to be the most resistant to flipping noising;
 - Balanced and multiclass datasets are more affected by the random null values; 
 - If the dataset is highly imbalanced and has null values in labels, it is disastrous. However, it might be a better idea to fill the null values with the dominant class. If dataset has null values in features one can use any value to fill them from 0, mean and median, in almost all the cases it doesn’t affect much but there are more efficient methods than these.
 - ML based imputation methods perform uniformly well, but the best ones were LR and ETR




