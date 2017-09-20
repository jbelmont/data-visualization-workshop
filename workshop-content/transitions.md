# Data Visualization Workshop - Transitions

## Sections:

* [Transitions](#transitions)
* [Bread Crumb Navigation](#bread-crumb-navigation)

## Transitions

* A transition is a selection-like interface for animating changes to the DOM.
* Instead of applying changes instantaneously, transitions smoothly interpolate the DOM from its current state to the desired target state over a given duration.

To apply a transition, select elements, call selection.transition, and then make the desired changes.

For example:

```js
d3.select("body")
  .transition()
    .style("background-color", "red");
```

* Transitions are derived from selections via selection.transition.
* You can also create a transition on the document root element using d3.transition.

[selection.transition](https://github.com/d3/d3-transition#selection_transition)

* Returns a new transition on the given selection with the specified name.
* If a name is not specified, null is used.
* The new transition is only exclusive with other transitions of the same name.

```js
var t = d3.transition()
    .duration(750)
    .ease(d3.easeLinear);

d3.selectAll(".apple").transition(t)
    .style("fill", "red");

d3.selectAll(".orange").transition(t)
    .style("fill", "orange");
```

[Circle Transitions](http://blockbuilder.org/jbelmont/dd2b58748e79855d1baa9d11fb76cef8)

**Click `Fork` Button to Play with this on your own**

## Bread Crumb Navigation
_________________________

Previous | Next
:------- | ---:
← [Exit and Merge](./exit-and-merge.md) | [Third Challenge](./third-challenge.md) →
