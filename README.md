# Creds to vincep5 for this amazing module!
This fork includes the English Premier League, more leagues might be added.

# MMM-MyStandings
MagicMirror module to get ESPN standings for the major US sports including the English Premier League
# MMM-MyStandings
MagicMirror module to get ESPN standings for the major US sports (incl English Premier League). I was inspired by MMM-MyScoreboard and figured that this will compliment it nicely. The module will rotate through different sports. If you only want to show one sport or one division, the module will just display one without rotating.

## API
Uses the ESPN API for sports standings

## Preview
![screenshot1](screenshot2.JPG)
![screenshot1](screenshot1.JPG)

## Installing the module
Go to your MagicMirror modules directory by entering `cd MagicMirror/modules`

run `git clone https://github.com/vincep5/MMM-MyStandings`

if you clone from `https://github.com/vincep5/MMM-MyStandings` copy the MMM-MyStandings.js and standings.njk into the module folder.

## Config
Add `MMM-MyStandings` module to the `modules` array in the `config/config.js` file:
````javascript
modules: [
  {
		module: "MMM-MyStandings",
		position: "top_right",
		config: {
			updateInterval: 60 * 60 * 1000, // every 60 minutes
			rotateInterval: 1 * 60 * 1000, // every 1 minute
			sports: [
				{ league: "NBA", groups: ["Atlantic", "Central", "Southeast", "Northwest", "Pacific", "Southwest"] },
				{ league: "MLB", groups: ["American League East", "American League Central", "American League West", "National League East", "National League Central", "National League West"] },
				{ league: "NFL", groups: ["AFC East", "AFC North", "AFC South", "AFC West", "NFC East", "NFC North", "NFC South", "NFC West"] },
				{ league: "NHL", groups: ["Atlantic Division", "Metropolitan Division", "Central Division", "Pacific Division"] },
				{ league: "MLS", groups: ["Eastern Conference", "Western Conference"] },
				{ league: "Prem", groups: ["English Premier League 2019-2020"]},
				{ league: "NCAAF", groups: ["American Athletic - East", "American Athletic - West", "Atlantic Coast Conference - Atlantic", "Atlantic Coast Conference - Coastal",
										"Big 12 Conference", "Big Ten - East", "Big Ten - West", "Conference USA - East", "Conference USA - West",
										"FBS Independents", "Mid-American - East", "Mid-American - West", "Mountain West - Mountain", "Mountain West - West",
										"Pac 12 - North", "Pac 12 - South", "SEC - East", "SEC - West", "Sun Belt - East", "Sun Belt - West"] }
			],
			nameStyle: "short",
			showLogos: true,
			useLocalLogos: true,
			showByDivision: true,
			fadeSpeed: 2000,
		}
  }
]
````

| Option | Description
| ------- |  -------
| updateInterval | 60 * 60 * 1000 // every 60 minutes <br> Time in milliseconds to update data from ESPN
| rotateInterval | 1 * 60 * 1000 // every 1 minute <br> Time in milliseconds to rotate through the leagues or divisions
| nameStyle | "abbreviation", "full", or <b>"short" </b> <br> Display abbreviation, full name, or short name for the team
| showLogos | <b>true</b> or false <br> Display logos (true) or not (false)
| useLocalLogos | <b>true</b> or false <br> Display logos from folder (true) or display logos from the ESPN url (false) <br> Most of the logos are the same from MMM-MyScoreboard
| showByDivision | <b>true</b> or false <br> Show the standings by division (true) or everything at once (false)
| fadeSpeed | 2000 <br> Time in milliseconds to display the module

Alternate ways of showing sports:
````javascript
		sports: [
			{ league: "NFL" },
			{ league: "NHL", groups: ["Central Division"] }
		]
````
This will rotate ALL NFL and only NHL's Central Division
