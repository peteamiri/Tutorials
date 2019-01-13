# HTML5
* [Wiki](https://en.wikipedia.org/wiki/HTML5)
* [Specification](https://html.spec.whatwg.org/)
* [W3C Spec](https://www.w3.org/TR/2012/CR-html5-20121217/)
* [HTML5 working Group](https://www.w3.org/html/wg/)
* [Resources](https://developers.google.com/web/)
* [Mazilla](https://developer.mozilla.org/en-US/docs/Web/HTML)
* [Tutorial](https://www.html-5-tutorial.com/)
* [W3c School](https://www.w3schools.com/html/html5_intro.asp)
* [tutorials Point](https://www.tutorialspoint.com/html5/)
* [tutorial](http://www.html5andcss3.org/)
*

# Apendix A

Sample Style Sheet file. File Name `stylesheet.css`

```css
body {
  font-family: "Lucida Sans Unicode", "Lucida Grande", Verdana, sans-serif;
  max-width: 800px;
}

.Header {
  background-color: #7695FE;
  border: thin #336699 solid;
  padding: 10px;
  margin: 10px;
  text-align: center;
}

.Header h1 {
  margin: 0px;
  color: white;
  font-size: xx-large;
}

.Header .Teaser {
  margin: 0px;
  font-weight: bold;
}

.Header .Byline {
  font-style: italic;
  font-size: small;
  margin: 0px;
}

.Content {
  font-size: medium;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  padding-top: 20px;
  padding-bottom: 5px;
  padding-left: 50px;
  padding-right: 50px;
  line-height: 120%;
}

.Content .LeadIn {
  font-weight: bold;
  font-size: large;
  font-variant: small-caps;
}

.Content h2 {
  color: #24486C;
  margin-bottom: 2px;
  font-size: medium;
}

.Content p {
  margin-top: 0px;
}

.Footer {
  text-align: center;
  font-size: x-small;
}

.Footer .Disclaimer {
  font-style: italic;
}

.Footer p {
  margin: 3px;
}
```
Sample HTML 5 file

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Angular.js</title>
  <link rel="stylesheet" href="stylesheet.css">
</head>

<body>
<div class="Header">
<h1>Angular.JS</h1>
<p class="Teaser">Description of some of the concepts</p>
<p class="Byline">by Pete Amiri</p>
</div>

<div class="Content">
<p>
  <span class="LeadIn">What is Angular.js</span>
  is a structural framework for dynamic web apps. It lets you use HTML as your template language
  and lets you extend HTML's syntax to express your application's components clearly and succinctly.
  Angular's data binding and dependency injection eliminate much of the code you would otherwise
  have to write.<span class="style1">—</span>probably more comfortable than it's
  been for the average human being throughout all of recorded history.</p>

<p>But don't get too smug. There's still plenty of horrific ways it
could all fall apart. In this article, you'll learn about a few of our
favorites.</p>

<h2>Mayan Doomsday</h2>
<p>Skeptics suggest that the Mayan calendar simply rolls to a new
5,126-year era after 2012, and doesn't actually predict a life-ending
apocalypse. But given that the long-dead Mayans were wrong about
virtually everything else, why should we trust them on this?
</p>

</div>

<div class="Footer">
<p class="Disclaimer">These apocalyptic predictions do not reflect the views of the
author.</p>
<p>
<a href="AboutUs.html">About Us</a>
<a href="Disclaimer.html">Disclaimer</a>
<a href="ContactUs.html">Contact Us</a>
</p>
<p>Copyright © 2011</p>
</div>
</body>
</html>
```
