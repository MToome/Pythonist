---
title: "Python põhi teadmised"
last_modified_at: 2023-08-16
categories:
  - Eesti, Estonia
tags:
  - Begginer

---

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

##### Boolean 
Boolean on väljend, on kaks varjanti kas tõene(True) või vale(False). kui näiteks võrdled kahte väärtust siis pyton hindab seda ja annab Boolean vastuse.
```python
print(1 < 11)
# Väljund True
print(32 < 1)
# Väljund False
```

##### List
Hoiustades mitut väärtust muutujas(variable). Listide puhul kasutatakse nurksulgusid []. 
Pythonis on 4 erinevat sisse ehitatud andme tüübid milles hoiustatakse andmete kogumit, teised on tuples, set ja Dictonary.
List on sorteeritud, muudetav ja võivad olla koopiaid väärtustest. Sorteeritud tähendab, et väärtusid on võimalik leid indexiga. Index on asukoha number. Python alustab lugemist nullist. Indexi abil on võimalik muutujast(variable) välja võtta kindel väärtus ilma andmekogu printimata.
```python
nimekiri = ["leib", "sai", "tomat"]
# Index 0 on leib, 1 on sai ja 2 on tomat
print(type(nimekiri))
# Väljund <class 'tuple'>
```

##### Tuples
Hoiustab samuti mitmeid väärtusid muutujas(variable). Tuplesi puhul kasutatakse sulgusid (). Tuples on sorteeritud ja neid ei ole võimalik muuta.
```python
seetuple = ("leib", "sai", "tomat")
print(type(seetuple))
# Väljund <class 'tuple'
```

##### Set
Hoiustab mitmeid erinevaid tüüpi väärtusi muutujas(variable). Set on organiseerimata, andmeid ei saa muuta, aga saab lisada ja eemaldada väärtusid ja neil puudub index.
Puudub index tähendab, et andmed võivad olla sisestatud _1, 2, 3_ aga salvestatud ja välja tulles võivad olla _2, 1, 3_.
Set puhul kasutatakse looksulge {}. Set ei luba väärtuste koopiaid. Sarnaste väärtuste puhul näiteks kui on _1, 2, 1_ salvetatakse ainult _1, 2_.
```python
# Siin setis on integer, string ja Boolean väärtus.
seeonset = {13, "Tere", True}
# Väljund {'Tere', 13, True}

print(type(seeonset))
# Väljund <class 'set'>

koopiagaset = {"Tere", 1, True, False, 0, "tere"}
# Väljund {'Tere', 1, 'tere' False}
# Suure tähega Tere ei ole võrdne väikse tähega tere, aga 1 on pythonis võrdne True ja 0 on võrdne False 
# see kumb väärtus on andmete sisestamisel eespool see salvetatakse.

# Andmetest on võimalik teha set kasutades set() constructorit.
settegemine = set((12 , "tere", False)) 
# Topelt sulud kuna constructoril kastutades peab kõik olema () vahel 
# ja kuna on nimekiri siis nimekiri peab olema omakorda () vahel.
```