# Event recommendation system called 'Titan'
This web system is to find interesting events around user and provide recommendations for users based on their favorite


## Programming environment
Platform: Eclipse Oxygen  
Local Server: Tomcat 9.0.1   
Remote Server: Amazon EC2  
Back-end language: Java 8  
Front-end language: CSS, HTML5, JavaScript    
API: TicketMaster API, extensible with different geo-based API like Yelp or New York Times    
Database: MySQL, MongoDB (this is used to make a MapReduce simulation on distributed system)  
Test Tools: JMeter 4.0, Postman  

## OOD Pattern 

Builder pattern for Events (Because we might add more features in the future)  
Factory pattern for switching Database

### Recommendation Algorithm

First of all, this webpage might have few users at the very beginning so called 'cold start'.  
We only have to use a content-based algorithm: which means we just need to find the common part between users.

## Running the tests

I used JMeter to figure out that by using EC2 server this webpage is able to handle 150 queries per second.
### Break down into end to end tests


## Authors

* **Duo Liu** 


## License

This project is licensed under the LaiOffer License 
