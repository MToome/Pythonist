---
title: "Moodulid Pythonis"
last_modified_at: 2023-08-16
categories:
  - Eesti, Estonia
tags:
  - Begginer
---

# Moodulid Pythonis

Pythonis on andme pakkid mida kutsutakse mooduliteks. Moodulites on  Pytoni määratlused ja avaldused. Moodul saab määrata funktsiooni, klassi ja muutujat. Moodulis saab olla ka valmis kood. Sarnased koodi on modulisse kokku pandud, et muuta kood lihtsamini arusaadavaks ja kasutatavaks. Ühtlasi muudab see koodi loogiliselt organiseerituks.

### Näide moodulist

Lihtne näide moodulist on arvutamine, liitmine ja lahutamine.

```python
# defineerime mis saab kui kutsume liitmine
def liitmine(a, b):
    return a + b

# defineerime mis saab kui kutsume lahutamine
def lahutamine(a, b):
    return a - b
```

Selliselt on kood salvestatud moodulites. Mida saab enda koodi importida ja siis kasutada ilma, et ise peaks kulutama aega selle kirjutamisele. Kui ise salvestada see kood faili nimega _arvuta.py_ siis saad hiljem seda importida seda ka teistesse projektidesse.

### Mooduli importimine

Mooduli saamiseks projekti on vaja kõigepeal moodul importida. Seda tuleb teha programmi alguses. Võimalik on importida kogu moodul või siis osa moodulist. Osa moodulist võib tahta importida selleks, et kood ei läheks liiga suureks.

```python
# Mooduli importimine
import arvuta

# Väljund on 3
print(arvuta.liitmine(1, 2))
```

Moodulit võid nimetada ükskõik kuidasd, aga sellel peab olema faili lisa _.py_ .
Ühtlasid on võimalik oma projektis moodul ümber nimetada, et ei peaks pikalt kirjutama.
```python
# Nimetab ümber aruta ar-iks
import aruta as ar

# Kasutamiseks tuleb kutsuda ar
print(ar.liitmine(1, 2))
```

Kirjutades mitu sada rida koodi on hea kui saab kuskil trükkimis vaeva vähendada.

### Sisseehitatud moodulid

Pythonis on väga palju moodule mis on sisseehitatud pythonisse. 
Näiteks on olemas calc moodul. 

```python
# Impordime calc mooduli
import calc

# Väljund 3
print(calc.add(1, 2))
```

### Functsioonid moodulis

Mooduli funtsioonide nimekirja saamiseks on vaja kasutada _dir()_ funktsiooni.

```python
# Impordime mooduli
import math

# Prindime funktsioonid nimekirja
print(dir(math))

"""
Väljund
['__doc__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'cbrt', 'ceil', 'comb', 'copysign', 'cos', 'cosh', 'degrees', 'dist', 'e', 'erf', 'erfc', 'exp', 'exp2', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf', 'isclose', 'isfinite', 'isinf', 'isnan', 'isqrt', 'lcm', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'nextafter', 'perm', 'pi', 'pow', 'prod', 'radians', 'remainder', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau', 'trunc', 'ulp']
"""
```