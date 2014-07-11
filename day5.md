# Firebase login

Here's the template we're going to start with.

```
<!DOCTYPE html>
<html>
	<head>
		<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
		<script type="text/javascript" src="https://netdna.bootstrapcdn.com/bootstrap/3.0.3/js/bootstrap.min.js"></script>
		<script type="text/javascript" src="https://cdn.firebase.com/v0/firebase.js"></script>
		<script type="text/javascript" src="https://cdn.firebase.com/js/simple-login/1.4.1/firebase-simple-login.js"></script>
		<link rel="stylesheet" href="https://netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css">
		<link href="https://netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.css" rel="stylesheet">
		
		<style>
		
		</style>
		
		<script type="text/javascript">
		// Set up Firebase and the login for Firebase
		var firebase = new Firebase("https://your-firebase-name.firebaseio.com");
		var firebaseLogin = new FirebaseSimpleLogin(firebase, onLogin);
		
		// Run the setup function when the document is loaded.
		$(document).ready( setup );
		
		// setup function
		function setup() {
		
		}
		
		function onLogin(error, user) {
			if (error) {
				// Handle the login error.
			}
			else if (user) {
				// Handle the successfully logged in user.
				console.log(user.provider + " - " + user.id);
			}
			else {
				// Handle logged out user.
			}
		}
		</script>
	</head>
	<body>
	
	</body>
</html>
```
