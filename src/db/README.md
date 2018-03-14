### ER  
![image](https://github.com/DuoL/Event_Recommendation_Java/blob/master/images/ER%20model.JPG)
### Pattern design (Factory Pattern)
I have a class to support other Database, if we want to change the database to NoSQL like MongoDB, 
we can create another new class MongoDB in the db package and do a similar implementation. 
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
