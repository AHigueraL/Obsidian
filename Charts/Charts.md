Put this in the middle of this ``` ``` (shown only on Edit Mode) to display a chart 
```
chart
    type: ""
    labels: []
    series:
        - title: ""
        data: []
        - title: ""
        data: []

```

```md
|       | Test1 | Test2 | Test3 |
| ----- | ----- | ----- | ----- |
| Data1 | 1     | 2     | 3.33  |
| Data2 | 3     | 2     | 1     |
| Data3 | 6.7   | 4     | 2     |
^table
```

|       | Test1 | Test2 | Test3 |
| ----- | ----- | ----- | ----- |
| Data1 | 1     | 2     | 3.33  |
| Data2 | 3     | 2     | 1     |
| Data3 | 6.7   | 4     | 2     |
^table

````md
```chart
type: bar
id: <blockId>
layout: rows
width: 80%
beginAtZero: true
```
````

- Choose the column or row oriented layout using the `layout` attribute. Options are `rows` or `columns`.
- (Optional) Select the Columns or Rows with the `select` attribute. E.g. to only show Row `Data2` add `select: [Data2]`

```chart
type: bar
id: table
layout: rows
width: 80%
beginAtZero: true
```

## Other types
````yaml
```chart
    type: bar
    labels: [Monday,Tuesday,Wednesday,Thursday,Friday, Saturday, Sunday, "next Week", "next Month"]
    series:
        - title: Title 1
          data: [1,2,3,4,5,6,7,8,9]
        - title: Title 2
          data: [5,4,3,2,1,0,-1,-2,-3]
```
````

```chart
type: bar
labels: [Monday,Tuesday,Wednesday,Thursday,Friday, Saturday, Sunday, "next Week", "next Month"]
series:
    - title: Title 1
	  data: [1,2,3,4,5,6,7,8,9]
    - title: Title 2
	  data: [5,4,3,2,1,0,-1,-2,-3]
```

## Modifiers
## `width` Modifier

The `width` Modifier is used to set the width of **any** Chart. It is advised to use it for the following Charts:

- Pie Chart
- Doughnut Chart
- Radar Chart
- Polar Area Chart

The Values can be any valid CSS Property, for examples fixed Values (e.g. `400px`) or dynamic Values (e.g `40%`).

- Default: `100%`

### Example

````yaml
```chart
type: polarArea
labels: [Monday,Tuesday,Wednesday,Thursday,Friday]
series:
    - title: Title 1
    data: [1,2,3,4,5]
    - title: Title 2
    data: [5,4,3,2,1]
width: 40%
```
````

## `fill` Modifier

The `fill` Modifier is used in Line Charts to fill the Area under the Traces.

- Expected: `boolean` (`true` or `false`)
- Default: `false`

### Example

````yaml
```chart
    type: line
    labels: [Monday,Tuesday,Wednesday,Thursday,Friday]
    series:
        - title: Title 1
        data: [1,2,3,4,5]
        - title: Title 2
        data: [5,4,3,2,1]
        - title: Title 3
        data: [8,2,5,-1,4]
    fill: true
```
````

## `bestFit` Modifiers

The `bestFit` Modifier is used in Line Charts to generate a line of best fit for the given line.

- Expected: `boolean` (`true` or `false`)
- Default: `false`

The `bestFitTitle` Optional modifier is used with `bestFit` to specify a title for the line of best fit.

- Expected: `string`
- Default: `Line of Best Fit`

The `bestFitNumber` Optional modifier is used with the `bestFit` modifier to specify a line for `bestFit` to use.

- Expected: `integer` (`0` for the first line, `1` for the second line, ...)
- Default: `0`

### Example

````yaml
```chart
    type: line
    labels: [Monday,Tuesday,Wednesday,Thursday,Friday]
    series:
        - title: Title 1
        data: [1,2,3,4,5]
        - title: Title 2
        data: [5,4,3,2,1]
        - title: Title 3
        data: [8,2,5,-1,4]
    bestFit: true
    bestFitTitle: "Best Fit Title!"
    bestFitNumber: 1
```
````

## `spanGaps` Modifier

The `spanGaps` Modifier is used to fill in missing Datapoints.

- Expected: `boolean` (`true` or `false`)
- Default: `false`

### Example

````yaml
```chart
    type: line
    labels: [Monday,Tuesday,Wednesday,Thursday,Friday]
    series:
        - title: Title 1
        data: [1,2,null,4,5]
        - title: Title 2
        data: [5,null,null,null,1]
        - title: Title 3
        data: [8,2,5,-1,4]
    spanGaps: true
```
````

## `tension` Modifier

The `tension` Modifier is used in Line Charts to set the tension of the Traces to the given points. A Value of 0 means no smoothness at all, a value of 1 is maximum smoothness.

- Expected: Double (0-1)
- Default: 0

