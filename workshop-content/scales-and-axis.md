# Data Visualization Workshop - Scales and Axis

## Sections:

* [Scales and Axis](#scales-and-axis)
* [Bread Crumb Navigation](#bread-crumb-navigation)

## Scales and Axis

[D3 Scales Docs](https://github.com/d3/d3-scale)

Key Functions:

[Scale Band](https://github.com/d3/d3-scale#scaleBand)

* Constructs a new band scale with the empty domain, the unit range [0, 1], no padding, no rounding and center alignment.

[Scale Linear](https://github.com/d3/d3-scale#scaleLinear)

* Constructs a new continuous scale with the unit domain [0, 1], the unit range [0, 1], the default interpolator and clamping disabled.

* Linear scales are a good default choice for continuous quantitative data because they preserve proportional differences.

* Each range value y can be expressed as a function of the domain value x: y = mx + b.

[D3 Continuous `domain`](https://github.com/d3/d3-scale#continuous_domain)

* If domain is specified, sets the scale’s domain to the specified array of numbers.
* The array must contain two or more elements.
* If the elements in the given array are not numbers, they will be coerced to numbers.
* If domain is not specified, returns a copy of the scale’s current domain.

```js
var color = d3.scaleLinear()
    .domain([-1, 0, 1])
    .range(["red", "white", "green"]);

color(-0.5); // "rgb(255, 128, 128)"
color(+0.5); // "rgb(128, 192, 128)"
```

[D3 Axis Docs](https://github.com/d3/d3-scale)

[Scales and Axis](http://blockbuilder.org/jbelmont/96f2c14132fb446e839ef8fd9e517267)

Notice in this file that I make a call to `d3.csv`

[d3 request docs for csv and tsv files](https://github.com/d3/d3-request#csv)

* Returns a new request for the CSV file at the specified url with the default mime type text/csv.
* If no callback is specified, this is equivalent to:

```js
d3.request(url)
    .mimeType("text/csv")
    .response(function(xhr) { return d3.csvParse(xhr.responseText, row); });
```

```js
d3.request(url)
    .mimeType("text/csv")
    .response(function(xhr) { return d3.csvParse(xhr.responseText, row); })
    .get(callback);
```

Here is our function in the blockbuilder file

```js
// dataset for city demographics by city
d3.csv('demographic-states-by-city.csv', (err, data) => {
  data.forEach(d => {
    d[COUNT_HISPANICS] = Number(d[COUNT_HISPANICS]) + 0; // y
  });

  // get min/max
  var min = d3.min(data, d => d[COUNT_HISPANICS]);
  var max = d3.max(data, d => d[COUNT_HISPANICS]);
  // or use extent, which gives back [min, max]
  const extent = d3.extent(data, d => d[COUNT_HISPANICS]);

  // try different scales, change the ranges, see what happens
  const yScale = d3.scaleLinear()
    .domain(extent)
    .range([height, 0]);

  // try passing in tick valuess
  const yAxis = d3.axisLeft()
    .scale(yScale);

  const axis = d3.select('svg').append('g')
    .attr('transform', 'translate(40, 20)')
    .call(yAxis);

  const text = axis.selectAll('text')
    .attr('fill', d => d === 35 ? 'blue' : 'green')
});
```

`d3.csv(url, row, callback);`

Notice we provided a url and a callback but not `row`

[Introduction to D3 Scales by Mike Bostock](https://medium.com/@mbostock/introducing-d3-scale-61980c51545f)

**Click `Fork` Button to Play with this on your own**

## Bread Crumb Navigation
_________________________

Previous | Next
:------- | ---:
← [Enter and Append](./enter-and-append.md) | [First Challenge](./first-challenge.md) →
