# Day 1 of web development

### Here's what you should do at home!
[Learn CSS](https://techlab.education/learn/css/)


### Things we used today

- Sublime Text 2 [link](http://www.sublimetext.com/)
- Codecademy [link](http://codecademy.com)
- codepen [link](http://codepen.io)
- jQuery [link](http://jquery.com)
- Firebase [link](https://firebase.com)

### Code from today

```
<html>
	<head>
		<script type='text/javascript' src='https://cdn.firebase.com/js/client/1.0.17/firebase.js'></script>
		<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>

		<script type="text/javascript">
		var data;
		$(document).ready( setup );

		function setup() {
			data = new Firebase("https://bestappever.firebaseio.com");
			// Whenever I get new data, do the onMessage function
			data.on('child_added', onMessage);
			// When I click the button do the when clicked function
			$('button').click(whenClicked);
		}
		function whenClicked() {
			var text;	// Make a variable
			text = $('textarea').val(); // Store textarea
			data.push(text); // Push it to Firebase
			// Thank the user for their compliment
			$('textarea').val('Thanks for the compliment!');
		}
		function onMessage(message) {
			// Select the h1 and tell it that your text
			// is whatever came out of the message
			$('h1').text( message.val() );
		}

		</script>


		<style>
		body {
			/* paste background here */
		}
		h1 {
			margin-top:100px;
			/* font color */
			color: green;
			font-size: 60px;
			text-align: center;
		}
		textarea {
			/* width and height */
			margin-left:15%;
			width: 70%;
			height: 50px;
			/* text alignment */
			text-align: center;
			/* remove the border/outline */
			border: none;
			outline: none;
			font-size: 24px;
		}
		button {
			margin-top:20px;
			display: block;
			margin-left: auto;
			margin-right: auto;
			width: 200px;
			height: 80px;
			font-size:30px;
		}
		</style>
	</head>
	<body>
		<h1>You're great for visiting mycompliment website!</h1>
		<textarea>Compliment!</textarea>
		<button>compliment!</button>
	</body>
</html>
```
