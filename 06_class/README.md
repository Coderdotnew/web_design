# JavaScript
JavaScript is the programming language of HTML and the Web. It allows you to animate, manipulate, move, access, render the HTML elements of a webpage. JavaScript is referred to as the programming language of the web because it is an object-oriented language like Ruby or Python, but was created specifically to be used in the *front-end* of a web application. 

If you've ever been impressed by a loading screen, auto-scrolling, elements popping up and hiding, or even snowflakes falling on a screen, we have JavaScript to thank for that. 

![1](https://github.com/Coderdotnew/web_design/blob/master/gifs/thankyou.gif)
Thank you JavaScript!

# jQuery
JavaScript can take many years to master. There are many syntax rules, computer science principles and foundations, and understanding of frameworks. That's where jQuery comes in handy.

jQuery is a fun, feature-rich JavaScript library. A library is a collection of pre-written code with various events and commands you can call upon to use on your own webpage. 

## jQuery Syntax
The syntax is written specifically to grab HTML elements and performing an **action** on said element.

Basic syntax is: **$(HTML selector).action()
- A $ sign defines/accesses the jQuery library
- A (HTML selector) is used to "query" (or find) specific HTML elements
- a jQuery action() is a function performed on the element(s)

Let's take a look at an example all together:
```javascript
$(document).ready(function(){
    $("p").click(function(){
        $("p").hide();
    });
});
```
There are 3 important lines here...
1. The first line `$(document).ready(function)()` prepares the entire page, or the document, to load entirely. It is important for the page to load entirely before any jQuery events occur because if the page loads slowly then an action may occur before the page has even loaded!
2. `$("p").click(function()` commands the HTML element, a paragraph tag to execute a function when it is clicked. 
  - Clicking is an event. Other events include double click, keyup, hover, load, scroll, mouse enter, mouse leave, and others. 
3. ` $("p").hide();` is the action. In this case, the paragraph tag will hide when it is clicked!

# jQuery In HTML
Now let's combine our jQuery with our HTML. Similar to how we linked CSS in our `<head>` tag, we will do the same with jQuery.
```html
<!DOCTYPE html>
<html>
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
    $("p").click(function(){
        $("p").hide();
    });
});
</script>
</head>
<body>
    <p>If you click on this paragraph, I will disappear because I am a paragraph tag!.</p>
    <p>Or this one!</p>
    <h1>But not this one because this is not a paragraph tag!</h1>
</body>
</html>
```
Notice the `<script src >` and the `<script>` tags are both in the head. All jQuery requests must go in the head tag or in a separate file reserved for JavaScript (similar to how CSS can go inside a `<style>` tag or in a CSS file.
- In this example, the paragraph tag is the targeted element to be clicked. 
- Only paragraph tags will fade because hte hide function is called only on paragraph tags.
- However, it does not apply to the header tag because that is not a paragraph tag!

Here's another example.
```html
<!DOCTYPE html>
<html>
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
    $("button").click(function(){
        $(".box1").fadeIn();
        $(".box2").fadeIn(1500);
        $(".box3").fadeIn(3000);
    });
});
</script>
</head>
<body>
  <p>Clicking a button to fadeIn numerous boxes.</p>
  <button>Click to fade in boxes</button><br><br>
    <div class="box1" style="width:100px;height:100px;display:none;background-color:red;"></div><br>
    <div class="box2" style="width:100px;height:100px;display:none;background-color:green;"></div><br>
    <div class="box3" style="width:100px;height:100px;display:none;background-color:blue;"></div>
</body>
</html>
```
This one looks much tougher, but it's not!

In this case, the click event is called only on the button element. Upon clicking the button element, each box div fades in at different speeds.
- The higher the number, the slower the fade in. 
- Notice `fadeIn()` is called directly on each div class to be as specific as possible.

Use the following list of events and actions to animate your HTML elements

### Events
- .click
- .dblclick
- .keypress
- .hover
- .load
- .scroll

### jQuery Actions/Effects
- .hide()
- .show()
- .fadeIn() 
- .fadeOut() 
- .slideDown()
- .slideUp()
  - All of the above can take a number in milliseconds, the higher the slower (i.e. `.slideDown(5000)`)
- .animate()
  - Animate takes in parameters as well as speed. (i.e. `.animate({left: '250px'}, 5000)`)

##### .slideDown Example  

```html
<!-- slideDown example -->
<!DOCTYPE html>
<html>
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script> 
$(document).ready(function(){
    $(".top").click(function(){
        $(".bottom").slideDown("slow");
    });
});
</script>
 
<style> 
.top {
    padding: 5px;
    text-align: center;
    border: solid 1px black;
}

.bottom {
    padding: 50px;
    display: none;
    border: solid 1px black;
    text-align: center;
}
</style>
</head>
<body>
 
  <div class="top">Click to slide down panel</div>
  <div class="bottom">Hello world!</div>

</body>
</html>
```
##### .animate Example  

```html
<!-- animate example -->
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script> 
$(document).ready(function(){
    $("button").click(function(){
        $("div").animate({left: '250px'}, 5000);
    });
});
</script> 
</head>
<body>

<button>Click here to move the box!</button>

<p>By default, HTML elements stay in place. We learned about CSS animation, jQuery provides another way to animate!</p>

<div style="background:gray;height:100px;width:100px;position:absolute;"></div>

</body>
</html>
```

# jQuery Plugins
jQuery plugins are typically pre-written jQuery functions that can add awesome features to your webpage. Plugins usually have pretty complex JavaScript attached to them so the good news is as the developer, you simply need to copy and paste the JavaScript and then customize the jQuery function calls to your code!
