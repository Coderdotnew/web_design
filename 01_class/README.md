# Web Design with HTML, CSS, & JavaScript
Web design is a field of computer programming that determnines how web pages look and what they say. This might includes different titles, images, paragraphs, links, tables, navigation bars, footers, and much more. *Every page you have ever viewed on the internet* was written with some format of HTML. If there were colors and different fonts used, then it definitely included some CSS. And if there were popup windows, motion, or maybe automatic scrolling, there was likely some JavaScript included as well!  
![1](https://github.com/Coderdotnew/web_design/blob/master/gifs/internet.gif)

## What is HTML?
HTML stands for **Hypertext Markup Language**. Every page you see on the web is built with HTML. 
* You view webpages *in a browser*. You have one open right now as you are reading this text!
  * A **browser** is an application on your computer that lets you view webpages on the internet.
  * Google Chrome, Safari, Firefox, and Internet Explorer are a few examples of web browsers.
* HTML is made up of tags that structure the content on the page, which essentially determineshow a site looks and what words and images are displayed.
* This basically acts as the "skeleton" of a website--it holds everything together.
* HTML is interpreted by your browser where the code is translated to form a webpage.
* When you think HTML, think *content*.


## What is CSS?
CSS stands for **Cascading Style Sheets**.
* This gives a style and format to your HTML, in other words it makes your website look pretty.
* It can help define certain aspects of HTML such as font, background, positioning, sizing, spacing, and other visual information. 
* CSS works directly with an HTML pages and changes the way information is presented.
* When you think CSS, think *style*.

![2](https://github.com/Coderdotnew/web_design/blob/master/gifs/style.gif)

## HTML Syntax
Just like English, HTML reads top to bottom, left to right.
* HTML uses **tags** for the browser to distinguish between plain text and your code.
* Tags are used to describe certain *elements* that are going to be edited. For example:
  * paragraphs
  * links
  * images
  * headers
  * tables
  * lists
* Each element is enclosed in angle-brackets (`<`, `>`). 
  * Without these, the element will just be interpreted as plain text, and will be printed on your webpage. 
* *Almost* all tags include an opening and closing tag (just like senetences begin with a capital letter and punctuation).
```html
<p>This is a paragraph!</p>
```
* The tag in this example is `p` which represents paragraph.
* The opening tag, `<p>` is on the lef.
* The closing tag, `</p>` is on the right and MUST include the forward slash (`/`) to indicate it is a closing tag. Without a closing tag, your HTML won't work correctly, sort of like when you forget a period, it turns into a runon sentence.

## Page Structure
Three tags essentially make up and hold everything in an HTML webpage--`<head>`, `<html>`, and `<body>`. ALL code goes inside the html tag. (Which lets the browser know what language we are coding in!)
* Below is an example of VERY basic HTML structure--this is what you start out with every time you build a page.
* Note: `<!DOCTYPE html>` is a declaration for the browser to read the document as HTML, and not any other language and does not require a closing tag (but the rest do!)
```html
<!DOCTYPE html>
<head>
    <!-- Information like a title goes here -->
</head>
<body>
    <!-- All content for the webpage goes here -->
</body>
</html>
```
* Note: `<!-- notes here -->` represents a comment, which means the browser ignores it!

## Head
Your own head contains a very important organ, your brain. Think of the head tag as your brain; it contains information about language it speaks (`<html>`), what it calls itself (`<title>`), any realtives it has (links to other sheets CSS, JS).
* The `<head>` tag stores information that does not appear on the page itself (i.e. metadata, which describes the webpage and let search engines find your page, the page title, etc.)
* Adding a title for the page is simple, just use `<title></title>`. This will be displayed at the top of your browser, usually in the tab.
```html
<DOCTYPE! html>
<head>
    <title>Personal Website</title>
</head>
<body>
    <!-- All content for the webpage goes here -->
</body>
</html>
```
* When the page runs in the browser, notice the title in the tab has changed!
* Now that we have the basic structure for our page, we can start adding some text...

## Body
Everything added to the `<body>` will appear on your webpage.
* Plain text that is not enclosed in tags will be shown as the browser's default font family and size (spoiler alert: it will look plain)
* Lets start out with a header...

### Headers
Header tags are typically reserve for titles and headings. These tags will have bold and larger font.
* There are different sizes of header tags (`<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`) with `h1` being largest and `h6` being smallest.
* Here we are adding an `h1` header to the body of our page:
```html
<!DOCTYPE html>
<head>
    <title>Personal Website</title>
</head> 
<body>
    <h1>Body Title Text Here</h1>
</body>
</html>
```

Next, let's add an `h3` tag below the first header. This will server as a tagline for our webpage.
```html
<!DOCTYPE html>
<head>
    <title>Personal Website</title>
</head> 
<body>
    <h1>Body Title Text Here</h1>
    <h3>Tagline or quote here...</h3>
</body>
</html>
```

### Buttons
Buttons serve many functions. Sometimes they allow you to submit data, other times they allow you to select from a list of options. 
* The `<button>` tag is pretty self-explanitory; it adds a basic button to your page.
```html
<!DOCTYPE html>
<head>
	<title>Personal Website</title>
</head>
<body>
	<h1>Title here</h1>
	<h3>"Tagline or quote here."</h3>
	<button>Learn more...</button>
</body>
</html>
```
* The text between the opening and closing `button` tag is the text that will appear directly on the button itself.

Lastly, let's add a longer paragraph tag to give a brief description of the webpage, perhaps a bio.

### Paragraphs
As mentioned before, `<p>` is the paragraph tag, used for smaller font in addition to long chunks of text.
* Using these tags to separate different content will help organize the body while also making it easier to style when we get into CSS.
```html
<!DOCTYPE html>
<head>
	<title>Personal Website</title>
</head>
<body>
	<h1>Title here</h1>
	<h3>"Tagline or quote here."</h3>
	<button>Learn more...</button>
	<p>Longer paragraphs or descriptions can be inserted inside paragraph tags. This might include a biography, website description, or additional information.</p>
</body>
</html>
```


# HTML Cheat Sheet
Tag | Function
--- | --- 
`<!DOCTYPE html>` | Declares the browser language as HTML
`<p>Paragraph text</p>` | Paragraph
`<h1>`...`<h6>` | Headers (biggest = 1, smallest = 6)
`<a href="link address here">Link display text here</a>` | Makes text clickable
`<img src="image link here">` | Displays an image on webpage
`<br>` | Creates a break between text lines (like pressing enter)
`<hr>` | Similar to `<br>`, but inserts a horizontal line

![3](https://github.com/Coderdotnew/web_design/blob/master/gifs/cheatsheet.gif)

# Resources
![w3school Reference](http://www.w3schools.com/tags/)
* This is a great source to find a more extensive and complete list of tags and a lot of other helpful info on HTML, CSS, and many other languages!