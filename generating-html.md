A bad way to generate HTML that still works.

```javascript
function toHTML(obj) {
	var html = "";
	html = html + '<div class="col-md-3 portfolio-item">';
	html = html + '<a href="';
	html = html + obj.url;
	html = html + '">';
	html = html + '<img class="img-responsive" src="';
	html = html + obj.url;
	html = html + '">'
	html = html + "</a>";
	html = html + "<p>";
	html = html + obj.text;
	html = html + "</p>";
	html = html + "</div>";
	return html;
}
```

A much better way to generate the same HTML using jQuery.
```javascript
function betterHTML(obj) {
	// entire div
	return $("<div></div>")
	// add classes to my div
	.addClass("col-md-3 portfolio-item")
	// append the a element
	.append( 
		// Make the a element
		$("<a></a>")
		// Set its href attribute to the url
		.attr("href", obj.url)
		// Tell it to append an image element
		.append( 
			// The image element
			$("<img>").attr("src", obj.url) 
		) 
	)
	.append( 
		// A p element containing the text
		$("<p></p>").append(obj.text) 
	);
}
```
