# Divs
* Divs are ways to organize your HTML into different sections. Think of divs as separate boxes that group certain chunks of relative code together.
* Any kind of code we have dicussed so far can be put into a div---p, h1, button, etc. This is to keep the code organized, while also creating a layout for the page.
* Here's an example of a simple div:
```html
<div>
    <h1>Hello! I'm inside a div!</h1>
</div>
```
* Div's can be formatted separately, which makes them easier to style and position around the page.
* Remember inheritence? Well it also applies to divs! If we style the element 'div' in CSS, this is considered the *parent element*, because parent elements are containing elements. They are more often than not the tags that are on the outside of other code. The elements that are contained within that parent element are called *child elememts*. These will *inherit* any characteristics from the parent element!
  * In the code snippet above, the div (parent) contains the h1 (child) inside.
  * Below, we see that the font in the div is set to blue. This means that the text "Hello! I'm inside of a div!" will inherit that color, right? Well no, not in this case. Because we have also styled the h1 inside of the div and set the color to pink, it is dominant over the blue value since it is directly styled on the child element.
```css
div {
    color: blue;
    font-family: Arial;
}

h1 {
    color: pink
}
```
* But how can each div tag be styled separately when all of the <div> tags are the same? That's where classes come in.

# Classes
* Classes can be applied to any code so we can style tags individually. Using the same example from above, if we have multiple div tags on our HTML page, then we can use classes to style each one of these tags individually. Classes can also be used to style multiple tags at once, to give them the same characteristics. Let's give the div from above a class:
```html
<div class="text">
    <h1>Hello! I'm inside a div!</h1>
</div>
```
* To give a tag a class, simply add a space then 'class="text"' before closing your opening tag, replacing "text" with any name.
* Now when we style the div, we will address it with it's class name. This is slightly different than styling tags, as we have to add a period before the class name so the browser knows it's a class and not a tag.
* Instead of the CSS from above where we styled the div, we will now change that to the class:
```css
.text {
    color: blue;
    font-family: Arial;
}

h1 {
    color: pink
}
```

Now let's apply what we've learned and add some div's and classes to our webpage!
* We're going to group together some tags together in some separate divs. First off, let's make a div around everything we have in the body of the HTML so far. This will let us control and style everything on the whole page we have created. Let's also add a class to the div and call it "homepage."
```html
<!DOCTYPE html>
<head>
	<title>Personal Website</title>
	<link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="homepage">
    	<h1>Title here</h1>
    	<h3>"Tagline or quote here."</h3>
        <p>Longer paragraphs or descriptions can be inserted inside paragraph tags. This might include a biography, website description, or additional information.</p>

    	<button>Learn More..</button>
    </div>
</body>
</html>
```
* Now we can style just this chunk of code instead of using the body to style it! Because we will be adding more code to this later, we don't want properties like the background on the entire body---we just want them on the homepage!
* In our CSS file, lets move the background and text-align properties so they will be in the div and not the body selector. (We will be styling this through the class name!)
   * We're going to leave the font-family property in the body because we want the whole page to be in the same font. (If you want a specific element to be a differnt font, we can target that element directly. *Inheritence* comes in handy!)
```css
body { 
    font-family: "Arial";
}
.homepage {
    background: url("http://images.summitpost.org/original/272289.jpg");
    text-align: center;
}
h1 {
    color: Cyan;
    font-size: 50px;
}
h3 {
    color: Fuchsia;
    font-size: 30px;
}
p {
    color: White;
    font-size: 20px;
}
button {
    background: transparent;
    border: 2px solid white;
    color: white;
    font-family: "Arial";
}
```
* We're also going to wrap divs separately around the h1, h3, p, and button tags, naming their classes respectfully. (Yes, you can put divs inside of divs!)
```html
<!DOCTYPE html>
<head>
	<title>Personal Website</title>
	<link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="homepage">
        <div class="name-header">
    	    <h1>Title here</h1>
    	</div>
    	<div class="home-tagline">
    	    <h3>"Tagline or quote here."</h3>
    	</div>
    	<div class="home-text">
    	    <p>Longer paragraphs or descriptions can be inserted inside paragraph tags. This might include a biography, website description, or additional information.</p>
    	</div>
    	<div class="home-button">
    	    <button>Learn More..</button>
        </div>
    </div>
</body>
</html>
```
* Like we did before, let's move the properties of the elements we just put into divs, into their new classes.
* Now, we will not style most elements through their tags, but through their div classes. This ensures that the characteristics we give these elements will be specific, so not all p tags will be affected throughout the webpage. 
```css
body { 
    font-family: "Arial";
}
.homepage {
    background: url("http://images.summitpost.org/original/272289.jpg");
    text-align: center;
}
.name-header {
    color: Cyan;
    font-size: 50px;
}
.home-tagline {
    color: Fuchsia;
    font-size: 30px;
}
.home-text {
    color: White;
    font-size: 20px;
}
.home-button {
    background: transparent;
    border: 2px solid white;
    color: white;
    font-family: "Arial";
}
```
* Great! Now that we've organized a bit, let's get back to styling.

