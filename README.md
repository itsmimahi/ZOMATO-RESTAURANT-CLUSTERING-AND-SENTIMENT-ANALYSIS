## Zomato Restaurant Clustering And Sentiment Analysis

![Zomato-Machine-Learning-1-1024x576](https://user-images.githubusercontent.com/105766113/231358984-9fc85ac0-1213-4a49-85b1-1770ae34904c.jpg)



### Problem Statement:
Zomato is an Indian restaurant aggregator and food delivery start-up founded by Deepinder Goyal and Pankaj Chaddah in 2008. Zomato provides information, menus and user-reviews of restaurants, and also has food delivery options from partner restaurants in select cities. India is quite famous for its diverse multi cuisine available in a large number of restaurants and hotel resorts, which is reminiscent of unity in diversity. Restaurant business in India is always evolving. More Indians are warming up to the idea of eating restaurant food whether by dining outside or getting food delivered. The growing number of restaurants in every state of India has been a motivation to inspect the data to get some insights, interesting facts and figures about the Indian food industry in each city. So, this project focuses on analysing the Zomato restaurant data for each city in India. The Project focuses on Customers and Company, you have to analyze the sentiments of the reviews given by the customer in the data and made some useful conclusion in the form of Visualizations. Also, cluster the zomato restaurants into different segments. The data is vizualized as it becomes easy to analyse data at instant. The Analysis also solve some of the business cases that can directly help the customers finding the Best restaurant in their locality and for the company to grow up and work on the fields they are currently lagging in. This could help in clustering the restaurants into segments. Also the data has valuable information around cuisine and costing which can be used in cost vs. benefit analysis. Data could be used for sentiment analysis. Also the metadata of reviewers can be used for identifying the critics in the industry.





### Data Description:

### Attribute Information:

   * Name : Name of Restaurants
   * Links : URL Links of Restaurants
   * Cost : Per person estimated Cost of dining
   * Collection : Tagging of Restaurants w.r.t. Zomato categories
   * Cuisines : Cuisines served by Restaurants
   * Timings : Restaurant Timings
   
### Zomato Restaurant reviews

   * Restaurant : Name of the Restaurant
   * Reviewer : Name of the Reviewer
   * Review : Review Text
   * Rating : Rating Provided by Reviewer
   * MetaData : Reviewer Metadata - No. of Reviews and followers
   * Time: Date and Time of Review
   * Pictures : No. of pictures posted with review

### Exploratory Data Analysis(Basic)
* For the zomato restaurant metadata there are 105 rows and 6 columns or features, while in review dataset there were 10,000 rows and 7 columns.
  Both the data set does not contain duplicate values.
* There were null values present in both dataset , In the metadata the null values present in collection dataset was converted to ‘Not rated’, while in the review       dataset the dataset containing null values were very few but important features, so in order to avoid inaccuracy these were removed.
* The mean cost of food for the restaurants in zomato is 861.42 rupees.
  Most Common timing of restaurants in zomato are from 11 AM to 11PM.


### Exploratory Data Analysis(Insights)

*  Collage-Hyatt Hyderabad Gachiboli is the most expensive restaurant.
*  Amul and Mohammedia Shawarma are the cheapest restaurant.
*  Most popular cuisine of our dataset is North Indian with 61 restaurants offering it.    
*  Chinese is the second most popular cuisine with 43 restaurants offering it.
*  Majority of restaurants provide three different types of cuisines
*  Only one restaurant provides six different types of cuisines and that restaurant is “Beyond flavours”.
*  Average rating of the restaurants in zomato is 3.6, while median rating is 4 implying our rating column is negatively skewed.
*  Maximum pictures uploaded by a person is 64.
*  More than 75 percentile of people do not upload pictures.
*  Out of all the reviewers, Parijat Ray with 13 reviews was the largest reviewer(in our dataset).
*  Satwinder Singh was the reviewer with most number of followers, he has 13,410 followers, Eat_vth_me was a close second with 13,320 followers.
*  The reviews till 2017 were very less ,from 2018 and 2019 the number of reviews increased exponentially.
*  The count of reviews were higher during the months of May and July and least during the month of June
*  Most of the reviews are posted during weekends(i.e. Saturday and Sunday)
*  The majority of reviews are posted at night from 9 to 11pm.
*  The restaurant with highest average rating from the given dataset is AB’s –Absolute Barbecues with a rating of 4.88

### Summary
Clustering of the dataset was done by k means clustering initially. The number of clusters was found out with the help of elbow curve and Silhouette coefficient method. The optimum number of clusters was found as 6 since it is the point after which elbow gradient stabilises and silhouette coefficient is more. The 6 clusters were formed based on their cost per head. Their cluster distribution was visualised with respect to cost, number of cuisines and name of restaurant. Then hierarchical clustering was done with the number of clusters specified as 6. The number of clusters were taken as 6 as we could use it to compliment our clustering done through K means.

The sentiment analysis of review column is to be done, before doing so the following transformations are done.

  *  Removing urls from dataset
  *  Removing punctuations and special character
  *  Removing emoji pattern from given string
  *  Removing words with length less than or equal to 2.
  *  Lemmatization

Then dataset is split into two: train dataset and test dataset for the classification analysis. Then the text was converted from words into numbers by the process called Vectorization. The vectorizing method used here is Count vectorizer.The vectorized dataset is used here and experimented with various models like Logistic Regression, Naïve Bayes Classifier, XG Boost and Random Forest. Hyper parameter tuning was also done on all of them. The evaluation metrics used here for checking the predicted model accuracy are Accuracy score, recall, precision and F1 score.





### Conclusion :

*    The clustering is done and the restaurants are divided in to 6 different clusters or groups based on the number of cuisines and cost per head.
*    Sometimes people give good rating even when their reviews are bad or negative
*    The Naive Bayes gives the best model for sentimental analysis for the given dataset.
*    The Naive Bayes model gives an accuracy,precision, recall score of 0.92
