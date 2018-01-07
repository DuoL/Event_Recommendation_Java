# Titan

This is an interactive webpage for users to search and get recommendations.

## What I used
Used RESTful API to handle HTTP request and response  
Front end :AJAX technology, CSS, HTML, JavaScript  
Back end: TicketMaster, relational database MySQL, NoSQL MongoDB  
Remote Server: EC2(Currently closed because of breaching the free tier limit)  
Local Server: Apache tomcat 9.0.1  

### OOD Pattern 

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
