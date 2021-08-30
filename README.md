# stock trend forecast project
[Presentation](https://github.com/naumushv/stock-forecast-master/blob/main/Final%20Defence.pdf
) | [Paper](https://github.com/naumushv/stock-forecast-master/blob/main/Stock%20market%20prediction%20model%20based%20on%20deep%20learning%20algorithms.pdf)

This project was created as final defence 2021 graduation year. Following descriptions will unleash some details, how it's done.

In this paper, a neural network project will be presented that predicts the behavior of stock prices of 9 American companies over the last 7-13 years. These companies are Boeing, Cisco,Goldman Sachs, IBM, Intel corp., Coca cola, Microsoft, Verizon, Walmart. Python was chosen as the programming language

Complete name of the project:
### Stock Price Trend Forecasting Using News Analysis based on Deep Learning Methods

Modern traiding is hard and it require usage of more and more complicated tools. New tools, such machine learning, deep learning techniques emerge and seem extremely perspective. 
Many parties participate in stock market operations, including hedge funds, investment funds, retirement funds. Investment bankers can make some nice profits on this operations, but also they can lose a lot of money. Companies can predicts their growths rates and raise money using stock market. In order for different parties to make more educated decisions, such tools and such projects as this one can be helpful. 
Different sources and researches show that news highly correlate to direction of market movements, especially when it comes to press releases. Financial news conveys important information, however market is volatile and hard to predict, perhaps sentimental analysis may help. 
Main objectives are: 
1. Explore machine learning tools possibilities in stock market trend line prediction domain
2. Check the hypothesis:
  - Model using several variables, including sentiment based on news, gives more accurate predictions than a model that does not use only stock price data
  - Check efficient market hypothesis

##### Data flow 
![Data flow](https://raw.githubusercontent.com/naumushv/stock-forecast-master/main/Data%20flow.png)

In flow different headlines goes in, then using different sentiment mining tools we get final dataset with sentiments that match to each news header. Then this data concatenated with stock volume data, some data rows with absent volume or sentiment deleted. No prediction or smoothing techniques used at this point. Then different models serve to produce meaningful predictions.

##### Proposed architecture

![image](https://user-images.githubusercontent.com/30201843/131269433-1adb6b2f-dbf2-428d-868f-f4e3225c68fb.png)

We have two different types of models: with sentiment information and without.
We have two different sources of data: stocks news and stocks prices volumes. 
When it comes to stocks news, we have 2 different approaches to mining a sentiment: through NLTK - NLC Vider set of tools and second appraoch is to create our own model pretrained based on twitts from dataset sentiment140 with 1.6 million twitts. In both cases main objective is to create column or columns that represents sentiment estimation between 0 and 1. We consider this as main feature.
Then models using this sentiments will be computed and models without sentiments will be computed.
Winner will be defined based on 4 metrics: MAE, MSE, RMSE, MAPE. All complete details available in paper.

##### Results

![image](https://raw.githubusercontent.com/naumushv/stock-forecast-master/main/Final%20results.png)

As it can be seen, two multivariate models represent results with sentimental data. From this plot, it's hard to make decisive conclusion which model is the best, but it's actually possible to make conclusion that models with more sentimental data from headlines not giving more accurate predictions. Hypothesis rejected.
