# The basics of Javascript charts

This is a change to master.

By Christian McDonald | Data Visualization | Spring 2015

GOAL: To give students a basic understanding of how JavaScript charting tools work, so they can learn and explore in the future.

When you want to learn more, there are plenty of online tutorials:

* W3Schools HTML
* W3Schools CSS
* W3Schools JavaScript

To use JavaScript charting tools, you need to have the basic understanding of the code behind the modern-day website: HTML, CSS and Javascript.

I explain how these work together through an analogy of the human body:
HTML (Hypertext Markup Language, but no one calls it that) is the skeleton. It's is the underlying structure of a web page, holding all the parts together.
CSS (Cascading Style Sheets) is the skin and DNA of the body, defining the color and shape of all the bones underneath.
JavaScript is the muscles and brain. It controls the movement and functionality.

At their most basic levels, they are not difficult to understand. CSS and Javascript can get complex quickly.

## HTML basics

Every web page has these basic parts:

	<!DOCTYPE html>
	<html>
		<head>
			<title>Name of the page</title>
		</head>
		<body>
			<h1>Main headline</h1>
			<p>Text on the page</p>
		</body>
	</html>

Most HTML tags come in pairs, indicating a beginning and end. There are some exceptions (img, br, hr). 
The doctype describes to the browser that this is an HTML file. It stands alone and MUST be at the beginning of the page. Nothing should be before it.

* `<html>` (and the `</html>` at the end) describe where the page begins and ends.
* The `<head>` area contains information and code about the webpage that is not actually displayed. Our example include the `<title>`, which is the name of the page at the top of the browser. It also contains code that can describe what happens in the body of the page, like CSS and JavaScript. It's the brains and DNA of the page.
* The `<body>` is the content of the page. It is where the skeleton resides. It will have all text and images in the page, all within the elements described below.

There aren't that many HTML tags to learn, really. They come in two flavors: in-line elements happen within the flow of the page, and block elements are segments that naturally break the page and start over. CSS can change the behavior of both.

### Block elements

* `<h1>` is the biggest, main headline. `<h2>` is the next step smaller, and they go down to `<h6>`, I think. I rarely go past and h4. The text between the beginning and end tags is what is displayed on the page.


```
<h1>This is your headline</h1>
```

* `<p>` is a paragraph tag. The workhorse of text. You begin and end at every paragraph break.

```
	<p>This is the first paragraph</p>
	<p>This is the second</p>
```

* There are a couple of lists: `<ul>` is an unordered list, like the bulleted list here that you are reading here. `<ol>` is an ordered list, which has numbers or letters in order, like you might cite in a research paper. Inside of both kinds of lists are `<li>` list items which is the actual text on each line.

```
	<ul>
		<li>The first bullet item</li>
		<li>The second bullet item</li>
	<ul>
	<ol>
		<li>The first numbered item. It will start with the 1. even if you don't type it.</li>
		<li>This line with start with 2.</li>
	</ol>
```

* The `<table>` holds tabular information. At it's most basic, it will have inside it a `<tr>` to start each table row, or line of data. Each cell is defined by `<td>` or table data.

```
	<table>
		<tr>
			<td>first cell</td><td>second cell</td>
		</tr>
	</table>
```

* `<div>` is a division on the page. It provides organization, and way for you to separate parts of the page. It would naturally create a break and the next item on the page would be a new line, though that is often changed through CSS.
* `<hr>` is horizontal rule. It's one of the few that does not have a closing tag. `<hr>` stands alone.
* `<br>` is a break. It creates a new line. Another element without a closing tag.

### Inline elements

* `<span>` allows you to define words of text within a paragraph without creating a new line.
* `<strong>` and `<em>` (which is short for emphasis) are ways to signify bold or italic text. The browser will naturally make `<strong>` bold and `<em>` italic, but usually you define the font and style through CSS.
* `<img>` is the image tag
