---
title: De klasse Board
parent: "Stap 2: Het speelbord"
has_children: false
nav_order: 4
---

# board.py
Maak nu een nieuw bestand aan en noem het __board.py__.  
Als alles goed zit hebben we nu devolgende structuur in ons project:
```
|_ main.py
|_ board.py
|_ game.json
```

Nu begint het echte werk!
Open __board.py__.

We gaan een klasse Board maken die alle nodig gegevens van het speelbord kent, en die het bord ook kan printen in de console.
Een klasse maak je om een aantal variabelen op een gestructureerde manier bij elkaar te houden, maar een klasse kan ook bepaalde functies bevatten die vanalles met die variabelen kunnen doen.

Een goed voorbeeld is een klasse __Persoon__ met variabele __geboortedatum__ en een functie __leeftijd()__.
Die functie kan dan aan de hand van de geboortedatum berekenen hoe oud de persoon is.


Een klasse maak je met het sleutelwoord ```class```.
Klassenamen beginnen altijd met een hoofdletter.  
De klasse voor on speelbord wordt dus:  
```python
class Board:
```


Het speelbord in het spel heeft een breedte en een hoogte, en dat zijn 2 variabelen die perfect bij onze klasse passen.  
Om te beginnen gaan we doen alsof het bord altijd 5 vakjes breed is en 8 vakjes hoog.  
Daarom gaan we het bord __initialiseren__ met die variabelen.

Daarvoor maken we een __method__ aan met een speciale naam die we niet zelf kunnen kiezen:```def __init__(self):```.
```python
class Board:

    def __init__(self):
        self.height = 8
```

```def``` betekent dat er een methode aankomt, en tussen de haakjes ```()``` komt altijd ```self```.  
Een methode eindigt ook altijd op een ```:```.

LET OP! In Python is het belangrijk dat je 4 spaties inspringt als je een ```method``` binnen een ```class``` definieert.
Ook de code binnen de ```method``` moet telkens 4 spaties inspringen.

In ons voorbeeld wordt de hoogte ```self.height``` op de waarde 8 gezet.
```self``` betekent hier dat het een variabele van de klasse is.

--> Stel nu ook de breedte van het bord in op 5 vakjes in de variabele ```width``` .


# Een Board gebruiken
Nu we in bestand __board.py__ een klasse ```Board``` met een ```width``` en een ```height``` hebben, kunnen we dat bord gaan gebruiken in ons programma.

Open terug main.py en voeg een extra import lijn toe bovenaan.  

```python
from board import Board
```

Hiermee kunnen we onze klasse Board gaan gebruiken.

Dat doen we door een nieuw Board in een variabele te steken.

```python
new_board = Board()
```

Eens dat gebeurd is, kunnen we ```new_board``` gebruiken en bijvoorbeeld de hoogte en breedt printen in de console.

```python
print(new_board.height)
```

--> Probeer nu main.py aan te passen zodanig dat je niet de naam van het spel print, maar wel de volgende output krijgt.
De '5' en '8' mag je niet zomaar intikken, maar moet je van je new_board variabele halen. 
```
Hoogte: 8
Breedte: 5
```