### Example

````yaml
```chart
    type: line
    labels: [Monday,Tuesday,Wednesday,Thursday,Friday]
    series:
        - title: Title 1
        data: [1,2,3,4,5]
        - title: Title 2
        data: [5,4,3,2,1]
        - title: Title 3
        data: [8,2,5,-1,4]
    tension: 0.5
```
````

## `beginAtZero` Modifier

The `beginAtZero` Modifier is used to force set the Chart to begin at 0. Otherwise the Chart will cut out all unused space.

- Expected: `boolean` (`true` or `false`)
- Default: `false`

### Example

````yaml
```chart
    type: line
    labels: [Monday,Tuesday,Wednesday,Thursday,Friday]
    series:
        - title: Title 1
        data: [4,2,3,4,5]
        - title: Title 2
        data: [5,4,3,2,2]
        - title: Title 3
        data: [8,2,5,3,4]
    beginAtZero: true
```
````

## `legend` Modifier

The `legend` modifier sets whether or not the legend will be displayed.

- Expected: `boolean` (`true` or `false`)
- Default: `true`

### Example

````yaml
```chart
    type: line
    labels: [Monday,Tuesday,Wednesday,Thursday,Friday]
    series:
        - title: Title 1
        data: [4,2,3,4,5]
        - title: Title 2
        data: [5,4,3,2,2]
        - title: Title 3
        data: [8,2,5,3,4]
    legend: false
```
````

## `legendPosition` Modifier

Determines where the legend will be displayed.

- Expected `top`, `left`, `bottom`, `right`
- Default: `top`

## Axes Modifiers

Valid for `bar` and `line` types only.

### `indexAxis` Modifier

Allows horizontal graphs.

- Expected: `x` or `y`
- Default: `x`

### `stacked` Modifier

Will change the bar and line graphs to be stacked.

- Expected: `boolean` (`true` or `false`)
- Default: `false`

### Modifiers by Axis

Prepend either the x or y axis to any of these to modify them.

#### `Title` Modifier

Use either `xTitle: "Title here"` or `yTitle: "Title here"` to add a Title to any Axis.

#### `Reverse` Modifier

Can reverse the axis it is applied to

- Expected: `boolean` (`true` or `false`)
- Default: `false`

````yaml
```chart
    type: line
    labels: [Monday,Tuesday,Wednesday,Thursday,Friday]
    series:
        - title: Title 1
        data: [4,2,3,4,5]
        - title: Title 2
        data: [5,4,3,2,2]
        - title: Title 3
        data: [8,2,5,3,4]
    xReverse: true
```
````

### `Min` and `Max` Modifiers

Can set the min and max of the respecitve axis (like: `xMax` or `yMin`). `Min` will override beginAtZero.  
Use `rMax` to set the max for radar and polar area charts.

- Expected: `int`

### `Display` and `TickDisplay` Modifiers

Determines whether the axis (`Display`) or the ticks of the axis (`TickDisplay`) are visible.

- Expected: `boolean` (`true` or `false`)
- Default: `true`

## `time` Modifier

If you use e.g. dates on your X Axis, you can set the `time` modifier to automatically format them.

- Expected: `string` (`day`, `week`, `month`, `year`, etc.)

## `transparency` Modifier

You can override the inner color of your Chart's elements using the `transparency` Modifier.

- Expected: `float` (`0.0` - `1.0`)
- Default: `0.25`

## Dataview integration
Dataview Integration

If you want to use this Plugin in combination with Plugins like Dataview, I recommend using the API. When this Plugin is enabled, you can render a Chart using the following:

```js
window.renderChart(data, element);
```

There are some full Examples:

## Get data from current page

````md
test:: First Test
mark:: 6

```dataviewjs
const data = dv.current()

const chartData = {
    type: 'bar',
    data: {
        labels: [data.test],
        datasets: [{
            label: 'Grades',
            data: [data.mark],
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        }]
    }
}

window.renderChart(chartData, this.container);
```
````

or you can use with `charts` Codeblock

````md
test:: First Test
mark:: 6

```dataviewjs
const data = dv.current()

dv.paragraph(`\`\`\`chart
    type: bar
    labels: [${data.test}]
    series:
    - title: Grades
      data: [${data.mark}]
\`\`\``)
```
````

## Get data from multi-pages

````md
```dataviewjs
const pages = dv.pages('#test')
const testNames = pages.map(p => p.file.name).values
const testMarks = pages.map(p => p.mark).values

const chartData = {
    type: 'bar',
    data: {
        labels: testNames,
        datasets: [{
            label: 'Mark',
            data: testMarks,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1,
        }]
    }
}

window.renderChart(chartData, this.container)
```
````

The data is the standard [Chart.js](https://www.chartjs.org/docs/latest/) data payload, you can use everything it supports in there.