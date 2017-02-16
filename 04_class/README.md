# Code Along!
* The best way to learn the nuances of HTML and CSS is to follow tutorials and then edit the code snippets so your page responds exactly how you envision. 
* Use the following code snippets to complete your first personal webpage and clean up any parts that are not responding correctly. 

## Page 2
* The second page first and foremost requires a `div` with a class. Let's call the class `info-page`. 
* After adding the HTML, we need to also add the CSS to make sure this div takes up the entire second page.
```HTML
<div class="info-page">
</div>
```
```CSS
/* INFO PAGE */
.info-page {
    height: 100%;
    margin: 0;
    padding: 0;
    background:black;
    text-align:center;
}
```
* There is a black background just to be able to visualize the size and contrast it against the homepage when scrolling down. 
* Also, I want my pictures to be center-justified so there is a `text-align` attribute present.

#### Picture Links
On this page, let's add 6 images, however, each image will be responsive and act as a link to another webpage. 
* For this site, I will have each image be a picture of a city which will link to the city's official web address.
* First, though, we need to create a div to hold each of these images. Let's give it a class called `pic-table`.
```HTML
<div class="info-page">
    <div class="pic-table">
    </div>
</div>
```
* Let's add some simple CSS. First, we need to make sure there is no margin 
* Next, let's add a little padding so the images are directly at the top of the page (I use a % value so it is responsive)
```CSS
.pic-table {
    margin: 0;
    padding-top:10%;
}
```

#### Pictures
Each picture will be contained in a div (duh). 
* Let's further classify the picture div by giving it a class of `pic`.
```HTML
<div class="info-page">
    <div class="pic-table">
        <div class="pic"></div>
        <div class="pic"></div>
        <div class="pic"></div>
        <div class="pic"></div>
        <div class="pic"></div>
        <div class="pic"></div>
    </div>
</div>
```
Perfect! Now for the CSS, we need to do a few special commands to ensure the images are *inline*, evenly spaced, and responsive (meaning they change depending on the size of the screen).
* Let's give each pic div a height of `25vmax` and a width of `25vmax`.
* `vmax` is a responsive value (unlike pixels) that stands for *viewport max*. This means the size changes no matter what direction you shrink or expand the size of the screen in.
  * `vw` is viewport width and `vh` is viewport height. Feel free to see how those respond differently when you alter the screen sizes. 
  * A new attribute is `display`. We will give the display value `inline-block`. This means the elements will lie together in a line and go to the next line if the screen isn't big enough for them all to fit.
  * Lastly, let's give a margin of `1%` so they are slightly spread apart from one another.
```CSS
.pic {
    height: 25vmax;
    width: 25vmax;
    display:inline-block;
    margin: 1%;
}
```

## Picture ID's
Now that each div containing each image shares a class name, we need a method to further classify the image so we can give each div a different image background.  

This is where `id` comes in. `id` is similar to `class` but less important and less useful. Only use when you need to further specific within a class, as we are doing now. 
* Let's give each picture a new id with a number.
```HTML
<a name="info-page"><div class="info-page"></a>
    <div class="pic-table">
        <div class="pic" id="p1"></div>
        <div class="pic" id="p2"></div>
        <div class="pic" id="p3"></div>
        <div class="pic" id="p4"></div>
        <div class="pic" id="p5"></div>
        <div class="pic" id="p6"></div>
    </div>
</div>
```
Now for the CSS.
* Each id will simply require a background and a background-size of `cover`. 
```CSS
#p1 {
    background: white;
    background-size: cover;
}
#p2 {
    background: turquoise;
    background-size: cover;
}
```
I bet you can fill in images 3, 4, 5, and 6. 

## Adding links
I want to turn each div into a clickable image. This means there must be a link attribute surrounding each div. 
* Here is what that looks like on 1 div:
```
<a name="info-page"><div class="info-page"></a>
    <div class="pic-table">
        <a href="https://www.lacity.org/" target="_blank">
            <div class="pic" id="p1"></div>
        </a>
        <div class="pic" id="p2"></div>
        <div class="pic" id="p3"></div>
        <div class="pic" id="p4"></div>
        <div class="pic" id="p5"></div>
        <div class="pic" id="p6"></div>
    </div>
</div>

```
Just about done! Use the completed code below to fix your page up and make sure to add links and image backgrounds to each of the divs.

```HTML
<!DOCTYPE html>
<html>
<head>
    <title>Personl Website</title>
    <link rel="stylesheet" href="style.css">
</head>   
<body>
    
<!-- HOMEPAGE -->
<div class="homepage">
    <div class="name-header">
        <h1 class="home-h1">Title here</h1>
    </div>
    <div class="home-tagline">
        <p>"Tagline or quote here."</p>
    </div>
    <div class="home-button">
        <!-- the # is an anchor that links to an internal div, in this case the info-page div -->
        <a href="#info-page"><button type="submit">Learn more..</button></a>
    </div>
</div>
<!-- END HOMEPAGE -->

<!-- INFO PAGE -->
<a name="info-page"><div class="info-page"></a>
    <div class="pic-table">
        <a href="https://www.lacity.org/" target="_blank">
            <div class="pic" id="p1"></div>
        </a>
        <div class="pic" id="p2"></div>
        <div class="pic" id="p3"></div>
        <div class="pic" id="p4"></div>
        <div class="pic" id="p5"></div>
        <div class="pic" id="p6"></div>
    </div>
</div>

<!-- END INFO PAGE -->

</body>
</html>
```

```CSS
/* @import is used to import Google fonts, you can find a different font at https://fonts.google.com/ */
@import url(https://fonts.googleapis.com/css?family=Work+Sans:400,200,300,700,500);

html, body {
    margin: 0;
    padding: 0;
    height: 100%;
    font-family: 'Work Sans', sans-serif;
}

/* HOMEPAGE */
.homepage {
    background: url("http://images.summitpost.org/original/272289.jpg") no-repeat center center fixed;
    height: 100%;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
}

.name-header {
    color: white;
    text-align: center;
    padding-top: 17%;
    font-size: 3.5vmax;
}

.home-h1 {
    margin: 0;
}

.home-tagline {
    color: salmon;
    text-align: center;
    color: white;
    font-size: 2vmax;
}

.home-button {
    text-align: center;
    padding-top: 2%;
}

button {
    background: transparent;
    font-family: 'Work Sans', sans-serif;
    border: 1px solid white;
    color: white;
    height: 5vmax;
    width: 20vmax;
    font-size: 1.5vmax;
    letter-spacing: 1px;
}

button:hover {
    font-weight: 700;
    border: 5px solid white;
}

/* INFO PAGE */
.info-page {
    height: 100%;
    margin: 0;
    padding: 0;
    background:black;
    text-align:center;
}
.pic-table {
    margin: 0;
    padding-top:10%;
}
.pic {
    height: 25vmax;
    width: 25vmax;
    display:inline-block;
    margin: 1%;
}

#p1 {
    background: url("https://photos.travelblog.org/Photos/136486/494630/f/5013188-Venice_beach_sunset-0.jpg");
    background-size: cover;
}
#p2 {
    background: turquoise;
    background-size: cover;
}
#p3 {
    background: gray;
    background-size: cover;
}
#p4 {
    background: silver;
    background-size: cover;
}
#p5 {
    background: blue;
    background-size: cover;
}
#p6 {
    background: salmon;
    background-size: cover;
}



```




