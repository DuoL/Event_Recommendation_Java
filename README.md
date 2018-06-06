# Event recommendation system called 'Titan'
This web system has two main functions:  
	1. Find events around a user's geolocation within 50 miles;  
	2. Recommend events based on a user's favorites  

## WebPages [link](https://github.com/DuoL/Event_Recommendation_Java/blob/master/WebContent/)
There are only a few pages:
1. LoginPage
2. FrontPage
3. FavoritePage
4. RecommendPage  

## Database [link](https://github.com/DuoL/Event_Recommendation_Java/tree/master/src/db)
I used two kinds of DB   
	1. MySQL (for local database test)  
	2. MongoDB (extensible for distributed system test))


## Algorithm [link](https://github.com/DuoL/Event_Recommendation_Java/tree/master/src/algorithm)
1. Online: I've used content-based recommendation algorithm to deal with not too much users at the very beginning.  
2. Offline:  
	2.1 Purify Algorithm: clean the data and format them into a JSON file  
	2.2 Find Peak: find the right time for us to do data analysis(MapReduce) when offline  


## Items
Items will be based on the data we get from TicketMaster API  
So in a case there could be some attributes missing, we need a builder pattern to avoid creating so much constructors  

## External API
Here I used TicketMaster API, but this system is also extensible for other recommendations like Yelp API or NY times API
So Here I've used Factory pattern to make the API switchable for easy change in the future

## RPC 
Java Servlets to handle different HTTP request
[Test the servlets and deploy it on Amazon EC2](https://github.com/DuoL/Event_Recommendation_Java/tree/master/src/rpc)

## Dataflow 
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/DataFlow.JPG)  
## Programming environment
 Platform: Eclipse Oxygen   
 Local Server: Tomcat 9.0.1  
 Remote Server: Amazon EC2  
 Back-end language: Java 8  
 Front-end language: CSS, HTML5, JavaScript    
 API: TicketMaster API, extensible with different geo-based API like Yelp or New York Times    
 Database: MySQL, MongoDB (this is used to make a MapReduce simulation on distributed system)  
 Test Tools: JMeter 4.0, Postman  

## Authors

* **Duo Liu** 

## License
This project is licensed under the LaiOffer License 
