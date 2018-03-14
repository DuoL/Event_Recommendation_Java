### Test
Here we used Postman to see if every POST or GET could work well with the servlet  
Use an example to illustrate if we can get user's favorite data  
Step 1: for a user, he needs to favorite some events first so we post a simple item to it like this  
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/PostFavorite.JPG)  
Step 2: request a GET from server to see if it is there  
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/GETFavorite.JPG)

### Deploy on Amazon EC2
Here is what I got from JMeter  

|Number of Users (threads)| Avg. resp. time|Throughput(qps)|
|-------------------------|----------------|---------------|
|100                      |738             |84.7           |
|500                      |2420            |103.4          |
|1000                     |3267            |137.4          |
|1500                     |4497            |150.6          |
|2000                     |6587            |119.9          |
