# Leaflet.d3chart

Leaflet.d3chart is a leaflet plugin for adding to a leaflet map small animated bar charts, pie charts or polar area charts.

It can be used to visualize multiple variables associated to geographical coordinates and to look at the evolution of these variables.

## Examples

```js
var center = [48.861415, 2.349326];

var mymap = L.map('map').setView(coord, 13);
L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(mymap);

// Let us generate fake data
function fakeData() {
  return [Math.Random(), Math.random(), Math.random()];
}

// Create a barchart
var myBarChart = L.d3chart(center, {data: fakeData()});
mymap.addLayer(myBarChart);

// Update data every 2 seconds
setInterval(function() {
  myBarChart.setOptions({data: fakeData()})
}, 2000);
```

![Example of a barchart on a map](img/example_barchart.gif)