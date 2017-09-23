# Data Visualization Workshop - SVG

## Sections:

* [SVG Basic Shapes](#svg-basic-shapes)
* [Rectangles](#rectangle)
* [Circles](#circles)
* [Ellipses](#ellipses)
* [Straight Lines](#straight-lines)
* [Bread Crumb Navigation](#bread-crumb-navigation)

## SVG Basic Shapes

SVG Basic Shapes:

* Rectangle
* Circle
* Ellipse
* Straight Line
* Polyline
* Polygon
* Path

The basic shapes that SVG provides are:

* rectangle

* circle

* ellipse

* straight line

* polyline, polygon and path

## Rectangles

```xml
<svg width="50" height="50">
    <rect x="0" y="0" width="50" height="50" />
</svg>
```

For us to be able to use an SVG rectangle it must be defined inside of the SVG tags.

The x and y - which is where the rectangle is drawn from and the height and width

The SVG coordinate space starts at the top left and goes to the bottom right as x and y coordinates increase.

So as the height increases, the rectangle will get longer down

And as the width increases, the rectangle will get longer to the right.

```js
var rectangles = [
  {"x": 0,   "y":   0, "width": 30, "height": 40},
  {"x": 50,  "y":  50, "width": 30, "height": 40},
  {"x": 100, "y": 100, "width": 30, "height": 40},
  {"x": 150, "y": 150, "width": 30, "height": 40}
];
```

```js
var svgContainer = d3.select("body")
  .append("svg")
  .attr("width","560")
  .attr("height","900");
```

```js
var svgRectangles = svgContainer
  .selectAll("rect")
  .data(rectangles)
  .enter()
  .append("rect");
```

This binds each JSON object to an SVG rectangle DOM element

```js
svgRectangles
    .attr("x",      function (d,i) { return d.x;  })
    .attr("y",      function (d,i) { return d.y;      })
    .attr("width",  function (d,i) { return d.width;  })
    .attr("height", function (d,i) { return d.height; });
```

We use an anonymous function to extract the relevant information from each JSON object
For the rectangle, this means the x, y, width and height information.

[D3 Rectangle in SVG](http://blockbuilder.org/jbelmont/f3cd7d0885e7a285021d5bfcb63c12eb)

## Circles

```xml
<svg width="50" height="50">
    <circle cx="25" cy="25" r="25" />
</svg>
```

SVG circles must be defined inside of the SVG tags

The SVG circle takes in three main inputs:

* cx which is where the center of the circle is drawn from
* cy which is where the center of the circle is drawn from
* r which is the radius of the circle.

The JSON objects should have the cx, cy and r properties.

```js
var svgContainer = d3.select("body")
  .append("svg")
  .attr("width","560")
  .attr("height","900");
```

First, we define the SVG Container the rectangles will live in.

Note that we define the width and height of the SVG viewport container

```js
var circles = [
  {"cx":  25, "cy":  25, "r": 20},
  {"cx":  75, "cy":  75, "r": 20},
  {"cx": 125, "cy": 125, "r": 20},
  {"cx": 175, "cy": 175, "r": 20}
];
```

The circles array contains 4 circle JSON Objects.

This will be the data source used to construct the circles

```js
var svgCircles = svgContainer.selectAll("circle").data(circles).enter().append("circle");
```

This binds each JSON object to an SVG circle DOM element

```js
svgCircles
    .attr("cx", function (d,i) { return d.cx; })
    .attr("cy", function (d,i) { return d.cy; })
    .attr("r",  function (d,i) { return d.r;  });
```

We use an anonymous function to extract the relevant information from each JSON object

For the circle, this means the cx, cy and r information.

Bonus if you can set the first SVG Circle to Red Color

**Tip use the filter function with the svgCircles variable**

[D3 Circles in SVG](http://blockbuilder.org/jbelmont/99ffa83bcf299372014e743419cadc2d)

## Ellipses

```xml
<svg width="50" height="50">
    <ellipse cx="25" cy="25" rx="15" ry="10" />
</svg>
```

SVG ellipses must be defined inside of the SVG tags.

The SVG ellipse takes in four main inputs:

* cx which is where the center of the ellipse is drawn from
* cy which is where the center of the ellipse is drawn from
* x radius of the ellipse
* y radius of the ellipse

The JSON object should have the cx, cy, rx and ry properties.

```js
var svgContainer = d3.select("body")
  .append("svg")
  .attr("width","560")
  .attr("height","900");
```

Here we define the SVG Container the ellipses will live in.

Note that we define the width and height of the SVG viewport container

```js
var ellipses = [
  {"cx":  25, "cy":  25, "rx": 15, "ry": 20},
  {"cx":  75, "cy":  75, "rx": 15, "ry": 20},
  {"cx": 125, "cy": 125, "rx": 15, "ry": 20},
  {"cx": 175, "cy": 175, "rx": 15, "ry": 20}
];
```

The ellipses array contains 4 ellipse JSON Objects.

This will be the data source used to construct the ellipses

```js
var svgEllipses = svgContainer
  .selectAll("ellipse")
  .data(ellipses)
  .enter()
  .append("ellipse");
```

```js
svgEllipses
    .attr("cx", function (d,i) { return d.cx; })
    .attr("cy", function (d,i) { return d.cy; })
    .attr("rx", function (d,i) { return d.rx; })
    .attr("ry", function (d,i) { return d.ry; });
```

We use an anonymous function to extract the relevant information from each JSON object

For the ellipse, this means the cx, cy, rx and ry information.

```js
d3.selectAll('ellipse').data()
```

This will return the data bound to each ellipse

```js
d3.selectAll('ellipse').nodes()
```

This will return each dom node for each ellipse

This binds each JSON object to an SVG ellipse DOM element

[D3 Ellipses in SVG](http://blockbuilder.org/jbelmont/d3461d2bc771d8e2d7bac18d192b6f4a)

## Straight Lines

```xml
<svg width="50" height="50">
    <line x1="5" y1="5" x2="40" y2="40" stroke="gray" stroke-width="5" />
</svg>
```

SVG Straight Lines must be defined inside of the SVG tags.

The SVG Straight Line takes in six main inputs:

* x1 which is where the line starts
* y1 which is where the line starts
* x2 which is where the line ends
* y2 which is where the line ends
* stroke which is the color of the line
* stroke-width which is the stroke width

The stroke and stroke-width are necessary because an SVG line is dimensionless.

So by applying a stroke-width greater than zero, we can see the line.

The JSON object should have the x1, y1, x2, y2, stroke and stroke-width properties.

```js
var svgContainer = d3.select("body")
  .append("svg")
  .attr("width","200")
  .attr("height","200");
```

First, we define the SVG Container the straight lines will live in.

Note that we define the width and height of the SVG viewport container

```js
var straightLines = [
  { "x1":  0, "y1":  0, "x2": 40, "y2": 40, "stroke":"black", "stroke_width":5 },
  { "x1": 50, "y1": 50, "x2": 90, "y2": 90, "stroke":"black", "stroke_width":5 },
  { "x1":100, "y1":100, "x2":140, "y2":140, "stroke":"black", "stroke_width":5 },
  { "x1":150, "y1":150, "x2":190, "y2":190, "stroke":"black", "stroke_width":5 }
];
```

The straight lines array contains 4 straight line JSON Objects.

This will be the data source used to construct the straight lines

Note that for the stroke_width, we use an underscore to separate the stroke and width words

Why this is important will be seen shortly.

```js
var svgStraightLines = svgContainer
  .selectAll("line")
  .data(straightLines)
  .enter()
  .append("line");
```

This binds each JSON object to an SVG Straight Line DOM element

```js
svgStraightLines
    .attr("x1",           function (d,i) { return d.x1;           })
    .attr("y1",           function (d,i) { return d.y1;           })
    .attr("x2",           function (d,i) { return d.x2;           })
    .attr("y2",           function (d,i) { return d.y2;           })
    .attr("stroke",       function (d,i) { return d.stroke;       })
    .attr("stroke-width", function (d,i) { return d.stroke_width; });
```

We use an anonymous function to extract the relevant information from each JSON object

For the straight line, this means the x1, y1, x2, y2, stroke and stroke-width information.

Note, the stroke-width anonymous function uses the d.stroke {underscore} width.

If we have written stroke {dash} width, then JavaScript would have thought we were trying to do a subtraction.

This is very important to keep in mind as this can often cause bugs in the code.

[D3 Straight Lines in SVG](http://blockbuilder.org/jbelmont/be3d71e582388f97554a0656132b5755)

## Bread Crumb Navigation
_________________________

Previous | Next
:------- | ---:
← [Enter and Append](./enter-and-append.md) | [Scales and Axis](./scales-and-axis.md) →
