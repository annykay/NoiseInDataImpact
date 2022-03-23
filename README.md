# Missing values, noise and their effects

## Welcome to #team 10 project!

Here we investigated the impact of noise and missing values on the quality of different machine learning models. Our aim was to explore how different classification models respond to noise and give some practical recommendations.To do it we took 4 different datasets, corrupted them, trained models on corrupted datasets and investigated the performance. We tried to spoil different parts of our datasets: features, targets, important features – and   see how the models will respond to it.

![изображение](https://user-images.githubusercontent.com/52636876/159592306-d514c143-9acf-47b1-ac90-3ef97aaf046b.png)


------------------
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

