# Data Visualization Workshop

## Sections:

* [What is Data Visualization](#what-is-data-visualization)
* [Types of Visual Diagrams](#types-of-visual-diagrams)
* [D3 API Docs](#d3-api-docs)
* [List of D3 Modules](#list-of-d3-modules)
* [Selections, Data, and Demo](workshop-content/selections.md)
* [Enter and Append](workshop-content/enter-and-append.md)
* [Scales and Axis](workshop-content/scales-and-axis.md)
* [First Challenge](workshop-content/first-challenge.md)
* [Shapes](workshop-content/shapes.md)
* [Second Challenge](workshop-content/second-challenge.md)
* [Enter and Update](workshop-content/enter-and-update.md)
* [Exit and Merge](workshop-content/exit-and-merge.md)
* [Transitions](workshop-content/transitions.md)
* [Third Challenge](workshop-content/third-challenge.md)
* [Force Layout](workshop-content/force-layout.md)
* [D3 and Vuejs](workshop-content/d3-and-vuejs.md)
* [Data Visualization Best Practices](#data-visualization-best-practices)
* [General Data Visualization Resources](#general-data-visualization-resources)
* [Data Visualization Experts and Companies](#data-visualization-experts-and-companies)

## What is Data Visualization

* Data visualization is the presentation of data in a pictorial or graphical format.
* It enables decision makers to see analytics presented visually
* Decision makers can then grasp difficult concepts or identify new patterns.
* With interactive visualization, you can take concepts further and teach concepts better.
  * You can drill down into charts and graphs for more detail,
  * and interactively change what data you see and how it’s processed.

## Types of Visual Diagrams

A diagram is a symbolic representation of information according to some visualization technique.

### Bar Charts

[Bar Chart](https://en.wikipedia.org/wiki/Bar_chart)

* A bar chart or bar graph is a chart or graph that presents categorical data with rectangular bars with heights or lengths proportional to the values that they represent.
* The bars can be plotted vertically or horizontally.
* A vertical bar chart is sometimes called a line graph.

![Bar Chart](images/bar-chart.png)

### Line Charts

[Line Chart](https://en.wikipedia.org/wiki/Line_chart)

* A line chart or line graph is a type of chart which displays information as a series of data points called 'markers' connected by straight line segments.
* It is a basic type of chart common in many fields.
* It is similar to a scatter plot except that the measurement points are ordered (typically by their x-axis value) and joined with straight line segments.
* A line chart is often used to visualize a trend in data over intervals of time – a time series – thus the line is often drawn chronologically.

![Line Chart](images/line-chart.png)

## Scatter Plots

[Scatter Plots](https://en.wikipedia.org/wiki/Scatter_plot)

* A scatter plot (also called a scatter graph, scatter chart, scattergram, or scatter diagram) is a type of plot or mathematical diagram using Cartesian coordinates to display values for typically two variables for a set of data.
* If the points are color-coded, one additional variable can be displayed.
* The data is displayed as a collection of points, each having the value of one variable determining the position on the horizontal axis and the value of the other variable determining the position on the vertical axis

![Scatter Plots](images/scatter-plot.png)

## D3 API Docs

D3 4.0 is a [collection of modules](https://github.com/d3) that are designed to work together
* You can use the modules independently, or you can use them together as part of the default build.
* The source and documentation for each module is available in its repository.

Follow the links below to learn more:

* [Introduction](https://d3js.org/#introduction)
* [API Reference](https://github.com/d3/d3/blob/master/API.md)
* [Release Notes](https://github.com/d3/d3/blob/master/CHANGES.md)
* [Gallery](https://github.com/d3/d3/wiki/Gallery)
* [Examples](http://bl.ocks.org/mbostock)
* [Tutorials](https://github.com/d3/d3/wiki/Tutorials)
* [Plugins](https://github.com/d3/d3/wiki/Plugins)
* [d3.js on Stack Overflow](http://stackoverflow.com/questions/tagged/d3.js)
* [d3-js Google Group](http://groups.google.com/group/d3-js)
* [d3-js Slack Channel](https://d3js.slack.com) ([Invite](https://d3-slackin.herokuapp.com/))
* [d3-js Gitter Channel](https://gitter.im/d3/d3)
* d3-js IRC Channel => #d3.js on irc.freenode.net

## List of D3 Modules

#### Data space

* query
 * d3-request
 * d3-queue

* generation
 * d3-random

* parsing
 * d3-dsv
 * d3-time

* formatting
 * d3-time-format
 * d3-format

* manipulation
 * d3-array
 * d3-collection


#### Graphic space

* data transform
 * d3-scale
 * d3-geo-projection

* geometry computation
 * d3-voronoi
 * d3-hull
 * d3-quadtree
 * d3-interpolate
 * d3-geo

* dynamic geometry computation
  * d3-transition
  * d3-timer
  * d3-ease

* visual variables mapping
 * d3-hierarchy
 * d3-sankey
 * d3-chord
 * d3-hexbin
 * d3-force

* generation
 * d3-shape
 * d3-path
 * d3-polygon

* converter
 * d3-color

#### View space

* visual variables mapping (selection, data-binding, attributes)
 * d3-selection
 * d3-selection-multi

* high level set of visual variables mapping (component)
 * d3-axis

#### Interaction space

* internal events
 * d3-dispatch

* user events and geometry computation
 * d3-zoom
 * d3-brush
 * d3-drag

## Data Visualization Best Practices

There is a wonderful illustration in this [Tableau White Paper](https://www.tableau.com/sites/default/files/media/whitepaper_visual-analysis-guidebook_0.pdf) on Data Visualization Best Practices

## General Data Visualization Resources

* **[Dashing D3js](https://www.dashingd3js.com/table-of-contents)**
* **[Visualizing Data](http://www.visualisingdata.com)** -  a fantastic blog about data visualization. In particular, check out:
* **[The Visualizing Data Resource List](http://www.visualisingdata.com/index.php/resources/)** - A massive list of data visualization tools
* **[The Visualizing Data Dataset List](http://www.visualisingdata.com/index.php/references/)** - *click on 'Data Sources'*.  A list of interesting public data sets.
* **[Flowing Data](http://flowingdata.com)** - another data visualization blog.
* **[Information Aesthetics](http://infosthetics.com)** - Another good blog.

### Data Visualization Experts and Companies
* **[Jer Thorp](http://blog.blprnt.com)** - Data artist.
* **[Nicolas Feltron](http://feltron.tumblr.com)** - Data artist.
* **[Stamen](http://stamen.com)** - Data visualization company, excellent blog, heavy focus on maps.
* **[Fathom](http://fathom.info/latest/)** - Another interesting data visualization company.
* **[Shirley Wu](http://sxywu.com/)** - Excellent blog on Data Visualization.
