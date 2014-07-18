```javascript
var firebase = new Firebase("https://schiza.firebaseio.com/");

firebase.on("child_added", function (data) {
	$("#videos").append( toHTML(data.val()) );
});
$('#submit').click(function () {
	embed = toEmbed($("#input").val());
	if (embed) {
		console.log("valid");
		firebase.push({
			url: $('#input').val()
		});
	} else {
		console.log("not valid");
	}
});
function toHTML(obj) {
	return $("<div></div>").attr('id','video').append(
				$("<iframe></iframe>", {
					width: 247,
					height: 200,
					src: obj.url,
					frameborder: 0
				})
			);
}

function toEmbed(url) {
	var videoid = url.match(/(?:https?:\/{2})?(?:w{3}\.)?youtu(?:be)?\.(?:com|be)(?:\/watch\?v=|\/)([^\s&]+)/);
	if(videoid != null) {
	   return "http://www.youtube.com/embed/" + videoid[1];
	} else { 
	    return false;
	}
}
```
