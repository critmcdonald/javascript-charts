# Cleanup

We need to fix just a couple of things with our chart. Let's do two things:

* set the width and height of the chart using CSS
* Fix some font problems within the tooltips.

## Width and Height

* Replace your CSS code this this:

```css
    <style>
      h1 {color: red;}
      #barChart {width: 500px; height: 400px;}
    </style>
```

We're doing a couple of things here.

* We're condensing the code that made the h1 red, just putting it all on one line.
* We finding our div `#barChart` and setting a width and height. The # says to look for the `id=` and the value that follows. If you use an `id` on a page, there should be only one.

## Fixing the tooltip

Whenever I roll over the tooltips, I get a funky character I don't like. I can set a HighCharts option to format the tooltips to now use that character.

* Add the following code after the `<script type="text/javascript">` tag on the page:

```javascript
  //set global options to fix tooltip
  $(function () {
      Highcharts.setOptions({
          tooltip: {
            pointFormat: '<span style="color:{series.color}">{series.name}</span>: <b>{point.y}</b><br/>',
          },
      });
  });
```

We're again using JQuery to call Highcharts, and then setting a tooptip option. For that tooltip, we are defining the pointFormat to be specific HTML and using data from that series in curly braces. This is much like the info window you edited in Google Fusion Tables.

