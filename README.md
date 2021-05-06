# Cryptocurrencies
In this repository, I have preprocessed a data set of cryptocurrencies, reduced its dimensions using Principal Component Analysis (PCA), sorted the data into clusters using K-Means then visualized the data with both 2 and 3D scatter plots. 

## Results
First, the data had to be processed to cleanse it of any null values, currencies that are not currently being traded and to drop columns which do not contribute to the story being told by the data (such as CoinName). 

![]( https://github.com/thomasstvr/Cryptocurrencies/blob/main/Resources/working_crypto_df.png)

Once this had been accomplished the data could then be transformed to purely numerical values. To accomplish this, pandas.get_dummies was employed. This function takes string values and breaks them up into new columns which read either 0 (False) or 1 (True) so that the data can be scaled.

After scaling, PCA is then applied to the data to reduce it from 100 to 3 columns. This allows the machine learning algorithm to perform its function quicker since there is less to parse through.

![]( https://github.com/thomasstvr/Cryptocurrencies/blob/main/Resources/pcs_df.png)

This was then used in an elbow curve to determine the best number of clusters to use in a K-Means clustering algorithm.

![]( https://github.com/thomasstvr/Cryptocurrencies/blob/main/Resources/ElbowCurve.png)

You can clearly see the slope of the curve is greatly reduced at a cluster count of 4. This means that 4 clusters will allow the K-Means algorithm to be of best fit to our data.

With the class information from the K-Means model, the data was then reassembled into a new dataframe. 

![]( https://github.com/thomasstvr/Cryptocurrencies/blob/main/Resources/clustered_df.png)

With this new column breaking up the data, it was then plotted on a 3D scatter plot as well as made into an easy to read table.

![]( https://github.com/thomasstvr/Cryptocurrencies/blob/main/Resources/3DPlot.png)

![]( https://github.com/thomasstvr/Cryptocurrencies/blob/main/Resources/table.png)

Now the ‘TotalCoinSupply’ and ‘TotalCoinsMined’ columns were scaled using sklearn’s MinMaxScaler. This is done so that the relative values of these columns do not throw off the data by carrying more weight from larger values. With this newly scaled data ‘TotalCoinSupply’ was plotted against ‘TotalCoinsMined’.

![]( https://github.com/thomasstvr/Cryptocurrencies/blob/main/Resources/2DPlot.png)

## Summary 

In conclusion, data sets with large amounts of features can be represented with much less features using PCA all while not losing any of the information represented by the original data set. K-Means machine learning can be used to find trends in the data and form clusters of similar data points all without being trained. 
