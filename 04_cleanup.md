# Cleanup

If we have time, we can fix a couple of things with our chart. Let's do two things:

* Set the width and height of the chart using CSS.
* Redefine the tooltip display to fix some font problems.

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
* We finding our div `#barChart` and setting a width and height. The # says to look for the `id=` and the value that follows. If you use an `id` on a page, there should be only one of that name.

## Fixing the tooltip

Whenever I roll over the tooltips, I get a funky character I don't like. I can set a HighCharts option to format the tooltips to now use that character.

* On the line in the chart javascript that stars with `series`, ddd the following code:

```javascript
      tooltip: {
        pointFormat: '<span style="color:{series.color}">{series.name}</span>: <b>{point.y}</b><br/>',
      },
```

This adds an option to the chart that defines parts of the tooltip. In our case ee are setting that the `pointFormat` to be specific HTML and using data from that series in curly braces. This is much like the info window you edited in Google Fusion Tables.

[Example code](04_mychart.html)

[Javascript](03_javascript.md)

--30--
