# LSTM-stock
Created an LSTM for stock prediction in python

In this project, we first created a classification model in sk-learn to predict whether stock data would go up or down for one day based on historical data. Then, we created a LSTM model that would allow us to predict what the stock price would be for an “user-selected” arbitrary number of days. We tended to train our data around predicting for 1 month in advance. In general, we primarily trained exclusively on historical equity price data. One of the issues that primarily came up when attempting to add features was the accessibility of financial information. Many of the data sources only contained historical equity price data for free. To access any other information, such as P/E ratios, EPS ratios, etc..., you needed to pay for premium subscriptions. As a result, we were unable to access relevant financial information for the time period we were using in order to add the features that we wanted.

# What went well:
Before normalizing because of the vairiaiton of the price in the stocks we chose, the model was doing a poor job at predicting 
the future price (Error ~ 200) However, when we normalized between 0 and 1, it allowed us to make meaningful predictions based on the training and test data and reduce MSE to below 1.

# What went poorly:
When attempting to add features, we needed to make the 1-D array (that originally just contained the mid-price) into a 2-D array that contained  the mid-price, P/E ratios, EPS, etc... That being said, when trying to make this implementation, we could not get the 2-D array work with our batching function, as well as the way trainng and test data were converted into tensor objects.

# What would we do future:
- Adding features and understanding how we could convert the test data into a 2-Da rray
- Changing the parameters for the batching data, to ensure that bathc data couldn't overlap
  - This error presented itself when the loss on the training data was higher than the tests data
