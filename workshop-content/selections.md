# Data Visualization Workshop - Selections and Data

## Sections:

* [Selections and Data](#selections-and-data)
* [Playing with D3](#playing-with-d3)
* [Selections Demo](#selections-demo)
* [Bread Crumb Navigation](#bread-crumb-navigation)

## Selections and Data

[D3 Selections Documentation](https://github.com/d3/d3-selection)

* Selections are immutable.
* All selection methods that affect which elements are selected (or their order) return a new selection rather than modifying the current selection.
* However, note that elements are necessarily mutable, as selections drive transformations of the document!

[Selecting Elements](https://github.com/d3/d3-selection#selecting-elements)

```js
var anchor = d3.select("a");
```

This will select the first element that matches the specified selector string.

```js
const enter = svg.selectAll('rect')
```

This will select all elements that match the specified selector string

* If the selector is not a string, instead selects the specified array of nodes
* this is useful if you already have a reference to nodes, such as this.childNodes within an event listener or a global such as document.links

```js
d3.selectAll(document.links).style("color", "red");
```

```js
var even = d3.selectAll("tr").filter(":nth-child(even)");
```

Notice here that you can a css pseudo selector and you can also pass a function

```js
var even = d3.selectAll("tr").filter(function(d, i) { return i & 1; });
```

[Block Builder Editor](http://blockbuilder.org/)

* A very nice editor to build d3 visualizations that get saved as gists

* Click `START CODING` button
* Click Login and you will be routed to github page to authorize application
* You can then save your code here and get interactive editor

## Playing with D3

[Playing with D3](http://blockbuilder.org/jbelmont/ccd655bb9c410190e305408bb93871b9)

## Selections Demo

[Selections and Data Block Builder Demo](http://blockbuilder.org/jbelmont/f5c73b49d3478dfbb0135148fa04ad92)

[Selections Filter Demo](http://blockbuilder.org/jbelmont/e2017b083240255e42dffd515f9203d1)

[D3 Selections `attr`](https://github.com/d3/d3-selection#selection_attr)

* If a value is specified, sets the attribute with the specified name to the specified value on the selected elements and returns this selection.

* If the value is a constant, all elements are given the same attribute value

* Otherwise, if the value is a function, it is evaluated for each selected element, in order, being passed the current datum (d), the current index (i), and the current group (nodes), with this as the current DOM element (nodes[i]).

* The function’s return value is then used to set each element’s attribute. A null value will remove the specified attribute.

[D3 Selections `data`](https://github.com/d3/d3-selection#selection_data)

* Joins the specified array of data with the selected elements, returning a new selection that represents the update selection: the elements successfully bound to data

[D3 Selections `call`](https://github.com/d3/d3-selection#selection_call)

* Invokes the specified function exactly once, passing in this selection along with any optional arguments.

* Returns this selection. This is equivalent to invoking the function by hand but facilitates method chaining.

For example, to set several styles in a reusable function:

```js
function name(selection, first, last) {
  selection
      .attr("first-name", first)
      .attr("last-name", last);
}
```

[D3 Selections `text`](https://github.com/d3/d3-selection#selection_text)

* If a value is specified, sets the text content to the specified value on all selected elements, replacing any existing child elements.

* If the value is a constant, then all elements are given the same text content; otherwise, if the value is a function, it is evaluated for each selected element, in order, being passed the current datum (d), the current index (i), and the current group (nodes), with this as the current DOM element (nodes[i]).

* The function’s return value is then used to set each element’s text content. A null value will clear the content.

[D3 Selections `append`](https://github.com/d3/d3-selection#selection_append)

* If the specified type is a string, appends a new element of this type (tag name) as the last child of each selected element, or before the next following sibling in the update selection if this is an enter selection.

* The latter behavior for enter selections allows you to insert elements into the DOM in an order consistent with the new bound data; however, note that selection.order may still be required if updating elements change order (i.e., if the order of new data is inconsistent with old data).

* If the specified type is a function, it is evaluated for each selected element, in order, being passed the current datum (d), the current index (i), and the current group (nodes), with this as the current DOM element (nodes[i]). This function should return an element to be appended. (The function typically creates a new element, but it may instead return an existing element.)

For example, to append a DIV element to each paragraph:

`d3.selectAll("p").append("div");`

This is equivalent to:

```js
d3.selectAll("p").append(function() {
  return document.createElement("div");
});
```

Which is equivalent to:

```js
d3.selectAll("p").select(function() {
  return this.appendChild(document.createElement("div"));
});
```

[D3 style class attr and more play](http://blockbuilder.org/jbelmont/e991b69658afc57c5b8c4a0e9dd08fca)

## Bread Crumb Navigation
_________________________

Previous | Next
:------- | ---:
← [README](../README.md) | [Enter and Append](./enter-and-append.md) →
