
# Health Anamoly Detection

Anamoly detection is nothing  but the detection of  something that is unusual or uncommon within the data. 

    
  
Basically it is considered as the outliers detection in the given distribution.
An outlier is any data point which differs greatly from the rest of the observations in a dataset.



-->Outliers are of two types: Univariate and Multivariate. A univariate outlier is a data point that consists of extreme values in one variable only, whereas a multivariate outlier is a combined unusual score on at least two variables. Suppose you have three different variables – X, Y, Z. If you plot a graph of these in a 3-D space, they should form a sort of cloud. All the data points that lie outside this cloud will be the multivariate outliers


--> Outliers can impact the results of our analysis and statistical modeling in a drastic way but not everytime because it is helpful sometimes to extract/learn new information from the extreme data also.



-->Outliers are not necessarily a bad thing. These are just observations that are not following the same pattern as the other ones. But it can be the case that an outlier is very interesting. For example, if in a biological experiment, a rat is not dead whereas all others are, then it would be very interesting to understand why. This could lead to new scientific discoveries.  So, it is important to detect outliers


# How to detect outliers:
Our tendency is to use straightforward methods like box plots, histograms and scatter-plots to detect outliers. But dedicated outlier detection algorithms are extremely valuable in fields which process large amounts of data and require a means to perform pattern recognition in larger datasets.

Applications like fraud detection in finance and intrusion detection in network security require intensive and accurate techniques to detect outliers. Can you imagine how embarrassing it would be if you detected an outlier and it turned out to be genuine?

The PyOD library can step in to bridge this gap. Let’s see what it’s all about
## Installation

Yue Zhao, Zain Nasrullah, and Zheng Li designed and implemented the PyOD library.

PyOD is a scalable Python toolkit for detecting outliers in multivariate data. It provides access to around 20 outlier detection algorithms under a single well-documented API.

```
pip install pyod 
pip install --upgrade pyod  # to make sure that the latest version is installed!t
```
    
# Project:
### Aim:
 Health anamoly detection is to detect the anamoly or unusual from the given Health/medical data.
so,here we need to find the Best algorithm to detect anamoly from the given multivariate health data.


we know that to detect this anamoly/outliers from the data we use the pyod library.
pyod library is capable of running multiple outliers detecting algorithms upto 20.

## Outliers detection algorithms:

There are n number of algorithms. but here we are considering four types of outliers detection algorithms:

They are:
### Linear Models
 - Principal Component Analysis(PCA)
 - One Class - SupportVectorMachine(OCSVM)
 - Minimum Covariance Determinant(MCD)

### Proximity Models
 - Local Outlier Factor(LCF)
 - Cluster Based Local Outlier Factor(CBLOF)
 - K Nearest Neighbor(KNN)
 - Histogram Based Outlier Detection(HBOs)
 
### Probability Models
- Angle Based Object Detection(ABOD)

### Ensemble outliers
- Isolation Forest(IForest)
- Feature Bagging

# Import Packages
 - Import required python Packages
 - Import required pyod Models
 - Import required metric packages 

# perform operations:

### 1) define data files, read x & y
 - load all multiple health data's in matfile_list
 - check X and y values shapes and data types 
### 2) create empty dataframe columns and tables:
 - df_columns
 - roc performance evaluation table
 - precision n scores performance evaluation table
 - Time Dataframe

### 3) Loading and building all matfiles
 - import time and set randomstate
 - set for loop to traverse each data in matfile_list
 - join the path of real data dictionary and just named files in matfile_list
 - define X and Y values and flatten the y values with ravel.
 - set the outliers fraction. You can set the value of the outlier fraction according to your problem and your understanding of the data. for example, if I want to detect 5% observations that are not similar to the rest of the data. So, I’m going to set the value of outlier fraction as 0.05.
 - outliers fractions setted by considering the number of nonzero values in the y divided by the len of the y.
 - construct the containers for saving results like roc_list, prn_list,time_list
 - split the data
 - normalize the independent values
 - building models in dict form
 = print time_df, roc_df,prn_df.

## Conclusion:
 The best algorithm is considered mostly which gives the maximum precision and roc_auc score as well as minimum time duration for detecting the outliers/anamoly in the data.



## Acknowledgements

 - [PYOD analyticsvidhya](https://www.analyticsvidhya.com/blog/2019/02/outlier-detection-python-pyod/)

