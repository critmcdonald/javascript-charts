## JavaScript and HighCharts

JavaScript is the brains and muscle of your page, giving it logic and making it able to move and change.

[Google charts](https://developers.google.com/chart/interactive/docs/quick_start) is a JavaScript library that inserts interactive charts onto your page.

It's all a bunch of magic until you work with it a while. We'll lay in the pieces for a simple chart, and then describe those pieces. It's basically the [Quickstart section from Google Charts site](https://developers.google.com/chart/interactive/docs/quick_start).

## Follow along as we go

Typically, you would copy 'n' paste the whole example onto your page at once, but I'm going to walk through this code bit-by-bit to explain it.

### Add the chart placeholder

* Add this code below into the body of your page, after the line with the `<p>` tag.

```html
    <!--Div that will hold our chart-->
    <div id="chart_div"></div>
```

Javasript can find an element on page through the Document Object Model, or DOM, which is really just a map of all the elements on the page. Developers help this by identifying HTML elements on a page through the use of an `id` or `class`.

We just did that by identifying our `div` with an `id` of "chart_div". The id allows our JavaScript to find just that place on the page, and then put our chart inside it.

If you saved your page and refreshed now, there wouldn't be any visible changes because we haven't put anything inside the `div` yet. We'll get there, I promise.

### Loading the charting libraries

(This part is explained further in [Basic Libary Loading](https://developers.google.com/chart/interactive/docs/basic_load_libs))

To make our charts work, we will add the Google Charts libraries to the `<head>` tag of our web page. Add this after the close `</style>` tag you added earlier.

<!-- put this after the head after all the styles -->
```javascript
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <script type="text/javascript">
      // Load the Visualization API and the piechart package.
      google.charts.load('current', {packages: ['corechart']});
      // Set a callback to run when the Google Visualization API is loaded.
      google.charts.setOnLoadCallback(drawChart);

      // drawChart function that will:
      // * create and populate a data table
      // * Set chart options
      // * instantiate the chart, pass in the data and draw it.
      function drawChart() {

      // Create the data table


      // Set chart options


      // Instantiate and draw our chart, passing in some options.


      }

    </script>
```

Again, if you saved and refreshed your page at this point, there still wouldn't be a visible change because we haven't configured our chart yet.

### Create the data table

(This part is explained further in [Prepare the data](https://developers.google.com/chart/interactive/docs/basic_preparing_data))

The next thing we're going to do is define our data. Paste this code under the comment "Create the data table", and then I'll explain it:

```javascript
      var data = new google.visualization.DataTable();
      data.addColumn('string', 'Topping');
      data.addColumn('number', 'Amount');
      data.addRows([
        ['Onions', 1],
        ['Black Olives', 1], 
        ['Sausage', 2],
        ['Pepperoni', 2]
      ]);
```

* Starting on the first line, we are creating a javascript variable called `data`, and then we say that variable hold a new `DataTable` from the `google.visualization` library.
* Now that we have defined `data` as a `DataTable`, the next line says let's add a Column to it. The data type is 'string' and we are labeling it 'Topping'. This is the first column of our table.
* The next adds another column of numbers, and we are labeling it 'Amount'. We have defined the second column of our table.
* Lastly, we are adding rows of content to the table, and we are adding four rows of them. Inside of those rows, we define the 'Topping' and number for the 'Amount', based on their order.

You can envision our datatable `data` looking like this:

| Topping      | Amount |
|--------------|--------|
| Onions       | 1      |
| Black olives | 1      |
| Sausage      | 2      |
| Pepperoni    | 2      |

### Set chart options

(This is further explained in [Customize the charts](https://developers.google.com/chart/interactive/docs/basic_customizing_chart))

There are some options we can give our chart. We'll give our chart at title, width and height.

Add this on the line after the comment "Set chart options":

``` javascript
      var options = {
        'title':'How to make Christian\'s pizza',
        'width':400,
        'height':300
        }
      ;
```

### Make the chart!

(This portion is further explained in  [Draw the chart](https://developers.google.com/chart/interactive/docs/basic_draw_chart))

Finally, we add the code that will draw this chart on the page. Add this after the comment "Instantiate and draw our chart, passing in some options."

``` javascript
      var chart = new google.visualization.PieChart(document.getElementById('chart_div'));
      chart.draw(data, options);
```

Now, finally, if you ate your Wheaties and copied 'n' pasted right, you should be able to save your file, then refresh your page in the browser see the chart.

Here is the [Example code](03_mychart.html)

### Troubleshooting

We might have an opportunity here to talk about using the [Chrome Inspector](https://developers.google.com/web/tools/chrome-devtools/?hl=en) to read the console of your browser.

-------

There are many more [chart types](https://developers.google.com/chart/interactive/docs/gallery).

There are many other javascript charting libraries:

* [Highcharts](http://www.highcharts.com/docs)
* [Charts.js](http://www.chartjs.org/)
* [D3: Data-Driven Documents](http://d3js.org/)
* [and many more](http://www.sitepoint.com/15-best-javascript-charting-libraries/)

NEXT, if time: [Cleanup](04_cleanup.md)

BACK: [CSS](04_css.md)


