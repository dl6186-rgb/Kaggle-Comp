# Kaggle-Comp
Kaggle Competition Project Code - Jay and Derick

Predicting House Prices:

How to run:
1. open in Google Colab
2. download train and test files from kaggle into your google drive, make sure that they're labeled as "test.csv" and "train.csv" so that when your drive is linked, the right files are opened and rest of code works smoothly
3. run code from top to bottom

Approach:
1. Dropped columns with majority of their values missing as filling in too many of the values with a median or something else along those lines would bias the data too much
2. Filled in rest of columns with missing values either with a 'None' (for columns like basement quality when the house is missing that value because they don't have a basement), the median value (for columns like garage year built that can't be zero or none because it'll skew the data way too much for a house that just doesn't have a garage) , or zero (for columns like Masonry veneer area where if a house doesn't have one, it makes sense that the area would be 0).
3. Changed columns that had sequential orders like basement quality into numbers that were ranked using ordinal encoder. Treated none as being worse than poor becaues assumed that having a poor basement is still better than having no basement.
4. Changed rest of categorical columns into numbers using onehot encoder.
5. Made sure test and train data were transformed in same manner and then used regression to come up with a "submissions.csv" that contains all predicted house prices.

