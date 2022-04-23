# Clustering of Cryptocurrencies

## Overview

How to divide the vast number of cryptocurrencies available to a limited, more manageable number of groups? For investment banks looking to exapnd into this emerging asset, this is a key question. This analysis will use **unsupervised** machine learning on a dataset of cryptocurrencies and classify them into a few groups according to their features.


### Purpose

The main purpose of this analyses includes the following:

- preprocessing the data for **Principle Component Analysis** (PCA);
- reducing the data dimension using PCA;
- clustering cryptocurrencies using **K-Means**;
- visualizing cryptocurrencies classification results with 2D and 3D scatter plots.

### Resources

- Data souces: crypto_data.csv, CryptoCompare
- Data tools: Python 3.7.6, Jupyter Notebook, sklearn, plotly, hvplot



## Results

### Preprocessing the Data for PCA

In order to perform PCA, the dataset was preprocessed by removing umimportant features and null values. The following image showing a dataframe afetr reading the dataset in pandas DataFrame.

![crypto_df](https://github.com/Nusratnimme/Cryptocurrencies/blob/main/Images/crypto_df.png)

### Reducing Data Dimensions Using PCA

By applying Principal Component Analysis (PCA) algorithm on Standarized features, the **dimensions were reduced** to three principal components.

![pcs_df](https://github.com/Nusratnimme/Cryptocurrencies/blob/main/Images/pcs_df.png)

### Clustering Cryptocurrencies Using K-means - Elbow Curve

An **elbow curve** was used to visualize the decline in **inertia** with increased number of clusters. As can be seen from the image below, the best number of clusters appeared to be 4.
 
![elbow curve](https://github.com/Nusratnimme/Cryptocurrencies/blob/main/Images/Elbow%20Curve.png)

Therefore, 4 clusters were fitted to classify the cryptocurrencies.

### Visualizing Cryptocurrencies Results

#### 3D-Scatter plot with clusters

The 3-D scatter plot above shows the 4 clusters created with PCA and K-means clustering. As can be seen, the clusters are evidently separate from each other. **BitTorrent** stands out as an outlier and the sole member of cluster 2.

![3D plot](https://github.com/Nusratnimme/Cryptocurrencies/blob/main/Images/3D%20plot.png)

#### Tradable Cryptocurrencies Table

The table in the image below shows tradable cryptocurrencies.

![traded table](https://github.com/Nusratnimme/Cryptocurrencies/blob/main/Images/traded%20table.png)

There are **532** tradable cryptocurrencies.

#### 2D-Scatter plot with TotalCoinMined vs TotalCoinSupply

In order to create a 2D-Scatter plot of **TotalCoinMined vs TotalCoinSupply**, a new dataframe was created containing these columns, and **CoinNames** and **Class** columns from the previous dataset.

![plot_df](https://github.com/Nusratnimme/Cryptocurrencies/blob/main/Images/plot_df.png)

The 2D-Scatter plot is shown in the image below.

![2D plot](https://github.com/Nusratnimme/Cryptocurrencies/blob/main/Images/2D%20plot.png)

Similar patterns can be observed in the 2-D plot. BitTorrent appears to be an outlier. There's quite a spread in class 0 as far as their TotalCoinMined and TotalCoinSupply are concerned. The other two clusters are very homogeneous.

## Recommendation

The most serious issue with the dataset is missing values. When missing values were dropped, the number of records fell to 685 from more than 1,000. It should be explored if the missing values can be imputed instead of being dropped.


