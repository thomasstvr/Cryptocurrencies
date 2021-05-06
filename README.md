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


