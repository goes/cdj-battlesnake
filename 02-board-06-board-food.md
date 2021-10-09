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
