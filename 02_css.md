# CSS basics

When our browser reads our skeleton code, it sets its own default styles. Since `<h1>` is usually the biggest headline on the page, the browser sets font values like size, color and weight. But different browsers do that differently, so we want to specify it ourselves. We do that through styles.

Inside of our `<head>` tag after the title, we are going tell the browser to make the headline red.

```css
    <style>
      h1 {
        color: red;
      }
    </style>
```

* The `style` tag says we are creating CSS. 
* We next specify the item we are trying to style, the `h1` in our case.
* Then, inside curly braces, we define two things: What we want to change, and then what we want it to be.

## Do it

* Copy and paste the code above and place it in mycharts.html on the line under your `<title>` tag.
* Save your code.
* Go to your browser and refresh (or reopen) that page.

You've now added some DNA to your skeleton, making the headline red. [Example code](02_mychart.html)

NEXT, the brain and muscles: [Javascript](03_javascript.md)

BACK: [HTML](01_html.md)
