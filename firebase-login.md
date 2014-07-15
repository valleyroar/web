```html
<!DOCTYPE html>
<html>
	<head>
		<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
		<script type="text/javascript" src="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/js/bootstrap.min.js"></script>
		<script type="text/javascript" src="http://cdn.firebase.com/v0/firebase.js"></script>
		<script type="text/javascript" src="https://cdn.firebase.com/js/simple-login/1.4.1/firebase-simple-login.js"></script>
		<link rel="stylesheet" href="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css">
		<link href="http://netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.css" rel="stylesheet">
		<style>
		
		</style>
		<script type="text/javascript">
		var firebase = new Firebase("https://your-firebase-name.firebaseio.com");
		var firebaseLogin = new FirebaseSimpleLogin(firebase, onLogin);
		
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
		
		// Run the setup function when the document is loaded.
		$(document).ready( setup );
		</script>
	</head>
	<body>
	
	</body>
</html>
```
