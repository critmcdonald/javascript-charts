# HTML basics

We're going to start with the most basic HMTL page:


```
<!DOCTYPE html>
<html>
  <head>
    <title>My First JS Chart</title>
  </head>
  <body>
    <h1>Main headline</h1>
    <p>Text on the page</p>
  </body>
</html>
```

Most HTML tags come in pairs, indicating a beginning and end. There are some exceptions. 

* The `DOCTYPE` describes to the browser that this is an HTML file. It stands alone and MUST be at the beginning of the page. Nothing should be before it.
* `<html>` (and the `</html>` at the end) describe where the page begins and ends.
* The `<head>` area contains information and code about the webpage that is not actually displayed. Our example has the `<title>`, which is the name of the page at the top of the browser. It also contains code that can describe what happens in the body of the page, like CSS and JavaScript. It's the brains and DNA of the page.
* The `<body>` is the content of the page. It is where the skeleton resides. It will have all text and images in the page, all within the elements described below.

## Do it

* Launch TextWrangler of another code editor (not MSWord!)
* copy and paste the code above into it.
* Save the file as mychart.html and put it on your desktop
* Go into Chrome, go under File > Open and open the file.

You should see a web page that says "Main headline" and "Text on the page." You now have a skeleton. [Example code](01_mychart.html)

NEXT, the DNA: [CSS](02_css.md)

BACK: [Intro](README.md)