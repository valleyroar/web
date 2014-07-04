## Animating with JavaScript

We took simple sets of elements like `span`s:
```
<span class="glyphicon glyphicon-star"></span>
<span class="glyphicon glyphicon-star"></span>
<span class="glyphicon glyphicon-star"></span>
<span class="glyphicon glyphicon-star"></span>
<span class="glyphicon glyphicon-star"></span>
```

and gave them ID's:
```
<span id="star1" class="glyphicon glyphicon-star"></span>
<span id="star2" class="glyphicon glyphicon-star"></span>
<span id="star3" class="glyphicon glyphicon-star"></span>
<span id="star4" class="glyphicon glyphicon-star"></span>
<span id="star5" class="glyphicon glyphicon-star"></span>
```

Then wrote some JavaScript. To start, we made a `script` element:
```html
<script type="text/javascript">
  // JavaScript goes here
</script>
```

Then we made some JavaScript functions to change the star's color:
```javascript
function give1star() {
  $('#star1').css('color', 'yellow');
  $('#star2').css('color', 'gray');
  $('#star3').css('color', 'gray');
  $('#star4').css('color', 'gray');
  $('#star5').css('color', 'gray');
}
function give2stars() {
  $('#star1').css('color', 'yellow');
  $('#star2').css('color', 'yellow');
  $('#star3').css('color', 'gray');
  $('#star4').css('color', 'gray');
  $('#star5').css('color', 'gray');
}
function give3stars() {
  $('#star1').css('color', 'yellow');
  $('#star2').css('color', 'yellow');
  $('#star3').css('color', 'yellow');
  $('#star4').css('color', 'gray');
  $('#star5').css('color', 'gray');
}
function give4stars() {
  $('#star1').css('color', 'yellow');
  $('#star2').css('color', 'yellow');
  $('#star3').css('color', 'yellow');
  $('#star4').css('color', 'yellow');
  $('#star5').css('color', 'gray');
}
function give5stars() {
  $('#star1').css('color', 'yellow');
  $('#star2').css('color', 'yellow');
  $('#star3').css('color', 'yellow');
  $('#star4').css('color', 'yellow');
  $('#star5').css('color', 'yellow');
}
```

And finally we hooked it all together:
```javascript
$('#star1').click( give1star );
$('#star2').click( give2stars );
$('#star3').click( give3stars );
$('#star4').click( give4stars );
$('#star5').click( give5stars );
```

**This is a bad way to code!!** But it's important that you see how to hack something together to work. JQuery is a beautiful thing though, and it provides a great way to deal with elements in a smarter way. Read on to find out how.

## The non-hacked way

In case you're wondering how to do this the non-hacky way, start by putting your stars in a containing element:
```html
<div class="stars">
  <span class="glyphicon glyphicon-star"></span>
  <span class="glyphicon glyphicon-star"></span>
  <span class="glyphicon glyphicon-star"></span>
  <span class="glyphicon glyphicon-star"></span>
  <span class="glyphicon glyphicon-star"></span>
</div>
```

Then use the `.each` function to iterate over them with jQuery. I tried my best to explain each step below, but the best way to understand this code is to read more about jQuery through [Codecademy](http://codecademy.com) and practicing writing more complex functionality.
```javascript
// For every span within a .star container
    $('.stars span').each(
      // Do this function, which inputs the index of the star
      function(index) {
        // Get the parent element (the .star element)
        var p = $(this).parent();
        // Whenever this star is hovered over
        $(this).hover(function() {
            // Get the child elements
            var elems = p.children('span');
            // Loop through the resulting list
            for (var i = 0 ; i < 5 ; i++) {
                // If the index of this star is less than or equal to the index of the star that
                // triggered this code, then make it yellow
                if (i <= index) {
                    $(elems[i]).css('color', 'yellow');    
                }
                // Otherwise, make it gray
                else {
                    $(elems[i]).css('color', 'gray'); 
                }
            }
        });
      }
    );
```
