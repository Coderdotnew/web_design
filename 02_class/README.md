# Introduction to CSS
Without Cascading Style Sheets, our websites will be plain black text on a plain white background--pretty boring, right? CSS works directly with an HTML file, even more specifically, the HTML tags in the related file. For example, our CSS file cannot style a `<h4>` tag if there is no `<h4>` tag!

## Linking to HTML
* Because we are creating a separate file for CSS, we need to create a link between this and the HTML file. 
  * This link lets the browser know to use the CSS file in conjunction with the HTML.
  * We put this link in the <head> tag in the HTML document. Putting it inside this tag lets the browser read over it while making it not visible to the viewers.
```html
<head>
    <title>Personal Website</title>
    <link rel="stylesheet" href="style.css">
</head>
```
* `"style.css"` is the generic CSS stylesheet in our directly, therefore we must link directly to this filename.
* Now that the relative files are linked, we can move over to the CSS file.

# CSS Syntax
Unlike HTML, CSS does *not* use brackets to define code. Since there is not any plain text in a CSS file, we do not need to separate plain text and code.
* CSS is split up into 3 simple components:
  * selector { 
    &nbsp;&nbsp;&nbsp;&nbsp;property: value
    } 
  * **selector** is the HTML element you want to style
  * **property** defines what aspect of the selector you want to change
  * **value** is what you are styling
* For example, 
```css
body { 
    background-color: Blue; 
}
```
* We are matching up the `body` selector, with the `<body>` (body) tag.
  * This means that background of the body of the webpage will be blue!

