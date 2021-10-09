---
title: Een Board printen
parent: "Stap 2: Het spelbord"
has_children: false
nav_order: 5
---

# Het bord printen
Om te zien of het spelbord correct in je programma zit gaan is het handig als je het in de console kan printen.
Je zou een functie kunnen maken in __main.py__ dat het bord print, maar je hebt al een klasse ```Board``` die alle informatie over dat spelbord bevat, dus maak het printen als methode in die klasse.


Als eerste versie gaan we per vakje op van het bord een # printen.
Maak een methode in klasse ```Board```
```python
class Board: 
    
    ...

    def print(self):
        print("Een bord.")
``` 

Roep nu ```new_board.print()``` op in __main.py__ en er verschijnt "Een bord." in de console.

Maar we willen net iets meer natuurlijk.
Gebruik de variabelen ```self.height``` en ```self.width``` en programmeer het printen zo dat je devolgende output krijgt:
```
# # # # #
# # # # #
# # # # #
# # # # #
# # # # #
# # # # #
# # # # #
# # # # #
```

<details>
  <summary>Tip</summary>
<div class="code-example" markdown="1">
`for x in ...` en `range(n)` kunnen hier van pas komen.
</div>
</details>

<details>
  <summary>Lukt het niet? Klik hier om een oplossing te zien.</summary>
<div class="code-example" markdown="1">
```python
      def print(self):
        for h in range(self.height):
            line = ''
            for w in range(self.width):
              line = line + '# '
            print(line)
```
</div>
</details>

# Beter bord
Zo'n bord met hashtags ziet er een beetje saai uit.  
Maak er nu wat meer een "vakjesbord" van. Met de nodige plaats om later op zo'n vakje een eigenschap te kleven: hier is eten, hier is een slang, ...

Pas nu je `print()` methode aan zodat je een output als hieronder krijgt.  
Kijk goed: je print afwisselend 2 verschillende soorten lijnen nu.
```
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
|   |   |   |   |   |
+---+---+---+---+---+
```
<details>
  <summary>Lukt het niet? Klik hier om een oplossing te zien.</summary>
<div class="code-example" markdown="1">
```python
    def print(self):
        for h in range(self.height):
            separator_line = '+'
            line = '|'
            for w in range(self.width):
              separator_line = separator_line + '---+'
              line = line + '   |'
            print(separator_line)
            print(line)
        print(separator_line)
```
</div>
</details>

