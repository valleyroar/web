# Storing data on firebase

```javascript
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
<script type="text/javascript" src="https://cdn.firebase.com/js/client/1.0.17/firebase.js"></script>

<script>
$(document).ready( setup );

var firebase;

// Everything you want to do when the page is loaded
function setup() {
    // Make a connection to a Firebase
    firebase = new Firebase("https://[[[ENTER FIREBASE NAME HERE]]].firebaseio.com");
    // Whenever new data enters the Firebase, send it to the receiveData function
    firebase.on("value", receiveData );
}

function receiveData(data) {
    // Get a JavaScript object
    var obj = data.val();
    // Do something with the object
}
</script>
```
