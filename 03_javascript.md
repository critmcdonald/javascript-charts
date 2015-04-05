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

That's a big mess, eh? Let's break it down as best we can.

* The `<script>` tag tells the browser this is JavaScript. We actually don't need the `type` part of that, because JavaScript is the default script language for browsers, but we'll leave it here.
* the next part that starts with `//` is a comment within JavaScript. It's a note to say this is where the bar chart starts, and isn't really part of the code. It's just helps the next developer know what's goign on.

