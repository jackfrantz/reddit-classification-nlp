# Project 3: Reddit API NLP Modeling
***


### Contents
- Problem Statement
- Data Dictionary
- Executive Analysis
- Recommendations

## Problem Statement
In this scenario, I am working on behalf of an advertising agency that is trying to improve the way they target their advertising campaigns by age. Since it is not always possible for them to know the exact age of the individual their ads will be served to, they wanted to know if it was possible to figure out the age group someone fits in based on the way they talk. This could have several benefits, including more accurate ad targeting and preventing an ad from being shown to someone that is too young. To answer this, I will be examining the text included in the posts from subreddits of two different generations. I will be attempting to determine whether it is possible to predict the generational subreddit of the post originated in based on the text included.

## Data Dictionary
This data was sourced directly from the Reddit API. The data included has been scraped from the subreddits [r/GenZ](https://www.reddit.com/r/GenZ/) and [r/Millennials](https://www.reddit.com/r/Millennials/).<br>
<br>

|Feature|Type|Dataset|Description|
|---|---|---|---|
|Title|object|r/GenZ and r/Millennials|Title of the post on it's original subreddit|
|Selftext|object|r/GenZ and r/Millennials|Body of the post on it's original subreddit|
|All Text|object|r/GenZ and r/Millennials|Combined feature of Title and Selftext|
|Subreddit|object|r/GenZ and r/Millennials|Subreddit of origin for the post| 


## Exectutive Analysis
Based on the analysis and models created in this notebook and the Count Vectorizer notebook, I am confident that the Logistic Regression model using Count Vectorizer is the top performing model for our purposes. There are several reasons for that, the first simply being scoring. This model out performed all others with a test score of .79. Even though it appeared to be overfit, the model continued to score higher than any other combination of features.

The second reason is that it's errors are more practical than the other models. It tends to err on the side of classifying as Gen Z. This at least gives us opportunites to advertise, whereas an incorrect classification as Millennial does not. It is better to have a false positive because if the classification is incorrect, at least we were able to get an ad in front of somewhere, whereas with a false negative there is no attempt

Third, it is the most interpretable. If we need to justify our findings to another business team, the logistic regression is more straightforward than the other models. It is easier to see how the data is set up than with Naive Bayes or a TFIDF Vectorization, which will both make simplifications behind the scenes to try and improve performance.

After testing these models, I am recommending that the advertising team move forward with their plan of classifying users by generation based on the text they post, based on this Count Vectorizer Logistic Regression.

## Recommendations
Since we have successfully created a model off of this data, there are several recommendations that can be made. When targeting users based on their posts, use a Count Vectorizer and model with a logistic regression. 

If you wanted to use this model to see if the advertisements you are writing fit the language of the generation you are targeting, you can run your text through the to see how it is categorized. Then target the ads you want to serve to members of Gen Z to the ones whose posts were classified as such. To make this model even stronger, I would recommend collecting new data from more sources like other social media sites. You should also consider running potential advertisements through this model to see if they would match the language of the generation you are advertising to.

There are also ways this model can be modified for different applications in the future. If you wanted to try and flag users that may be too young to use your platform, you could collect new data on a younger generation to train the model on. Any account with language that was categorized as too young could be flagged for review. 