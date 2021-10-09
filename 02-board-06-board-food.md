---
title: Eten toevoegen
parent: "Stap 2: Het speelbord"
has_children: false
nav_order: 6
---

# Matrix
Het bord tot nu toe is tamelijk leeg.  
In deze stap ga je het wat meer inhoud geven.  We gaan namelijk naast lege vakjes ook vakjes met voedsel zien.

Zoals je weet hebben we in Python ook __arrays__ of lijsten.
Een speelbord kan je ook zien als een array, maar dan wel een array van arrays.

Als de hoogte 8 is, en de breedte 5, dan hebben we hier een array van 8 andere arrays. Zoiets wordt ook wel een matrix genoemd, of een 2-dimensionale of 2D-array.
Vaak wordt ook gezegd: deze matrix heeft 8 **rijen** (rows) en 5 **kolommen** (columns).
```json
[
  [1,2,3,4,5],
  [1,2,3,4,5],
  [1,2,3,4,5],
  [1,2,3,4,5],
  [1,2,3,4,5],
  [1,2,3,4,5],
  [1,2,3,4,5],
  [1,2,3,4,5]
]
```

Met zo'n constructie kan je gemakkelijk elk vakje in het bord benaderen met coordinaten.
Opgelet: het eerste element van een array in python is schrijf je zo [0]. Het eerste is het nulde dus.

Voeg nu bij `Board` in de `__init__` methode een nieuwe variabele `cells` (vakjes) toe.
Je kan dat met onderstaande code doen.
Let op de `None`, dat is een speciale waarde in Python: een "lege waarde".  
Dat betekent dat we hier een 2d-array van `nr_rows` rijen en `nr_columns` kolommen maken en dat we in elk vakje van die 2d-array `None` steken, letterlijk niets dus.

```python
self.cells = [[None for i in range(nr_rows)] for j in range(nr_columns)]
```

# Voedsel toevoegen
Nu je een spelbord met vakjes hebt, kan je eindelijk beginnen met het vullen met de vakjes.  
Maak daarvoor een methode in `Board` genaamd `add_food`.

Roep deze methode ook op in `__init__`, na het initialiseren van de variabelen.
```python
    def __init__(self):
        ...
        cels = ...

        self.add_food()
```

In `add_food` voeg je nu voedsel toe aan het bord door de waarde __'F'__ te zetten in de `cells` matrix.
Probeer nu in elk hoekje van je bord een 'F' te zetten. In totaal staan ga je dus 4 vakjes met een 'F' hebben.
```python
cells[3][7] = 'F'
```

# Voedsel printen
Je hebt nu voedsel toegevoegd, maar hoe weet je of je dat juist hebt gedaan?  
Je programma print namelijk nog steeds een leeg bord.  
Pas daarom de `print()` methode aan zodat hij de 'F' print als er voedsel in het vakje ligt.
De vakjes waar niks (of dus `None`) ligt moeten leeg blijven.  

:bulb: `None` is speciaal, je kan `None` namelijk niet aan een string plakken met de `+` operator waarmee je strings samenplakt.
Probeer dit maar eens, het zal je een crash opleveren: *TypeError: can only concatenate str (not "NoneType") to str*

```python
value_1 = None
value_2 = 'F'
print(value_1 + ' ' + value_2 + '.')
```
Het kan daarom handig zijn om een speciale methode aan te maken waarin je het omzetten van een waarde van een vakje naar een string regelt.  
'F' blijft 'F', maar None moet bv een '' spatie worden. Deze `if ... is ... else ... ` is een manier om dat te doen, met als voordeel dat als de waarde die je meegeeft al een string is, die waarde zal behouden worden, terwijl er een spatie komt als de waarde `None` is.
```python
value_1 = None
value_1_string = ' ' if value_1 is None else value_1
value_2 = 'F'
print(value_1_string + ' ' + value_2  + '.')
```

:point_right: Je programma zou nu een bord moeten printen dat er zo uit ziet. Lukt dat?
```
+---+---+---+---+---+
| F |   |   |   | F |
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
| F |   |   |   | F |
+---+---+---+---+---+
```

:point_right: Probeer ook nog eens of alles werkt als je de hoogte en breedte van je spelbord verandert in de __init__ methode.

<details>
  <summary>Lukt het niet? Klik hier om een oplossing te zien.</summary>
<div class="code-example" markdown="1">
```python
    def add_food(self):
        self.cells[0][0] = 'F'
        self.cells[self.width-1][self.height - 1] = 'F'
        self.cells[self.width-1][0] = 'F'
        self.cells[0][self.height - 1] = 'F'

    def print(self):
        for h in range(self.height):
            separator_line = '+'
            line = '|'
            for w in range(self.width):
              cell_value = self.cells[w][h]

              separator_line = separator_line + '---+'
              line = line + ' '
              line = line + (' ' if cell_value is None else cell_value)
              line = line + ' |'
            print(separator_line)
            print(line)
        print(separator_line)
```
</div>
</details>


