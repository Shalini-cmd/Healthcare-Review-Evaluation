# Healthcare-Review-Evaluation
Application Domain Project<br>
<u>Motivation</u> : On preliminary analysis on the Amazon website, we noticed that very old reviews as old as 2 years old coming at the top of the review panel because they have been there for too long and everytime someone viewed it and considered it helpful, its chances of staying at the top increased. So if the seller improved their performance , chances of it reflecting on the top is rare until the user selects latest reviews, ths negatively hampering customer intent to buy.<br>
  
We decided to create a predictive model to detect helpfulness of a review based on its text content. So that new reviews will get a predicted helpful rating when they are first written and used in the review ranking system before it gets atleast 5 views to reduce the bias caused by improved helpfulness of old reviews because of their duration

### Step 1 Target Variable : Helpfulness Flag
1 - If review is helpful
0 - Not helpful
Rating for every review: Total No. of Votes over total no. of views (atleast 5 views)
If Rating > 0.8 ,flag = 1 , otherwise 0

### Step 2
Removing Stop words like the, this, himself etc using NTLK library
Stemming using Porter Stemmer

### Step 3 Text Feature Generation
Count Vectorizer: Array with word frequency for each review
Tf - idf : Assigning weights for every word based on it’s important in the review corpus

### Step 4 Modeling
For every text vectorization method, we ran 4 models -
- Logistic Regression
- Grid Search Logistic Regression
- Random Forest
- Support Vector Machine<br>
In total, 8 models

### Step 5 Model Evaluation & Selection
Every model was evaluated across -
● Accuracy
● Precision
● Recall
Logistic Regression was selected as the performance was comparable to others ,but much more explainable
