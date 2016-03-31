# A little bit more

Congratulations! If you got this far, you've already made a Google Charts pie chart, and that is quite an accomplishment. Great job.

## But I want a bar chart!

If you look at the different [chart style examples](https://developers.google.com/chart/interactive/docs/gallery) for Google Charts, you can see that the construction of different chart types can be very similar.

Go into your chart and find the line that says:

``` javascript
var chart = new google.visualization.PieChart(document.getElementById('chart_div'));
```

And then change `PieChart` to `BarChart`, save your changes and then refresh your chart to see what happens.


## More configuration

That's great, but let's change it back to a `PieChart`.

There are some other changes we might consider adding to the chart. Each chart type has a list of options that can be configured, [including the pie chart](https://developers.google.com/chart/interactive/docs/gallery/piechart#Configuration_Options). Let's make some mods.

Let's review our current chart options:
``` javascript
      var options = {
        'title': 'How to make Christian\'s pizza',
        'width': 400,
        'height': 300
        }
      ;
```

We have a title (Note that we had to escape the single apostrophe), and we have a width and height. What else can we do?

Let's make our chart a 3D-looking chart chart. Add this to your options `'is3D':'true'`, but make sure you have a comma at the end of the line before it.

``` javascript
      var options = {
        'title': 'How to make Christian\'s pizza',
        'width': 400,
        'height': 300,
        'is3D': true,
        }
      ;
```

Now refresh your chart. Nice.

Now, lets make some change to the legend. If you look at the [pie chart configuration options](https://developers.google.com/chart/interactive/docs/gallery/piechart#configuration-options) and go down to `legend`, we'll see that legend can take on many options. Just like we are making a javascript array of `options`, we need to next inside of that an array for `legend`. So we can see how we make more than one change to the legend, we'll make two of them, for `legend.position` and `legend.alignment`.

``` javascript
      var options = {
        'title':'How to make Christian\'s pizza',
        'width':400,
        'height':300,
        'is3D': true,
        'legend': {
          'position': 'left',
          'alignment': 'center'
          }
        }
      ;
```

Here is an example of [the finished code](04_mychart.html).

I think that will about do it for this lesson. The trick with Google charts is to copy the example just as it is from the example website and make sure it works, and then see what changes you can make to bend Google Charts to your will.

BACK: [Javascript](03_javascript.md)

--30--
