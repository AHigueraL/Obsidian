## Terminado en 2022
```dataviewjs
const selectedYear = 2022
const selectedState = "Finished"

const rawData = dv.pages("#juego").sort(page => page.date)

//rawData.forEach(juego => console.log(juego.date.toString().substr(0,4)))

const data = rawData.filter(d => d.date.toString().substr(0,4) == selectedYear && d.state == selectedState)
const dataLabels = data.map(page => page.file.name).values
const dataDuration = data.map(page => page.estimatedLength).values
const dataPlayed = data.map(page => page.playedHours).values

const chartData = {
	type: 'bar',
	data: {
		labels: dataLabels,
		datasets: [{
			label: 'Duration',
			data: dataDuration,
			backgroundColor: [ 
				'rgba(255, 99, 132, 0.2)' 
			],
			borderColor: [ 
				'rgba(255, 99, 132, 1)' 
			],
			borderWidth: 1
		},
		{
			label: 'Played',
			data: dataPlayed,
			backgroundColor: [ 
				'rgba(255, 0, 132, 0.2)' 
			],
			borderColor: [ 
				'rgba(255, 0, 132, 1)' 
			],
			borderWidth: 1
		}]
	}
}

window.renderChart(chartData, this.container)
```

***

## Terminado en 2023
```dataviewjs
const selectedYear = 2023
const selectedState = "Finished"

const rawData = dv.pages("#juego").sort(page => page.date)

//rawData.forEach(juego => console.log(juego.date.toString().substr(0,4)))

const data = rawData.filter(d => d.date.toString().substr(0,4) == selectedYear && d.state == selectedState)
const dataLabels = data.map(page => page.file.name).values
const dataDuration = data.map(page => page.estimatedLength).values
const dataPlayed = data.map(page => page.playedHours).values

const chartData = {
	type: 'bar',
	data: {
		labels: dataLabels,
		datasets: [{
			label: 'Duration',
			data: dataDuration,
			backgroundColor: [ 
				'rgba(255, 99, 132, 0.2)' 
			],
			borderColor: [ 
				'rgba(255, 99, 132, 1)' 
			],
			borderWidth: 1
		},
		{
			label: 'Played',
			data: dataPlayed,
			backgroundColor: [ 
				'rgba(255, 0, 132, 0.2)' 
			],
			borderColor: [ 
				'rgba(255, 0, 132, 1)' 
			],
			borderWidth: 1
		}]
	}
}

window.renderChart(chartData, this.container)
```