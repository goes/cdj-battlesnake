---
title: Over JSON
parent: "Stap 2: Het speelbord"
has_children: false
nav_order: 1
---

# 1. Jason? JSON!
Alle informatie over het speelbord zullen we ontvangen in _JSON formaat_, spreek uit als Jason.  
Dat is een manier om structurele gegevens te noteren.  
De J van JSON komt van Javascript, maar elke programmeertaal kan er ondertussen al mee om.  

Hieronder zie je hoe je een CoderDojo'er van 12 jaar oud uit Nazareth, genaamd Ninja met zijn 2 huisdieren in JSON omschrijft:
```json
{
    "naam" : "Ninja",
    "nickname" : null,
    "leeftijd" : 12,
    "coderdojo_lid" : true,
    "lievelingskleuren" : ["wit", "blauw"],
    "woonplaats" : {
        "gemeente" : "Nazareth",
        "postcode" : 9810
    },
    "huisdieren" : [
        {
            "soort" : "konijn",
            "naam" : "Ninja Rabbit"
        },
        {
            "soort" : "egel",
            "naam" : "Ninja Hedgehog",
            "aantal stekels" : 8000
        }
    ]
}
```

We noemen de dingen die we met JSON beschrijven __objecten__.  
In het voorbeeld staan 4 objecten. Zie je dewelke?

Eigenschappen van objecten noemen we __attributen__.
De naam van de attributen wordt de __key__ genoemd en staat telkens tussen aanhalingstekens: ```"..."```.
Tussen 2 attributen staat altijd een ```,``` (komma).

De waarde van die attributen, de __value__, staat soms tussen __" "__ en soms niet. Dat hangt van het __type__ af.    
Dit zijn de types:

| Type | Voorbeeld | Info |
| ---- | --------- | ---- |
| __Number__ | <code lang="json">{"leeftijd" : 12}</code> | |
| __String__ | <code lang="json">{"naam" : "Ninja"}</code> | Met aanhalingstekens |
| __Boolean__ | <code lang="json">{"coderdojo_lid" : true}</code> | ```true``` of ```false``` |
| __Array__ | <code lang="json">"lievelingskleuren" : ["wit", "blauw"]</code> | Een Array is een lijst. Een lege lijst schrijf je als  ```[]```. Gebruik komma's tussen de elementen. In een Array kunnen ook andere objecten zitten, zoals bij de huisdieren. |
| __Object__ | <code lang="json">{"woonplaats" : {...}}</code> | Tussen ```{}```. Woonplaats is dus een object met 2 eigen attributen. |
| __null__ | <code lang="json">{"nickname" : null}</code> | Een lege waarde. Onze Ninja hier heeft dus nog geen nickname :-( |


# 2. BattleSnake JSON
Zo ziet het BattleSnake speelbord er uit in JSON.
In een volgende stap gaan we dit helemaal inlezen en in Python variabelen steken, zodat we er ook iets mee kunnen doen.

Kan je alvast de verschillende _objecten_ die je in het spel tegenkomt terugvinden?  

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