Before we get into Responsive design, let's add a small piece of code to our CSS file. This will just make sure that all of these properties are reset before styling them. Without this, there might be some strange white space on your page where the background doesn't fill the entire screen.
* Note: The `*` means that we are applying these properties to *all* elements, not just one speciic tag.
```css
* {
  margin: 0;
  padding: 0;
  border: 0;
  outline: 0;
  font-size: 100%;
  vertical-align: baseline;
  background: transparent;
}
```
# Responsive Design
Responsive design ensures that your webpage will still look the way you want it to under different circumstances---whether that be window size, different browsers, or different devices. This can make the content on your page change size, position, or visibility depending on how you are viewing a page.
#### Background
Let's fix our background since it looks pretty funky. We want our background to cover the whole page so there's some CSS we can add to fix it...
* The following code, `no-repeat center center fixed`, will be added to the end of the background line. This just ensures that the background will cover the entire page while centering and not repeating the image.
* We  also need to enter additional code (bottom four lines), because browsers will read the code slightly different. Not all properties need extra code, but there are some that will be rendered differently depending on the browser used---which is why we need to add code.
```css
.homepage {
    background: url("http://images.summitpost.org/original/272289.jpg") no-repeat center center fixed;
    text-align: center;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
}
```
#### Vmax
This is a very handy value we can use to have the font change size depending on how big or small the window in which you are viewing the page is. This is called a *viewport*, and vmax is considered a viewport unit.
* Vmax is based on the longest side of your viewport---usually horizontal if you are on a computer and vertical if you are on your phone. You can input any number up to 100 as the value for size. Think of the page as being 100 units long (or high depending on viewport). If we set our value to `100vmax`, this means whatever we are sizing will take up the entire page. `50vmax` will take up half of the page, and so on.
* Vmax is a bit confusing at first, but it will become easier after some trial and error. Test out using vmax on your header and see what happens when you resize your browser. Cool huh? Let's change all our font sizes to `vmax` instead of `px`.
```css
.name-header {
    color: Cyan;
    font-size: 6.5vmax;
}
.home-tagline {
    color: Fuchsia;
    font-size: 2vmax;
}
.home-text {
    color: White;
    font-size: 1vmax;
}
```
#### Box Model
Elements of HTML are represented as invisible recatngular boxes. This helps us figure out the dimensions and size of an element.
* There are multiple layers of this box---content, padding, border, and margin.
   * Content contains whatever information is inside this specific element. For example, in the code, <h1>Hello</h1>, "Hello" is the content.
   * Padding is the space between the content and the border of the box. Using CSS we are able to make this space as big or as small as we like. The same goes for margins, though they are on the outside of the border. A margin is the space between different elements.
* This will help us style and place content around the page. Right now all of our text is squished at the top of our page. Using logic from the box model will help us understand how to arrange this in any way we would like.


# Additional Styling
#### Fonts
Sometimes the web safe fonts can get a little boring, and may not be exactly what you were looking for. The good news is that fonts can be imported from the internet, and it's super easy.
* https://fonts.google.com/ is a great source to find just about any font!
* Once you find a font you like, they will give you a code snippet to put on the *very* top of your CSS stylesheet, which should look like so:
```css
@import url(https://fonts.googleapis.com/css?family=Work+Sans:400,200,300,700,500);
```
This let's your browser know where to look for the font in order for it to be displayed on your page. Now that we have this snippet of code, it will allow us to put `'Work Sans'` as the value of `font-family`!
* Let's change the fonts in our CSS file to this imported font.
```css
body {
    font-family: 'Work Sans', sans-serif;
}
```
* Note: putting `sans-serif` after our font is just like having a backup incase a browser does not support imported fonts.

