# Data Visualization Workshop - Force Layout

## Sections:

* [Force Layout Documentation](#force-layout-documentation)
* [Force Simulation](#force-simulation)
* [D3 Force Functions](#d3-force-functions)
* [Force Layout Demo](#force-layout)
* [Bread Crumb Navigation](#bread-crumb-navigation)

## Force Layout Documentation

[Force Layout Docs](https://github.com/d3/d3-force)

In the domain of information visualization, physical simulations are useful for studying networks and hierarchies!

![Force Dragging](../images/force-dragging.png)

Force Layout is good at providing insights on the relationships between connections

[d3 force layout guide](http://d3indepth.com/force-layout/)

**To give credit where it is due, the following content below is derived from the above url**

D3 force layout uses a physics based simulator for positioning visual elements.

Forces can be set up between elements, For example:

* all elements repel one another

* elements are attracted to center(s) of gravity

* linked elements are a fixed distance apart (network visualisation)

* elements may not overlap (collision detection)

## Force Simulation

There are 4 steps in setting up force simulation:

1. Create an array of objects

2. Call forceSimulation, passing in the array of objects.

3. Add one or more force functions (forceManyBody, forceCenter, forceCollide, etc) to the system

4. Set up callback function to update the element positions after each tick.

```js
const dimensions = {
  width: 300,
  height: 300
};

const nodes = [{}, {}, {}, {}, {}];

let simulation = d3.forceSimulation(nodes)
  .force('charge', d3.forceManyBody())
  .force('center', d3.forceCenter(dimensions.width / 2, dimensions.height / 2))
  .on('tick', ticked);

function ticked() {
  var u = d3.select('svg')
    .selectAll('circle')
    .data(nodes)

  u.enter()
    .append('circle')
    .attr('r', 5)
    .merge(u)
    .attr('cx', function(d) {
      return d.x
    })
    .attr('cy', function(d) {
      return d.y
    })

  u.exit().remove()
}
```

## D3 Force Functions

Force functions are added to the simulation using .force() where the first argument is a user defined id and the second argument the force function:

```js
simulation.force('charge', d3.forceManyBody())
```

#### forceCenter

* [forceCenter](https://github.com/d3/d3-force#forceCenter) (for setting the center of gravity of the system)

Creates a new centering force with the specified x- and y- coordinates.
If x and y are not specified, they default to ⟨0,0⟩.

forceCenter is useful (if not essential) for centering your elements as a whole about a center point. (Without it elements might disappear off the page.)

Initialis with a center position:

`d3.forceCenter(100, 100)`

or using the configuration functions .x() and .y():

`d3.forceCenter().x(100).y(100)`

`simulation.force('center', d3.forceCenter(100, 100))`

#### forceManyBody

* [forceManyBody](https://github.com/d3/d3-force#forceManyBody) (for making elements attract or repel one another)

Creates a new many-body force with the default parameters.

forceManyBody causes all elements to attract or repel one another.
The strength of the attraction or repulsion can be set using .strength() where a positive value will cause elements to attract one another while a negative value causes elements to repel each other.
The default value is -30.

`simulation.force('charge', d3.forceManyBody().strength(-20))`

#### forceCollide

* [forceCollide](https://github.com/d3/d3-force#forceCollide) (for preventing elements overlapping)

Creates a new circle collision force with the specified radius.
If radius is not specified, it defaults to the constant one for all nodes.

forceCollide is used to stop elements overlapping and is useful when ‘clumping’ circles together.

We must specify the radius of the elements using .radius():

```js
var numNodes = 100
var nodes = d3.range(numNodes).map(function(d) {
  return {radius: Math.random() * 25}
})

var simulation = d3.forceSimulation(nodes)
  .force('charge', d3.forceManyBody().strength(5))
  .force('center', d3.forceCenter(width / 2, height / 2))
  .force('collision', d3.forceCollide().radius(function(d) {
    return d.radius
  }))
```

### forceX and forceY

forceX and forceY cause elements to be attracted towards specified position(s).

#### forceX

* [forceX](https://github.com/d3/d3-force#forceX) for attracting elements to a given point

Creates a new positioning force along the x-axis towards the given position x.
If x is not specified, it defaults to 0.

```js
simulation.force('x', d3.forceX().x(function(d) {
  return xCenter[d.category];
}));
```

#### forceY

* [forceY](https://github.com/d3/d3-force#forceY) for attracting elements to a given point

Creates a new positioning force along the y-axis towards the given position y.
If y is not specified, it defaults to 0.

#### forceLink

* [forceLink](https://github.com/d3/d3-force#forceLink) for creating a fixed distance between connected elements

Creates a new link force with the specified links and default parameters.
If links is not specified, it defaults to the empty array.

* forceLink pushes linked elements to be a fixed distance apart.
* It requires an array of links that specify which elements we want to link together. * Each link object specifies a source and target element, where the value is the element’s array index:

```js
var links = [
  {source: 0, target: 1},
  {source: 0, target: 2},
  {source: 0, target: 3},
  {source: 1, target: 6},
  {source: 3, target: 4},
  {source: 3, target: 7},
  {source: 4, target: 5},
  {source: 4, target: 7}
]
```

We pass our links array into the forceLink function using .links():

`simulation.force('link', d3.forceLink().links(links))`

**Once again all credit for this content goes to [d3indepth.com/force-layout/](http://d3indepth.com/force-layout/)**

## Force Layout

[Force Layout](https://bl.ocks.org/mbostock/ad70335eeef6d167bc36fd3c04378048)

[Force Layout Forked Demo](http://blockbuilder.org/jbelmont/1aab97d586c87c2872b0ceeaa7769773)

## Bread Crumb Navigation
_________________________

Previous | Next
:------- | ---:
← [Third Challenge](./third-challenge.md) | [D3 and Vuejs](./d3-and-vuejs.md) →
