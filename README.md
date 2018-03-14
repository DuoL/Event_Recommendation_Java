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

## Dataflow 
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/DataFlow.JPG)  
### LoginPage  
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/LoginPage.JPG)  
```JavaScript
//Login code  
function login() {
		var username = $('username').value;
		var password = $('password').value;
		password = md5(username + md5(password));
		// The request parameters
		var url = './login';
		var params = 'user_id=' + username + '&password=' + password;
		var req = JSON.stringify({});
		ajax('POST', url + '?' + params, req,
		// successful callback
		function(res) {
			var result = JSON.parse(res);

			// successfully logged in
			if (result.status === 'OK') {
				onSessionValid(result);
			}
		},
		// error
		function() {
			showLoginError();
		});
	}
  ```
### FrontPage  
After login, we can see the events around me within 50miles. These are what we got from TicketMaster API
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/FrontPage.JPG)    

### FavoritePage
You can simply 'favorite' the events and those will be put into your own page
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/FavoritesPage.JPG)  

### RecommendationPage
This system will give you recommendations based on your favorites
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/RecommendationPage.JPG)  

### Database
ER  
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/ER%20model.JPG)  

#### Pattern design (Factory Pattern)
I have a class to support other Database, if we want to change the database to NoSQL like MongoDB, 
we can create another new class MongoDB in the db package and do a similar implementation. So does for TicketMaster API.
Sample code:  

```Java
public class DBConnectionFactory {
	// This should change based on the pipeline.
	private static final String DEFAULT_DB = "mysql";

	// Create a DBConnection based on given db type.
	public static DBConnection getDBConnection(String db) {
		switch (db) {
		case "mysql":
			return null;
		case "mongodb":
			return null;
		// You may try other dbs and add them here.
		default:
			throw new IllegalArgumentException("Invalid db " + db);
		}
	}

	// This is overloading not overriding.
	public static DBConnection getDBConnection() {
		return getDBConnection(DEFAULT_DB);
	}
}
```
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

## Authors

* **Duo Liu** 


## License
This project is licensed under the LaiOffer License 
