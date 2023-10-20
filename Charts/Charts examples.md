```dataviewjs
let pages = dv.pages("#juego")
dv.header(1, "Lista en js")
dv.table(["File", "Duration"], pages.map(page => [page.file.name, page.estimatedLength]))
```

```dataviewjs
const data = dv.pages("#juego").sort(page => page.date)
const dataLabels = data.map(page => page.file.name).values
const dataPoints = data.map(page => page.estimatedLength).values

const chartData = {
	type: 'bar',
	data: {
		labels: dataLabels,
		datasets: [{
			label: 'Duration',
			data: dataPoints,
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

window.renderChart(chartData, this.container)
```

```dataviewjs
let pages = dv.pages("#juego")
dv.header(1, "Lista en js")
dv.paragraph(dv.markdownTable(["File", "Duration"], pages.map(page => [page.file.name, page.estimatedLength])))
```

`= round(104/1.1)`