#### Button
We are going to create some padding space within the button, in addition to changing the font family and size.
* Let's add a width to this button using the property `width`
* It is also possible to style different sides of the box separately. For example, we will be changing the padding to be greater on the sides than on top and bottom. To do this we will change the value of the padding to individually change each side: "padding: top right bottom left;" in which the sides will be replaced by pixels. Let's add this to the stylesheet.
  * Go ahead and play around with the sizes and see what works best for you. Try using vmax instead of pixels!
  * Also, we're going to add `margin: 0 auto;` to center this button.
```css
.home-button {
    background: transparent;
    border: 2px solid white;
    padding: 1.5vmax 2vmax 1.5vmax 2vmax;
    margin: 0 auto;
}
```
Starting to come together, right? Now let's change the size, color, and family of the font in the button tag, as it won't inherit the div's properties.
```css
button {
    color: white;
    font-family: 'Work Sans', sans-serif;
    font-size: 1.5vmax;
}
```
#### Margins and Padding
Margins and paddings are very much a lot of trial and error. Until you get pretty experienced with CSS, it's hard to estimate how much margins and padding you need on your page.
* Margins and padding can be set using any of the units of measurement we've talked about so far, (px, vmax) and it can also use percentage. Percentage is pretty self-explanitory--if it's set to 25%, then it will be shifted 25% across the page.
* Since everything is pretty squished together, let's add some padding around the header, tagline, text, and button. Just play around with it until it looks right!
```css
.name-header {
    color: Cyan;
    font-size: 6.5vmax;
    padding: 15px;
}
.home-tagline {
    color: Fuchsia;
    font-size: 2vmax;
    padding: 15px;
}
.home-text {
    color: White;
    font-size: 1vmax;
    padding: 15px;
}
.home-button {
    background: transparent;
    border: 2px solid white;
    width: 15vmax;
    padding: 1.5vmax 2vmax 1.5vmax 2vmax;
    margin: 15px auto;
}
```
* Note: since we already have set padding for the button, we will have to use margins to create space around it. We currently have the margin set to `margin: 0 auto;`, but let's change the 0 to 15. Keep the `auto` at the end! (This ensures that the button will stay centered)

Lastly, let's move everything down the page so it's not stuck at the top. To do this let's add extra padding to the header class. We are only adding padding to this element because it is at the top of the stack of elements and it will push everything down with it when it moves. The property `padding-top` is used to just edit the padding on the top. (Yes, "top" can be interchanged with "right", "left" or "bottom.")
```css
.name-header {
    color: Cyan;
    font-size: 6.5vmax;
    padding: 15px;
    padding-top: 17%;
}
```

Here's all the CSS we have so far:
```css
@import url(https://fonts.googleapis.com/css?family=Work+Sans:400,200,300,700,500);

* {
  margin: 0;
  padding: 0;
  border: 0;
  outline: 0;
  font-size: 100%;
  vertical-align: baseline;
  background: transparent;
}
html, body {
    margin: 0;
    padding: 0;
    height: 100%;
    font-family: 'Work Sans', sans-serif;
}
.homepage {
    background: url("http://images.summitpost.org/original/272289.jpg") no-repeat center center fixed;
    text-align: center;
    height: 100%;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
}
.name-header {
    color: white;
    font-size: 6.5vmax;
    padding: 15px;
    padding-top: 17%;
}
.home-tagline {
    color: white;
    font-size: 2vmax;
    padding: 15px;
}
.home-text {
    color: white;
    font-size: 1vmax;
    padding: 15px;
}
.home-button {
    background: transparent;
    border: 2px solid white;
    width: 15vmax;
    padding: 1.5vmax 2vmax 1.5vmax 2vmax;
    margin: 15px auto;
}
button {
    color: white;
    font-family: 'Work Sans', sans-serif;
    font-size: 1.5vmax;
}
```
Note: all the fonts were changed to `white' to give the page a more streamlined look!
