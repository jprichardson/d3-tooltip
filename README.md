JavaScript - d3-tooltip
=======================

This is a JavaScript [d3](http://d3js.org/) tooltip component.


Browserify
----------

    npm install --save d3-tooltip


Component
---------

    component install jprichardson/d3-tooltip



Example
------


```javascript
var d3 = require('d3')
  , d3tooltip = require('d3-tooltip')

var yourDataArray = [.....]

var svg = d3.select('#graph').append('svg')

var tooltip = d3tooltip(d3) //create new tooltip

svg.selectAll("circle")
    .data(yourDataArray)
    .enter()
    .append("circle")
      .attr("r", 3)
      .attr("cx", function(d, i) {
        //return x position, typically you use a scale here
      })
      .attr("cy", function(d) {
        //return y position, could use a scale here as well
      })
      .on("mouseover", function(d) {
        var html = d.toString()

        tooltip.html(html)
        tooltip.show()    
      })
      .on("mouseout", tooltip.hide)
```

Credits
-------

This code is almost exclusively based upon this article: http://www.d3noob.org/2013/01/adding-tooltips-to-d3js-graph.html


License
-------

(MIT License)

Copyright 2013, JP Richardson  <jprichardson@gmail.com>


