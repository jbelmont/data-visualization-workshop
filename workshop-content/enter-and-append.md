# Data Visualization Workshop - Enter and Append

## Sections:

* [Enter and Append](#enter-and-append)
* [Enter and Append](#enter-and-append)
* [Enter and Append Demo](#enter-and-append-demo)
* [Bread Crumb Navigation](#bread-crumb-navigation)

## Enter and Append

[D3 Enter docs](https://github.com/d3/d3-selection#selection_enter)

`enter`:

* Returns the enter selection: placeholder nodes for each datum that had no corresponding DOM element in the selection.
* The enter selection is empty for selections not returned by selection.data.

* The enter selection is typically used to create “missing” elements corresponding to new data.
* For example, to create DIV elements from an array of numbers:

```js
const div = d3.select("body")
  .selectAll("div")
  .data([4, 8, 15, 16, 23, 42])
  .enter().append("div")
    .text(d => d);
```

* If the body is initially empty, the above code will create six new DIV elements, append them to the body in-order, and assign their text content as the associated (string-coerced) number:

```html
<div>4</div>
<div>8</div>
<div>15</div>
<div>16</div>
<div>23</div>
<div>42</div>
```

## Enter and Append Demo

[Svg Enter and Append](http://blockbuilder.org/jbelmont/3e6a7ce02a072da3db8a4f77483b811f)

[SVG Enter Append Call](http://blockbuilder.org/jbelmont/d750c43050baf612a11c9bb42e62551b)

[Enter and Append with Circles](http://blockbuilder.org/jbelmont/03048c2bf48778b1d605345d7fdd6965)

[Enter and Append](http://blockbuilder.org/jbelmont/b3418f3b8f3f90f8de7bc59bc4aa3592)

**Click `Fork` Button to Play with this on your own**

[Enter and Append with Existing Rects](http://blockbuilder.org/jbelmont/bbc300e1ebe57b3f39477845a510eb33)

## Bread Crumb Navigation
_________________________

Previous | Next
:------- | ---:
← [Selections](./selections.md) | [SVG](./svg.md) →
