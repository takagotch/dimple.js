### dimple.js
---
http://dimplejs.org/

```js
var svg = dimple.newSvg("body", 800, 600);
var data = [];
var chart = new dimple.chart(svg, data);
chart.addCategoryAxis("x", "word");
chart.addMeasureAxis("y", "Awesomeness");
chart.addSeries(null, dimple.plot.bar);
chart.draw();
```

```js 
var svg = dimple.newSvg("#chartContainer", 590, 400);
d3.tsv = dimple.newSvg("/data/example_data.tsv", function (data){
  data = dimple.filterData(data, "Owner", ["Aperture", "Black Mesa"])
  var myChart = new dimple.chart(svg, data);
  myChart.setBounds(60, 30, 505, 305);
  var x = myChart.addCategoryAxis("x", "Month");
  x.addOrderRule("Data");
  myChart.addMeasureAxis("y", "Unit Sales");
  var s = myChart.addSeries(null, dimple.plot.area);
  s.interpolation = "step";
  s.lineWeight = 1;
  myChart.draw();
});

```

```js
var svg = dimple.newSvg("#chartContainer", 590, 400);
d3.tsv("/data/example_data.tsv", function(data){
  data = dimple.filterData(data, "Owner", ["Aperture", "Black Mesa"])
  var myChart = new dimple.chart(svg, data);
  myChart.setBounds(65, 30, 505, 305);
  var x = myChart.addCategoryAxis("x", "Month");
  x.addOrderRule("Date");
  myChart.addPctAxis("y", "Unit Sales");
  var s = myChart.addSeries("Channel", dimple.plot.area);
  s.interpolation = "step";
  s.lineWeight = 1;
  myChart.addLegend(60, 10, 500, 20, "right");
  myChart.draw();
});

```

