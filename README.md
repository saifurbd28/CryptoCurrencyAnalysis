# CryptoCurrencyAnalysis

# Purpose

Create an analysis for the Advisory Services Team at Accountability Accounting company (a prominent investment bank) who is interested in offering a new cryptocurrency investment portfolio for its customers. They’ve asked to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment. Since there is no known category for what cryptocurrencies are better, it has been decided to use an unsupervised learning (i.e., PCA) to find out diffent categories within all data followed by supervised classification (i.e., K-means). 

This project had of 4 deliverables:

    Deliverable 1: Preprocessing the Data for PCA
    Deliverable 2: Reducing Data Dimensions Using PCA
    Deliverable 3: Clustering Cryptocurrencies Using K-means
    Deliverable 4: Visualizing Cryptocurrencies Results

# Results

Files:

    crypto_clustering.ipynb : Jupyter Notebook file with Python Analysis

    crypto_data.csv : data file retrieved from CryptoCompare

## Deliverable 1: Preprocessing the Data for PCA

A. The following five preprocessing steps have been performed on the crypto_df DataFrame:

    1) All cryptocurrencies that are not being traded are removed.
    2) The IsTrading column is dropped.
    3) All the rows that have at least one null value are removed.
    4) All the rows that do not have coins being mined are removed.
    5) The CoinName column is dropped.
 B. A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame.   
    ![Fig1](https://user-images.githubusercontent.com/100442163/177381409-8abfabc3-c38d-4a70-b760-e81f12a33feb.png)

C. The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X.

![fig2](https://user-images.githubusercontent.com/100442163/177381834-61b33142-7030-4d5c-a7bf-a9af7ee63c61.png)

D. The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function. 
E. The dataset was loaded from the source file and transformations were done to prepare the data for PCA.

![fig3](https://user-images.githubusercontent.com/100442163/177382147-8941be0c-ab42-45da-bf88-5267cb3df21e.png)


## Deliverable 2: Reducing Data Dimensions Using PCA
Using the knowledge of how to apply the Principal Component Analysis (PCA) algorithm, I have reduced the dimensions of the DataFrame to three principal components and place these dimensions in a new DataFrame.
![fig4](https://user-images.githubusercontent.com/100442163/177382880-edc45531-2a22-4510-89ad-2481a91c00a8.png)

## Deliverable 3: Clustering Cryptocurrencies Using K-means
Using the knowledge of the K-means algorithm, I have created an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in Deliverable 2. Then, I have run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.
![fig5](https://user-images.githubusercontent.com/100442163/177383530-d2d68f14-99d2-486b-a502-f419b8a6ada6.png)

Created an elbow chart to find the best value for K from the pcs_df dataframe from the previous deliverable.
![fig6](https://user-images.githubusercontent.com/100442163/177383923-bd746426-99b5-4052-b7b8-4a7709403e93.png)

Then I ran the K-means algorith with 4 clusters to predict the clusters for the data. A dataframe with all the data clustered_df was created.

![fig7](https://user-images.githubusercontent.com/100442163/177384166-9233ac49-8116-49b5-8392-dc4d47870f53.png)
