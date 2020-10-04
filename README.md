Challenge Overview



We use unsupervised learning to analyze crytocurrency market trade data. I report which cryptocurrencies are trading on the market and cryptocurrencies classification for future groupings to povide potential investments. I followed the following process: Cleaned up data for maching learning, used unsupervised learning, used clustering algorithm to assist in investment advice and lastly used data visualization to share the findings.


Objectives
Prepare data for dimensions reduction with PCA and clustering using K-means.
Reduce data dimensions using PCA algorithms from sklearn.
Predict clusters from cryptocurrencies data using the K-means algorithm form sklearn.
Present results by creating plots and data tables


Challenge Summary
Data Preprocessing:
We are provided a cryptocurrency CSV file and breakdown the data into a computer legible form. The data is sourced from CryptoCompare

The data is placed into a Pandas DataFrame named “crypto_df” with the following process to pull key data fields and information:

Remove cryptocurrencies which don't trade, Remove cryptocurrencies which don’t have a defined algorithm, Remove the "IsTrading" column, Remove cryptocurrencies with at least one null value, Remove cryptocurrencies without minded coins, Store all cryptocurrencies names on a DataFramed named coins_name, and use the crypto_df.index as the index for this new DataFrame, Remove the "CoinName" column, Create variables for all of the text features and store the resulting data on a DataFrame named X, Use the StandardScaler from sklearn to standardize all of the data from the X DataFrame, Reducing Data Dimensions Using PCA, We used the PCA algorithm from sklearn to reduce the dimensions of the X DataFrame down to three principal components.

Once we had reduced the data dimensions, we created a DataFrame named “pcs_df” that includes the following columns:PC 1, PC 2, PC 3


The crypto_df.index is used as the index for the new DataFrame.

Clustering Cryptocurrencies Using K-means
We used the KMeans algorithm from sklearn to cluster the cryptocurrencies using the PCA data.

We created an elbow curve to find the best value for K, and use the pcs_df DataFrame.
Once we defined the best value for K, we ran the K-means algorithm to predict the K clusters for the cryptocurrencies’ data. We Used the pcs_df to run the K-means algorithm.
We Created a new DataFrame named “clustered_df,” which includes the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class.


Visualizing Results
We created data visualizations to present the final results.

We created a 3D scatter plot using Plotly Express to plot the clusters using the clustered_df DataFrame. You should include the following parameters on the plot: hover_name="CoinName" and hover_data=["Algorithm"] to show this additional info on each data point.
We Used hvplot.table to create a data table with all the current tradeable cryptocurrencies. The table has the following columns: CoinName, Algorithm, ProofType, TotalCoinSupply, TotalCoinsMined, and Class.
We created a scatter plot using hvplot.scatter to present the clustered data about cryptocurrencies having x="TotalCoinsMined" and y="TotalCoinSupply" to contrast the number of available coins versus the total number of mined coins. Use the hover_cols=["CoinName"] parameter to include the cryptocurrency name on each data point.