# Inheritence
![1](https://github.com/Coderdotnew/web_design/blob/master/gifs/inerhit.gif)  
Think about your parents' attributes, they may be tall or short, have straight or curly hair, perfect eyes or corrected vision, certain immunities, and unfortunately, possibly some diseases. You inherited these attributes and many more (or some combination) from your parents. Some might say you even inherited their sense of humor, cleanliness, level of intelligence, and other attributes.  
Inheritence is an important concept when dealing with HTML and CSS. But first, we need to talk about nesting.
* **Nesting** occurs in HTML when there is an element tag contained inside of a *parent* element tag. It looks like this: 
```html
<body>
    <h1>Hello, World!</h1>
</body>
```
* In this case, the `h1` tag is *nested* in the `body` tag.
* This basically means that the `h1` tag will "inherit" any style that is applied to the body tag.
  * For example, if the body tag is given a blue font color, it will be applied to every tag inside of it, in this case, `h1`.
  * The `body` tag can be referred to as the *parent* tag and the `h1` tag is referred to as the *daughter* tag (yes, there can be grandparent and granddaughter tags). 


# Basic CSS Styling
Let's add some basic styling to our webpage. We have already given the `body` a background-color of blue. 
* Certain color names can be used safely in a web browser. This means that web browsers only recognize certain color names, such as blue, red, silver, and many other.
* [Web Safe Color Names](http://www.w3schools.com/colors/colors_names.asp)

### Font Color
```css
body { 
    background-color: Blue;
    color: Cyan;
}
```
*  Don't let the web safe color names limit you. There are several other formats to apply color values, one of which relies on **hexidemical** codes.
*  Hex codes are defined by a `#` followed by a six digit sequence, which is a combintion of different shade values of red, blue, and green. 
    *  `#ff0000` = red
    *  `#00ff00` = green
    *  `#0000ff` = blue  
    *  ##### [Color Code Picker](http://htmlcolorcodes.com/)

Due to inheritance, our `h1`, `h3`, and `p` tags are all the same color due to inheriting this trait from the `body` tag. Let's give each one a their own color:
```css
body { 
    background-color: Blue;
}
h1 {
    color: Cyan;
}
h3 {
    color: Fuchsia;
}
p {
    color: White;
}
```
* Note: This is *your* webpage, find colors that *you* like!

#### Font Size
For now, we will be using an absolute measuring value known as **pixels** to size our fonts. 
* A pixel is the basic unit of programmable measurement. Think of a pixel as each tiny dot of color combinations that make up your entire screen. Different combinations make up different colors, images, videos, and other graphics. 
```css
body { 
    background-color: Blue;
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
```
* Note: Again, feel free to customize your font-size values until you find a size that works for your webpage!
* You know when you zoom into a picture so much it becomes a whole bunch of squares? Each one of those squares is considered a pixel. This is the smallest piece of an image that your computer is able to display.
* The smaller number of  pixels you set, the smaller the font will be.

#### Font-Family
Similar to writing up an essay using a Word document, font-families are available to change the style of your font (except here we can be more creative than we would be writing a research paper!)
* Just like web safe color names, web  browsers only accept certain font-family names. 
  * [Web Safe Font-Family Names](http://www.w3schools.com/cssref/css_websafe_fonts.asp)

Let's add the font-family attribute to the `body` tag because font-families are usually consistent throughout a webpage (this is your call though if you want each header and paragraph to have different font-families).
```css
body { 
    background-color: Blue;
    font-family: "Arial";
}
```
*  NOTE: If a font name has spaces in it, (i.e. Times New Roman) it must be contained within quotation marks
  *  `"Times New Roman"` vs `Arial`
  *  [CSS Font References](http://www.w3schools.com/css/css_font.asp)

#### Buttons
The standard button without CSS is straight out of a 1997 movie. 
* Note: Buttons are referred to as a **form** element, meaning they can help submit data for a user. 
* Form elements do not inherit font-families like other elements do.  

Common Button Attributes:
* **Border**: The border of a button takes in three values-- 
  * Thickeness
  * Style (solid, dashed, dotted, etc.)
  * Color
* **Background**
* **Font color**
* **Font size**
```css
button {
    background: transparent;
    border: 2px solid white;
    color: white;
    font-family: "Arial";
}
```

### Background-Image
Lastly, let's add a customized background image to the body of our webpage. First, go to [Google Images](https://images.google.com/?gws_rd=ssl) and search for an aesthetically pleasing background image
* City skylines, nature backgrounds, abstract designs, or other clean design styles work well for backgrounds
  * Note: You may want to adjust the settings to make sure the image dimensions are at least 1024x768 pixels)
* Once you find your image, copy the **image address**, not the website address (the image address likely ends in .jpg or .png)
  * This example incudes an image of a desert sunset 
  * <img src="https://github.com/Coderdotnew/web_design/blob/master/gifs/sunset.jpg" height="250px" width="350px">  

```css
body { 
    background: url("http://images.summitpost.org/original/272289.jpg");
    font-family: "Arial";
    background:
}
```
* Also within the body selector, we are going to insert a background image. To do this, we must find a high resolution image so it will not look pixelated when it is stretched across the screen.
* Because we are using an image URL instead of a color name we need to insert this URL in between parenthesis and quotes like so.
```css
body { 
    font-family: sans-serif;
    background: url("http://images.summitpost.org/original/272289.jpg");
}
```
* Not bad! However, there may be some repetition if your background image is not the *exact same size* as the browser (which it probably is not). We will fix this soon!
* Note: The copied image address must be inserted between quotation marks inside the parentheses in the `background` CSS property.

#### Text-Align
To finish this basic webpage, we want to center this text. In order to do this we must use the text-align property in the body selector to change the position of all the text on the page. The value of this property will be set to "center" (though you may prefer "right", or "left")
```css
body { 
    font-family: sans-serif;
    background: url("http://images.summitpost.org/original/272289.jpg");
    text-align: center;
}
```
![2](https://github.com/Coderdotnew/web_design/blob/master/gifs/newgirl_clap.gif)
##### Getting there! Our webpage finally has some color and style, but there is a lot of work to be done! Next, we will be adjusting our measurement values to be more *responsive*.