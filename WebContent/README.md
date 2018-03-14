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
