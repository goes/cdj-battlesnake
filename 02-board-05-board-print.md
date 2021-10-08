---
title: Een Board printen
parent: "Stap 2: Het speelbord"
has_children: false
nav_order: 5
---

# Het bord printen
Om te zien of het spelbord correct in je programma zit gaan is het handig als je het in de console kan printen.
Je zou een functie kunnen maken in __main.py__ dat het bord print, maar je hebt al een klasse ```Board``` die alle informatie over dat speelbord bevat, dus maak het printen als methode in die klasse.


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
  <summary>:bulb: Tip</summary>
```for x in ...``` en ```range(n)``` kunnen hier van pas komen.
</details>

<details>
  <summary>Lukt het niet? Klik hier om een oplossing te zien.</summary>
  <code>
      def print(self):
        for h in range(self.height):
            line = ''
            for w in range(self.width):
              line = line + '# '
            print(line)
  </code>
</details>