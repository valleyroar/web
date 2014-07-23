# Firebase messaging

This is to get Firebase chat set up on a single-page application. In the example below, it assumes you are writing code directly into the page using a `script` element.

First, add the following scripts to your page.
```html
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
<script type="text/javascript" src="https://cdn.firebase.com/js/client/1.0.17/firebase.js"></script>
```

**After the script elements from above**, add in the following starting code. 
```javascript
<script>
$(document).ready( setup );

var firebase;

// Everything you want to do when the page is loaded
function setup() {
	// Make a connection to a Firebase
	firebase = new Firebase("https://[[[ENTER FIREBASE NAME HERE]]].firebaseio.com");
	// When the button is clicked, do the sendData function
	$("button").click( sendData );
	// Whenever new data enters the Firebase, send it to the receiveData function
	firebase.on("child_added", receiveData );
}

function sendData() {
	firebase.push("[[[your message]]]");
}

function receiveData(data) {
	var message = data.val();
	// Do something with the message
}
</script>
```
