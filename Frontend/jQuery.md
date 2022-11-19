# CDN

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.1/jquery.min.js"></script>
```

# W3Schools Doc

[jQuery Syntax](https://www.w3schools.com/jquery/jquery_syntax.asp)

# jQuery Syntax

The jQuery syntax is tailor-made for **selecting** HTML elements and performing some **action** on the element(s).

Basic syntax is: **$(*selector*).*action*()**

- A $ sign to define/access jQuery
- A (*selector*) to "query (or find)" HTML elements
- A jQuery *action*() to be performed on the element(s)

Examples:

`$(this).hide()` - hides the current element.

`$("p").hide()` - hides all <p> elements.

`$(".test").hide()` - hides all elements with class="test".

`$("#test").hide()` - hides the element with id="test".

## The Document Ready Event

You might have noticed that all jQuery methods in our examples, are inside a document ready event:

```js
$(document).ready(function(){

  // jQuery methods go here...

});
```

This is to prevent any jQuery code from running before the document is finished loading (is ready).

It is good practice to wait for the document to be fully loaded and ready before working with it. This also allows you to have your JavaScript code before the body of your document, in the head section.

Here are some examples of actions that can fail if methods are run before the document is fully loaded:

- Trying to hide an element that is not created yet
- Trying to get the size of an image that is not loaded yet

**Tip:** The jQuery team has also created an even shorter method for the document ready event:

```js
$(function(){

  // jQuery methods go here...

});
```

Use the syntax you prefer. We think that the document ready event is easier to understand when reading the code.

## [jQuery Selectors](https://www.w3schools.com/jquery/jquery_selectors.asp)

jQuery selectors allow you to select and manipulate HTML element(s).

jQuery selectors are used to "find" (or select) HTML elements based on their name, id, classes, types, attributes, values of attributes and much more. It's based on the existing [CSS Selectors](https://www.w3schools.com/cssref/css_selectors.asp), and in addition, it has some own custom selectors.

All selectors in jQuery start with the dollar sign and parentheses: $().

# jQuery Styles Methods

## css()

```javascript
$("p").css("background-color"); //Return a css property
$("p").css("background-color", "yellow"); //Set CSS property
$("p").css({"background-color": "yellow", "font-size": "200%"});
// Set multiple CSS property
```

## Class methods

```js
$("#div1").addClass("important blue");
$("h1, h2, p").removeClass("blue");
$("h1, h2, p").toggleClass("blue");
```

A good practice to separate JS from styling the webpage. 

# Set Content and Attributes

[jQuery Set Content and Attributes](https://www.w3schools.com/jquery/jquery_dom_set.asp)

```js
$("#btn1").click(function(){
  $("#test1").text("Hello world!");
});
$("#btn2").click(function(){
  $("#test2").html("<b>Hello world!</b>");
});
$("#btn3").click(function(){
  $("#test3").val("Dolly Duck");
});
```

```js
 $("button").click(function(){
  $("#w3s").attr("href", "https://www.w3schools.com/jquery/");
});
```

# Event Listener

[jQuery Event Methods](https://www.w3schools.com/jquery/jquery_events.asp)

```js
$("p").click(function(){
  // action goes here!!
});
```

```js
$("button").mouseover(function () {
    $(this).addClass("hover");
})
$("button").mouseout(function () {
    $(this).removeClass("hover");
})
$("button").click(function (event) {
    $("h1").addClass("big");
    console.log(event);
})
$("input").keypress(function (event) {
    console.log(event);
})
$(document).keypress(function (event) {
    console.log(event);
})
```

## The on() Method

The `on()` method attaches one or more event handlers for the selected elements.

```js
$("p").on("click", function(){
  $(this).hide();
});
```

# New elements

- `append()` - Inserts inner HTML content at the end of the content of the selected elements
- `prepend()` - Inserts inner HTML content at the beginning of the content of the selected elements
- `after()` - Inserts content **after the closing tag** of  selected elements
- `before()` - Inserts content **before the opening tag** of the selected elements

# Remove

- `remove()` - Removes the selected element (and its child elements)
- `empty()` - Removes the child elements from the selected element

# Animations

[jQuery Effects - Hide and Show](https://www.w3schools.com/jquery/jquery_hide_show.asp)

## Hide and show

```js
$("#hide").click(function(){
  $("p").hide();
});

$("#show").click(function(){
  $("p").show();
});

$("button").click(function(){
$("p").toggle();
});
```

## Fade

- `fadeIn()`
- `fadeOut()`
- `fadeToggle()`
- `fadeTo()`

The jQuery `fadeTo()` method allows fading to a given opacity (value between 0 and 1).

**Syntax:**

```js
$(selector).fadeTo(speed,opacity,callback);
```

The required speed parameter specifies the duration of the effect. It can take the following values: "slow", "fast", or milliseconds.

The required opacity parameter in the `fadeTo()` method specifies fading to a given opacity (value between 0 and 1).

The optional callback parameter is a function to be executed after the function completes.

The following example demonstrates the `fadeTo()` method with different parameters:

```js
$("button").click(function(){
  $("#div1").fadeTo("slow", 0.15);
  $("#div2").fadeTo("slow", 0.4);
  $("#div3").fadeTo("slow", 0.7);
});
```

## Sliding

- `slideDown()`
- `slideUp()`
- `slideToggle()`

```js
$(selector).slideDown(speed,callback);
```

The optional speed parameter specifies the duration of the effect. It can take the following values: "slow", "fast", or milliseconds.

The optional callback parameter is a function to be executed after the sliding completes.

## Animate

[jQuery Effects - Animation](https://www.w3schools.com/jquery/jquery_animate.asp)

```js
$(selector).animate({params},speed,callback);
```

```js
$("button").click(function(){
  $("div").animate({
    left: '250px',
    opacity: '0.5',
    height: '150px',
    width: '150px'
  });
}); 
```

You can't use animate to change color. 

It only applicable to **numerical CSS value.**

## Chaining

```js
$("#p1").css("color", "red").slideUp(2000).slideDown(2000);
```

All jQuery function returns itself.
