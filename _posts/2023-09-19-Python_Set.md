---
title: "Python Set"
last_modified_at: 2023-08-16
categories:
  - Eesti, Estonia
tags:
  - Begginer

---

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