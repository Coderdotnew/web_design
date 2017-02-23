# Animations
CSS3 animations allows animation of most HTML elements without using JavaScript or Flash!

`@keyframes` is the primary tool we will use for CSS3 animations. Think of `@keyframes` as a collection of different animations that can be called on an HTML element. Let's add `@keyframes` to a button.

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <button class="my-button">My Button!</a>
</body>
</html>
```
```css
@keyframes color-change {
    from {background-color: red;}
    to {background-color: yellow;}
}

.my-button {
  border: none;
  width: 100px;
  height: 100px;
  background-color: red;
  -webkit-animation-name: color-change; 
  -webkit-animation-duration: 4s;
  animation-name: color-change;
  animation-duration: 4s;
  animation-iteration-count: infinite;
}

```
We are calling on the `@keyframes` CSS3 rule and have called our rule, `color-change` (which we refer to in the second section of our CSS. 

Here is a table for what the various CSS animation properties.
| Property        | Description |
| ------------- |-------------| 
| @keyframes    | Specifies the animation code |
| animation     | A shorthand property for setting all the animation properties  | 
| animation-delay | Specifies a delay for the start of an animation | 
| animation-direction    | Specifies whether an animation should play in reverse direction or alternate cycles |
| animation-duration     | Specifies how many seconds or milliseconds an animation takes to complete one cycle | 
| animation-fill-mode | Specifies a style for the element when the animation is not playing (when it is finished, or when it has a delay) | 
| animation-iteration-count    | Specifies the number of times an animation should be played |
| animation-name     |Specifies the name of the @keyframes animation | 
| animation-play-state | Specifies whether the animation is running or paused | 
|animation-timing-function | Specifies the speed curve of the animation |

Let's take a look at a slightly more complex animation:
```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <button class="my-button">My Button!</a>
</body>
</html>
```
```css
@keyframes my-button {
    0%   {background-color:red; left:0px; top:0px;}
    25%  {background-color:yellow; left:200px; top:0px;}
    50%  {background-color:blue; left:200px; top:200px;}
    75%  {background-color:green; left:0px; top:200px;}
    100% {background-color:red; left:0px; top:0px;}
}

button {
    width: 100px;
    height: 100px;
    background-color: red;
    position: relative;
    -webkit-animation-name: my-button;
    -webkit-animation-duration: 4s;
    -webkit-animation-iteration-count: infinite;
    animation-name: my-button;
    animation-duration: 4s;
    animation-iteration-count: infinite;
}
```
This time, we've named our animation `my-button` and given it instructions where to move and what color to be at various points during the animation process.

W3Schools has some great [examples](https://www.w3schools.com/css/css3_animations.asp).
## Hover.css
There are tons of libraries we can use code from. Hover.css is a really cool library with lots of button animation options.  

Here is the link with the button demos: [Hover.css](http://ianlunn.github.io/Hover/)

Here is the documentation for each button animation: [Hover.css Documentation](https://github.com/IanLunn/Hover/blob/master/css/hover.css)

Let's do the first animation, `hvr-grow` together.
```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
  <link href="css/hover.css" rel="stylesheet" media="all">
</head>
<body>
  <button class="button hvr-grow">My Button!</a>
</body>
</html>
```
In this case, we need to link to the Hover.css library in our HTML head.  

Also, we've added the necessary class to our button, `button hvr-grow`.
```css
.hvr-grow {
  display: inline-block;
  vertical-align: middle;
  -webkit-transform: perspective(1px) translateZ(0);
  transform: perspective(1px) translateZ(0);
  box-shadow: 0 0 1px transparent;
  -webkit-transition-duration: 0.3s;
  transition-duration: 0.3s;
  -webkit-transition-property: transform;
  transition-property: transform;
}
.hvr-grow:hover, .hvr-grow:focus, .hvr-grow:active {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
```

Now it's time to explore!