# CSCA-5632-Unsupervised-Algorithms
## Final Project

Forward

Introduction

Dataset Overview

Data Exploration

Data Preprocessing

Feature Engineering

Model Selection

Training and Evaluation

Results

Conclusion

Future Work


### Forward
Welcome to my final project. For this project I have decided to join a Kaggle competiton for classification of breast cancer. This is a project that I feel has real world   
applications, and models like this one would be of great importance to the medical field. Lifes could potentially be saved, and much better outcomes for patients if models   
like the these are used for early detection.   

### Introduction
I will attempt to, through unsupervised learning models and preprocessing techniques to: clean, train, and predict what the classification of each data point is. My goal   
for this project is to create a model that with a fairly high degree of accuracy can separate the benign from the malignant. I will do my best to add visual elements to   
help better understand the data, the models and the results. 

### Dataset Overview
The dataset consists of 3 CSV files. The first is the training data, it consist of 31 features, and 1 label of M or B (malignant or benign). The 31 features are non-negative  
measurements mostly of size, shape, and other features of what I assume are masses presumed to be either benign tumors, or malignant tumors.  The second file in the set is   
the testing data. This data consists of only the X dataset, and does not contain labels. To detimine accuracy there must be a submission to the competition, this it done with  
the aid of the third file, which is a sample submission csv. By overwriting the data in the predictions column, and saving the CSV to the output, the Kagle website will   
evaluate the model performance, and return a score.   

### Data Exploration
For my EDA, I started with some basic checks on the structure of the data. I looked at the number of features (right around 30 useful features), the number of null values(398,   
all in the same feature which was dropped for that reason), and changing the label data from a set of strings to a bool for use in visualizations. Next I created a heatmap
correlation matrix for the dataset in order to better see relationships of each of the features to the labels, and to the other features. Finally I created a set of 
distribution plots to show the range of each of the features.

### Data Preprocessing
After some basic clean-up of removing the label data from the training set and creating a separate set, and dropping the on feature with nan values. I split the data into 
testing and training sets so I could more accurately measure the performance of my models. Other preprocessing method that I did try further into the training of the models
did not imporve upon the models effectiveness. These included scaling and normalizing the data. But as there are very few zero in the data, and all are non negative, I beleive 
that is why these techniques were not beneficial in these models. 

### Feature Engineering
Feature engineering for this data set was rather simple, and consisted of removing the 1 bad columns that was called Unnamed: 32, and litteraly had more nan than actual
values. Once that was taken care of, the rest of the data seems to be clean, and relevant. There were a few features that showed low corelation, but removing them led to very
slightly lower accuracies, and so were left in to help acheive a better score. 

### Model Selection
For this assignement, I was not sure what the best model would be, so I ran 3 of them, along with 2 dimensional reduction techniques. The dimensional reduction teqniques used
were NMF, and PCA. The models used are Kmeans, Agglomerative Clustering, and NMF (I decided to try stacking the NMF to test whether is was possible and would make a differnce
more on that later). Next a wrote a function to iterate through the differnt dimensional reduction techniques, and models and return a dataframe with the results. Once I did 
that I also added a function to test the performace of several supervised learning models. 

### Training and Evaluation
In the functions created to evaluate different models an the dataset, I used gridsearchCV and a parameter dictionary to optimize the models while training and testing them. 
Part of this system required a mapping function that would iterate through permutaions of the predictions and the labels to map out the prediction pair map with the highest 
accuracy. The result were returned as the best accuracy, and settings used to acheive said result. I also spent some time to create the same type of function for the 
supervised counterparts to evalute the performance of my models against their competitors.

### Results
I was not sure what to expect, as I had previous chossen a datset from a different competion on kaggle(welding defects) that did not lend itself well to unsupervised models. 
Initial testing on this dataset revealed it was a good application for unsupervised models. In the end, I only submitted the unsupervised predictions to the competition as that
is what the course was about. At 90% accuracy on the blind test dataset left me very happy with the results. But as seems to always be the case, the supervised models were much
more accurate than the unsupervised models, and if label are available, will generally always be a better option. 

### Conclusion
I did not expect the results from these models. I find it facinating that you can classify datapoints with any degree of certainty without first training the model with labels.
I did enjoy working on this problem and learned a good deal from it.
Some key takeaways from this project:
1. Don't underestimate the power of an unsupervied model, for some applications they can compare with supervised models, which can be invaluable if you don't have labeled data.
2. There is a lot of trial and error in building effective models, don't get discouraged by setbacks, and failures. Take the time to understand what is actually happening with
the data.
3. Clean data is key to accurate predictions. The data in this set was very clean, and required very little processing, and no guesswork to fill in blanks.  

### Future Work
I will not likely do much more with this specific dataset as my models were so accurate. But I will very much be continuing on with Kaggle, and joining more of the competions 
in the future.

