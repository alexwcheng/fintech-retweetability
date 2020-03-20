# Twitter Business

![Title_Slide](/Images/Slides/Title_Slide.png)

#
### Project File Summary

   - <b>[README.md](README.md)</b> - a summary of all contents in this repository.
   - <b>[/Data](/Data)</b> - All data called from the Twitter API.
   - <b>[/Images](/Images)</b> - Exported plots, etc...
   - <b>[/Jupyter_Notebooks](/Jupyter_Notebooks)</b> - All Jupyter Notebooks for this project.
   - <b>[/Project_Prompt](/Project_Prompt)</b> - The prompt for this project.
   - <b>[/Python_Files](/Python_Files)</b> - .py files loaded / imported in the Jupyter Notebooks.
   - <b>[/Final_Presentation](/Final_Presentation)</b> - A non-technical presentation of our project.

#
### Project Members

   - <b>[Alex Cheng](https://github.com/alexwcheng)</b>
   - <b>[Stuart Murphy](https://github.com/thespud56)</b>
   
#
### Project Responsibilities

   -  All project responsibilities were shared equally between <b>[Alex Cheng](https://github.com/alexwcheng)</b> and <b>[Stuart Murphy](https://github.com/thespud56)</b>.

#
### Project Scenario

Our client is a FinTech company looking to scale their customer acquisition efforts. They know that their target market are people who care deeply about their finances, and actively discuss finances in their everyday lives. They are also tech-savvy and are open to trying new digital & mobile experiences when interacting with their money (early adopters). Our client wishes to use their marketing budget wisely. They are aware that the best kind of marketing is 'word of mouth' marketing and want to produce content that will most likely get shared and retweeted by their followers. An example client might be a financial tech company like Alluva with only a few thousand followers, as seen below.

![Fintech_Example_Twitter_User](/Images/Slides/Fintech_Example_Twitter_User.png)

#
### Project Goals

The goal of this project is to help our client identify **the most important attributes** around a tweet and a twitter user that will lead to the most retweets. Our target (dependent variable) is the **number of retweets,** split into 3 classes:
1. 0-100 Retweets
2. 100-1000 Retweets
3. 1000+ Retweets

#
### Data

Our dataset comes from the [Twitter API](https://developer.twitter.com/en/docs/api-reference-index), using 3 endpoints: 
1. Users
2. Tweets
3. Tweet Details (Deets)

We decided on 10 terms targeting Financial Tech (Fintech) that we used to retrieve tweets that are most related to Fintech news, products, and services. We decided to collect up to **5,000 tweets per query term.** Sometimes, the number of results ran out before we reached 5,000 tweets for a particular query term. 

![Fintech_Twitter_Query_Terms](/Images/Slides/Fintech_Twitter_Query_Terms.png)

The data collection process required a large number of API requests via token pagination at 100 results per request. After collecting all of the tweets, the user ids and tweet ids were harvested, and used to request user information and detailed tweet metrics for each collected tweet. Finally, the data was cleaned, transformed, and merged into one dataframe.


### Random Forest Model

### Conclusions

### Future Work

#
### Methodology 


3. Feature Engineering. This includes some exploratory analysis to understand more about our predictors, hot one encode certain categorical variables (text color and user background color), and creating new features to help predictability. Most importantly, we needed to create an independent variable that we could make predictions about. This variable was rewteet 'class', that allowed us to identify if a tweet is highly retweeted (+ 1000), decently retweet (100 - 1000, or poorly retweeted (< 100).

4. Data Preprocessing. With many numerical variables existing on different scales, it is important to standardize them to enable us to model appropriately. We also "Train, Test, Split" our data (80/20 split), which will allow us to train our model sufficiently before making predictions.

5. Model Selection. We decided to use a random forest for our dataset. The primary reason for selecting random forests: i) We are working with lot of columns. ii) Feature importance is a priority. iii) Our dataset is not too large and so computational cost is not overbearing.

6. Train model and hypertune accordingly. Parameters that we hypertuned were max depth, number of estimators, max features, min samples leaf, min samples split, and bootstrapping. We also cross validated our model to ensure our prediction on the traing set wasn't an anomaly.

7. Make a prediction & establish features that were most important in our data.

8. Assess results, make recommendations and topics for further investigation.

9. Create a presentation of our findings for the client.
