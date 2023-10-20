# Playing
```dataview
TABLE
estimatedLength as Duration, playedHours as "Played hours", date as Date
from #Juego
where file.name != "TJuego" AND state = "Playing"
sort date
```

***

# Played
## 2022
```dataview
TABLE
estimatedLength as Duration, playedHours as "Played hours", date as Date
from #Juego
where file.name != "TJuego" AND date <= 202212
sort date
```

```dataviewjs
const selectedYear = 2022

const rawData = dv.pages("#juego").sort(page => page.date)

//rawData.forEach(juego => console.log(juego.date.toString().substr(0,4)))

const data = rawData.filter(d => d.date.toString().substr(0,4) == selectedYear)
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

## 2023
```dataview
TABLE
estimatedLength as Duration, playedHours as "Played hours", date as Date
from #Juego
where file.name != "TJuego" AND date > 202212
sort date
```

```dataviewjs
const selectedYear = 2023

const rawData = dv.pages("#juego").sort(page => page.date)

//rawData.forEach(juego => console.log(juego.date.toString().substr(0,4)))

const data = rawData.filter(d => d.date.toString().substr(0,4) == selectedYear)
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

# Finished
## 2022
```dataview
TABLE
estimatedLength as Duration, playedHours as "Played hours", date as Date
from #Juego
where file.name != "TJuego" AND state = "Finished" AND date <= 202212
sort date
```

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

## 2023
```dataview
TABLE
estimatedLength as Duration, playedHours as "Played hours", date as Date
from #Juego
where file.name != "TJuego" AND state = "Finished" AND date > 202212
sort date
```

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

***

# On Hold
## 2022
```dataview
TABLE
estimatedLength as Duration, date as Date
from #Juego
where file.name != "TJuego" AND state = "On Hold" AND date <= 202212
sort date
```

## 2023
```dataview
TABLE
estimatedLength as Duration, date as Date
from #Juego
where file.name != "TJuego" AND state = "On Hold" AND date > 202212
sort date
```

***

# Backlog
|Title|
|---|
|[[30xx]]|
|[[20xx]]|
|[[3D Classics]]|
|[A Dark Place](https://farawaytimes.itch.io/a-dark-place)|
|[[A Good Snowman]]|
|[[A Hat In Time]]|
|[[A Monster's Expedition]]|
|[[A Void Hope]]|
|[[AI: The Somnium Files]]|
|[[Alephant]]|
|[[Annalyn]]|
|[[Another World]]|
|[[Antonblast]]|
|[[Ara Fell]]|
|[[Art Of Rally]]|
|[[Assemble With Care]]|
|[[Baten Kaitos]]|
|[[Below]]|
|[[Black & White]]|
|[[Bomberman Story DS]]|
|[[Bonfire Peaks]]|
|[[Boyfriend Dungeon]]|
|[[Bug Fables: The Everlasting Sapling]]|
|[[Bugsnax]]|
|[[Captain Toad]]|
|Cassette Beasts|
|Caves of Qud|
|Chained Echoes|
|Chants Of Sennar|
|Citizen Sleeper|
|Corponation|
|Cosmic Express|
|Cosmic Star Heroine|
|Deadlink|
|Death Stranding|
|Deca Police|
|Demonschool|
|Digimon World Re: Digitize|
|Doom|
|Dragon Quest Monsters|
|Dragon Quest V|
|Dwarf Fortress|
|El Paso, Elsewhere|
|Elden Ring|
|Electroplankton|
|Entropy Center|
|Etrian Odyssey|
|EverOasis|
|F-Zero|
|Fallout: New Vegas|
|FIGHT’N RAGE|
|Flashback|
|flOw|
|Fortnite Zero Build|
|Frog Detective|
|Ghostwire: Tokyo|
|Gunstar Heroes|
|Hohokum|
|Homura|
|Hotel Dusk|
|Humanity|
|Hypnospace Outlaw|
|Ihatovo Monogatari|
|Immortality|
|Inazume Eleven|
|Kanto Expansion Pak|
|Katamari Damacy|
|Keepsake County|
|Konkan Coast Pirate Solutions|
|L.A. Noire|
|Langrisser|
|Last Bible III|
|Leximan|
|Little Inferno|
|Live A Live|
|Loddlenaut|
|Lonely Mountains Downhill|
|Luigi's Mansion|
|Maquette|
|Mario & Luigi Superstar Saga|
|Mario and Donkey Kong: Minis On The Move|
|Megaman Battle Network|
|Miitopia|
|Mother 2|
|Mudrunner|
|Myst|
|Neon White|
|NeverAwake|
|Ni No Kuni (NDS)|
|Nioh|
|Nocturnal|
|Nonary Games|
|Noora and the Time Studio|
|Norco|
|Octopath Traveler II|
|Olija|
|One Step From Eden|
|Oriental Blue|
|OutRun|
|OutRun 2|
|Oxenfree|
|Panzer Dragoon Saga|
|Paradise Killer|
|Passage|
|Patapon|
|Patrick's Parabox|
|Pentinent|
|Persona 2: Eternal Punishment|
|Phantom Brave|
|Pipe Dream (GB)|
|Pokémon Conquest|
|Pokémon Renegade Platinum|
|PowerSlave Exhumed|
|Prince Of Persia|
|Prinny 2|
|Punch Club|
|Pushmo|
|Quest Master|
|Ratatan|
|Ray'Z Arcade Chronology|
|Rayman|
|Red Dead Redemption|
|Resident Evil 4 HD Project|
|Return To Monkey Island (y otros que sean canon)|
|Rhapsody: A Musical Adventure|
|Risk Of Rain Returns|
|Rollerdrome|
|Rytmos|
|Sacrifire|
|SEGA 3D Classics|
|Shadows of Adam|
|Shenmue|
|Sifu|
|Signalis|
|Sokobond|
|SokoChess White|
|Solar Ash|
|Soma Bringer|
|Sonic Frontiers|
|Sonic Mania|
|Sonic Origins|
|Soul Hackers|
|Soulvars|
|Sound Shapes|
|Space Warlord Organ Trading Simulator|
|Spider-Man: Miles Morales|
|SRB2|
|Stacklands|
|Stranger Of Paradise|
|Stray Gods: The Roleplaying Musical|
|Stuffo the Puzzle Bot|
|Sunday Gold|
|Sunshine Shuffle|
|Super Mario Bros. Ultra Deluxe|
|Super Princess Peach|
|Super Space Club|
|System Shock|
|Teardown|
|Telling Lies|
|The Case of the Golden Idol|
|The Denpamen|
|The Friends Of Ringo Ishikawa|
|The Master's Pupil|
|The Secret Of Monkey Island|
|The World Ends With You|
|Toads Of The Bayou|
|Tokimeki Memorial|
|Trombone Champ|
|Tunic|
|Valkyrie Profile: Covenant Of The Plume|
|Vampire Survivors|
|Venba|
|Viewtiful Joe|
|Virtua Cop 2|
|Wario Ware Gold|
|Welcome To Nivalis|
|Whisker Squadron: Survivor|
|Who's Lila|
|Windosill|
|Wipeout|
|World Of Horror|
|Xenoblade Chronicles 3|
|Yokai Watch|
|Ys VI|