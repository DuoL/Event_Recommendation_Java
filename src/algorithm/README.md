### Recommendation Algorithm(Content-based recommendation)
Key Idea: You will like people or things of similar characteristics  
Given item profiles(category, price, etc.) of your favorite, recommend items that are similar to what you liked before.

Reason: When there is not enough data so called cold start, we can use this method generally.
#### Precision and Recall
|    |Human: like    |Human:Unlike|
|----|---------------|------------|
|Algorithm: Recommend    |A    |B    |
|Algorithm: Not Recommend|C    |D    |    

Precision = A / (A + B) means the prob of what a person like among all recommendations  
Recall = A / (A + C) means the prob of correct recommendations  
