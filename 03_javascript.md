## javascript

JavaScript is the programming language native to the web browser. It is used to control behaivor on a web page.

JavaScript can *find* and element on page through the Document Object Model, or DOM, which is really just a map of all the elements on the page. Developers help this by identifying elements on a page through the use of `id` or `class`.

JQuery is a JavaScript library that helps developers take advantage of the DOM.

HighCharts is another JavaScript library that uses JQuery, and then adds it's own programming on top of it.

It's all a bunch of magic until you work with it a while. We'll lay in the pieces for a simple chart, and then describe the pieces. It's basically the Installation and First chart sections of the [Highcharts docs](http://www.highcharts.com/docs).

## Follow along

### Add the chart placeholder

* Add this code below after the line with the `<p>` tag.

```html
    <div id="barChart"></div>
```

We've added a "division" and given it an `id` of "barChart". This allows our JavaScript to find just that place on the page, and then put our chart inside it.

If you save your page and refresh now, there wouldn't be any visible changes because we haven't put anything inside the `div` yet.

### Add the JS libraries

* Add this code after the barChart `div`.

```javascript
<!-- javascript at bottom of page -->
<script src="https://code.jquery.com/jquery-2.1.3.min.js"></script>
<script src="http://code.highcharts.com/highcharts.js"></script>
<script src="http://code.highcharts.com/modules/exporting.js"></script>
```

These are the JavaScript libraries that we have to call onto the page in order for HighCharts to work. We are using JQuery, HighCharts and specific HighCharts module that allows you to download the chart. Again, if you saved and refreshed your page at this point, there would still be no change.

### Define and add the chart

* After the script code you added above, add this chunk of code. I'll explain each part afterward.

```javascript
<script type="text/javascript">
//making the bar chart
  $(function () { 
    $('#barChart').highcharts({
      chart: {
        type: 'bar'
      },
      title: {
        text: 'Fruit Consumption'
      },
      xAxis: {
        categories: ['Apples', 'Bananas', 'Oranges']
      },
      yAxis: {
        title: {
          text: 'Fruit eaten'
          }
      },
      series: [{
        name: 'Jane',
        data: [1, 0, 4]
      }, {
        name: 'John',
        data: [5, 7, 3]
      }]
    });
  });
</script>

```

* Go ahead and save your page an refresh it to make sure your chart shows up.

That's a big mess of code, eh? All the parenthesis, braces and punctuation are really important. This is called "syntax" in programming. It's like grammar rules you can't break or your code will break. We use indentation to try to make sense of all the nesting, which gets confusing. Let's break it down as best we can:

* The `<script>` tags tell the browser that everything between them is JavaScript. We actually don't need the `type` part of that, because JavaScript is the default script language for browsers, but we'll leave it here.
* The next line that starts with `//` is a comment in JavaScript. It's a note to say this is where the bar chart starts, and isn't really part of the code. It's just helps the next developer know what's going on.
* OK, now the fun part. The `$` sign in JavaScript is shorthand to call JQuery. In this line, we are opening a JQuery function so we can use HighCharts. At it's most basic, it is this: `$(function () {});` but inside of the curly braces, we are nesting the bit of code that calls HighCharts.
* In the next line, we call the highcharts code to create our barchart. It is basically this: `$('#barChart').highcharts();`. But, like above, we are nesting a bunch of stuff within the last parenthesis there.
  * The first part defines where we are putting the chart that follows, in our case `'#barChart'`, which is the `<div>` where we want our chart to go. This description here has to match the `id` in our div for the chart to show there.
  * The next part `.highcharts({})` is the highcharts method, where we define parts of the charts. Again, we're nesting stuff inside parenthesis:
    * We define our chart type as `bar`.
    * We define our title as 'Fruit Consumption', which put that actual text where the title belongs.
    * We define our xAxis categories as Apples, Bananas and Oranges. We've put those three items in an *array*, which is basically a list of items in programming. The square brackets tell us it's an array.
    * On our yAxis, we've defined our title to be 'Fruit Eaten'
    * Series is all the data that will be on the chart, and were our data goes.
      * That first square bracket signifies and array, or list. Basically, we have a set of points for each person eating fruit.
        * For each person, we describe their name, and then the data, which has to be in the same order as our xAxis categories above. Jane has 1 apple, 0 bananas and 4 oranges.



