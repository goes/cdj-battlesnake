---
title: JSON lezen
parent: "Stap 2: Het spelbord"
has_children: false
nav_order: 3
---

# game.json
Maak nu een nieuw bestand aan en noem het __game.json__.  
Plak er de onderstaande JSON in.
```json
{
  "game": {
    "id": "game-00fe20da-94ad-11ea-bb37",
    "ruleset": {
      "name": "standard",
      "version": "v.1.2.3"
    },
    "timeout": 500
  },
  "turn": 14,
  "board": {
    "height": 11,
    "width": 11,
    "food": [
      {"x": 5, "y": 5}, 
      {"x": 9, "y": 0}, 
      {"x": 2, "y": 6}
    ],
    "hazards": [
      {"x": 3, "y": 2}
    ],
    "snakes": [
      {
        "id": "snake-508e96ac-94ad-11ea-bb37",
        "name": "My Snake",
        "health": 54,
        "body": [
          {"x": 0, "y": 0}, 
          {"x": 1, "y": 0}, 
          {"x": 2, "y": 0}
        ],
        "latency": "111",
        "head": {"x": 0, "y": 0},
        "length": 3,
        "shout": "why are we shouting??",
        "squad": ""
      }, 
      {
        "id": "snake-b67f4906-94ae-11ea-bb37",
        "name": "Another Snake",
        "health": 16,
        "body": [
          {"x": 5, "y": 4}, 
          {"x": 5, "y": 3}, 
          {"x": 6, "y": 3},
          {"x": 6, "y": 2}
        ],
        "latency": "222",
        "head": {"x": 5, "y": 4},
        "length": 4,
        "shout": "I'm not really sure...",
        "squad": ""
      }
    ]
  },
  "you": {
    "id": "snake-508e96ac-94ad-11ea-bb37",
    "name": "My Snake",
    "health": 54,
    "body": [
      {"x": 0, "y": 0}, 
      {"x": 1, "y": 0}, 
      {"x": 2, "y": 0}
    ],
    "latency": "111",
    "head": {"x": 0, "y": 0},
    "length": 3,
    "shout": "why are we shouting??",
    "squad": ""
  }
}
```

# JSON lezen

Open terug het bestand __main.py__, en maak het helemaal leeg.

We moeten het game.json bestand lezen en omzetten in een python-json object.  
Daarvoor importeren we eerst een __library__ genaamd __json__.  
Die library bevat handige code om met json om te gaan.   
```python
import json
```
Imports zoals deze schrijf je bovenaan in het bestand.



Vervolgens moeten we __game.json__ inlezen.  
Daarvoor maak je een __file__ variabele aan voor dat bestand. 
```python
file = open("game.json")
```



Nu kunnen we deze _file_ variabele gebruiken om de json uit het bestand in te laden in een andere variabele die we __game_data__ noemen.
```python
game_data = json.load(file)
```



Om te controleren of dit allemaal gelukt is kan je nog de onderstaande print() lijn toevoegen.
Als alles goed zit dan moet je in de console **game-00fe20da-94ad-11ea-bb37** zien als je nogmaals de __Run >__ knop indrukt.  
Als je goed kijkt is dat de __id__ waarde van het __game__ object in __game.json__.
```python
print(game_data["game"]["id"])
```



--> Kan je in plaats van **game-00fe20da-94ad-11ea-bb37** nu je eigen naam laten verschijnen door het __game.json__ bestand aan te passen?





