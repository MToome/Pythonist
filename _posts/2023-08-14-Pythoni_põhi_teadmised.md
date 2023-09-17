---
title: "Python põhi teadmised"
last_modified_at: 2023-08-16
categories:
  - Eesti, Estonia
tags:
  - Begginer

---



# Print

print() saab ekraanile kuvada erinevt infot. Stringid ehk reas tähed käivad juttumärkides, numbrid ja muutujate nimetajad ei pea olema juttumärkides.

```python
print("Tere")
# Kuvab ekraanile: Tere

print(3)
# Kuvab ekraanile: 3
```


# Kommentaar

Kommentaar algab pythonis trellide ehk numbrimärkidega #. Lõik mis alga trellidega pythoni koodis programm ei loe.
Hea jätta endale märge kus midagi jäi poolikuks või debugimiseks lõik koodist välja võtta, kirjutada mida mingi koodi lõik teeb
Mitme realise kommetaari tegemiseks võib kasutada kolmik juttu märke """  """.
```python
"""
Mitme 
realine
kommentaar
"""

```

# Help

Pythonis on võimalik kasutada _help()_ funktsiooni, see näitab dokumente moodulite, funktsioonide, klasside, võtmesõnade ja paljude muude asjade kohta.
```python
# Kutsub help() funktsiooni
help(print)
"""
Väljund:
Help on built-in function print in module builtins:

print(*args, sep=' ', end='\n', file=None, flush=False)
    Prints the values to a stream, or to sys.stdout by default.

    sep
      string inserted between values, default a space.
    end
      string appended after the last value, default a newline.
    file
      a file-like object (stream); defaults to the current sys.stdout.
    flush
      whether to forcibly flush the stream.
"""
```


# Muutuja
# Variable

Muutujaga manipuleerimine on üks võimsamaid asju programeerimises. Muutujaid kasutatakse andmete hoiustamiseks. 
Muutujatele saab määrata erinevaid nimesid, mis on koostatud tähtedest, numbritest ja alakriipsust. 
Muutujatele määratakse andmeid võrdusmärgiga (=).
Andmed on näiteks 1, 2, 3 või "Hello World". Andmetel on tüübid: numbrid, string, Boolean, nimekiri jne. 
```python
x = 4
nimi = "Toomas"
```

### Tüübid
### Types

Tüüpe saab küsida tõlgi käest:
```python
print(4)
# Väljund 4
# Tüübi teada saamiseks tuleb kirjutada:
print(type(4))
# Väljund <class 'int'>
print(type("Hello"))
# Väljund <class 'str'>
```
##### String ehk Str
Tähed ja laused on string(str) kuna on tähtede rida(string of letters). String tunneb ära sellest, et on juttumärkides ' ' või " "(ei ole vahet kumba juttumärki kasutad pythoni kirjutamisel peaasi, et kasutada kogu aeg samu ja teisi saad kasutada lausetes, et programm ei loeks seda). Numbrid ja märgid mis on juttumärkides on samuti str.
```python
print("Mati ütles:'Tere tulemast'")
# Väljund Mati ütles: 'Tere tulemast', kasutasin topelt juttumärke stringi tegemiseks ja lause jaoks ühekordseid
print(type("Hello World"))
# Väljund <class 'str'>
print(type("12"))
# Väljund <class 'str'>, kuna on juttu märkides
```

##### Integer ehk int
Integer ehk int on ilma koma kohata number. Pythonis tehakse vahet kas on koma koht või mitte. Näiteks 1 on int 1.0 on float

##### Floating point ehk float
Floating point ehk float on number koma kohaga. 

```python
print(type(5))
# Väljund <class 'int'>
print(type(10 000))
# Väljund <class 'int'>
print(type(5.0))
# Väljund <class 'float'>
print(type(10 000.1))
# Väljund <class 'float'>
```

