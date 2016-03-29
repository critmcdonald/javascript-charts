## JavaScript and HighCharts

JavaScript can find an element on page through the Document Object Model, or DOM, which is really just a map of all the elements on the page. Developers help this by identifying elements on a page through the use of an `id` or `class`.

[Google charts](https://developers.google.com/chart/interactive/docs/quick_start) is a JavaScript library that inserts interactive charts onto your page.

It's all a bunch of magic until you work with it a while. We'll lay in the pieces for a simple chart, and then describe those pieces. It's basically the [Quickstart section Google Charts site](https://developers.google.com/chart/interactive/docs/quick_start).

## Follow along

### Add the chart placeholder

* Add this code below after the line with the `<p>` tag.

```html
    <!--Div that will hold our chart-->
    <div id="chart_div"></div>
```

We've added a "division" and identified it with an `id` of "chart_div". This allows our JavaScript to find just that place on the page, and then put our chart inside it.

If you saved your page and refreshed now, there wouldn't be any visible changes because we haven't put anything inside the `div` yet.

### Load the libraries

This comes from [Basic Libary Loading](https://developers.google.com/chart/interactive/docs/basic_load_libs)

* To make our charts work, we have to add the Google Charts libraries to the `<head>` tag of our web page. Add this below the `<style>`s section you added earlier.

<!-- put this after the head after all the styles -->


```html
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <script type="text/javascript">
      // Load the Visualization API and the piechart package.
      google.charts.load('current', {packages: ['corechart']});
      // Set a callback to run when the Google Visualization API is loaded.
      google.charts.setOnLoadCallback(drawChart);

      // drawChart function that will:
      // * create and populates a data table
      // * Set chart options
      // * instantiate the chart, pass in the data and draw it.
      function drawChart() {

      // Create the data table


      // Set chart options


      // Instantiate and draw our chart, passing in some options.


      }

    </script>
```

Again, if you saved and refreshed your page at this point, there still wouldn't be a visible change because we haven't configured out chart yet.

### Define and add the chart

* After the script code you added above, add this chunk of code on the following line. I'll explain it below.

```javascript
  

```

* Go ahead and save your page an refresh it to make sure your chart shows up.

That's a big mess of code, eh? All the parenthesis, braces and punctuation are really important. This is called "syntax" in programming. It's like grammar rules you can't break or your code will break. We use indentation to try to make sense of all the nesting, which gets confusing. Let's break it down as best we can:

* The `<script>` tags tell the browser that everything between them is JavaScript. We actually don't need the `type` part of that, because JavaScript is the default script language for browsers, but we'll leave it here.
* The next line that starts with `//` is a comment in JavaScript. It's a note to say this is where the bar chart starts, and isn't really part of the code. It's just helps the next developer know what's going on.
* OK, now the fun part. The `$` sign in JavaScript is shorthand to call JQuery. In this line, we are opening a JQuery function so we can use HighCharts. At it's most basic, it is this: `$(function () {});` but inside of the curly braces, we are nesting the chunk of code that calls HighCharts.
* In the next line, we call the highcharts code to create our barchart. It is basically `$('#barChart').highcharts();`. But, like above, we are nesting a bunch of stuff within the last parenthesis there.
  * Inside the first parenthesis, we are defining where we are putting the chart, in our case `'#barChart'`, which is the `<div>` where we want our chart to go. The words after `#` has to match the `id` in our div in our page content for the chart to show up there.
  * The next part `.highcharts({})` is the highcharts method, where we define different parts of the chart. Again, we're nesting stuff inside the curly braces, all using proper syntax:
    * We define our chart type as `bar`.
    * We define our title as 'Fruit Consumption', which puts that actual text where the title belongs.
    * We define our xAxis categories as Apples, Bananas and Oranges. We've put those three items in an *array*, which is basically a list of items in programming. The square brackets tell us it's an array.
    * On our yAxis, we've defined our title to be 'Fruit Eaten'
    * Series is all the data that will be on the chart, and were our data goes.
      * That first square bracket signifies and array, or list. Basically, we have a set of points for each person eating fruit.
        * For each person, we describe their name, and then the data, which has to be in the same order as our xAxis categories above. Jane has 1 apple, 0 bananas and 4 oranges.

We could add another person to the chart by adding another segment to the `series` array, but our chart is basically done. [Example code](03_mychart.html)

There are many more [chart types](http://www.highcharts.com/demo/) and much that you can [do with them](http://www.highcharts.com/docs), but we're going to stay with the bascis here.

There are many other javascript charting libraries:

* [Google Charts](https://developers.google.com/chart/)
* [Charts.js](http://www.chartjs.org/)
* [D3: Data-Driven Documents](http://d3js.org/)
* [and many more](http://www.sitepoint.com/15-best-javascript-charting-libraries/)

NEXT, if time: [Cleanup](04_cleanup.md)

BACK: [CSS](04_css.md)


