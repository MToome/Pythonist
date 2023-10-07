---
title: "Moodulid Pythonis"
last_modified_at: 2023-09-17
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
# defineerib mis saab kui kutsub liitmine
def liitmine(a, b):
    return a + b

# defineerib mis saab kui kutsub lahutamine
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
Näiteks on olemas _math_ moodul. 

```python
# Impordib math mooduli
import math

# Kutsub math.pi, et teada saada π väärtus.
print(math.pi)
# Väljund 3.141592653589793
```

Sisseehitatud moodulite nimekirja saab kui kirjutada _help('modules')_. See annab terve nimekirja moodulitest mis on saadaval. Ühtlasi saab teada ka moodulite kohta lisa infot nii _help('math')_, väljundiks on nimekiri käsklustest ja kirjeldus mida need teevad.

### Pythoni välised moodulid

Pythoni üks populaarsuse põhjused on ka selles, et pythoni ühiskond loob ise mooduleid mida teised saavad kasutada. Nende moodulite saamiseks on vaja need kõigepealt endale installida ning siis saab neid kasutada nagu sisseehitatud mooduleid.
Moodul tuleb installida terminalis.
```console
pip install matplotlip
```
Peale seda saab seda importida.
```python
import matplotlip
```
### Functsioonid moodulis

Mooduli funtsioonide nimekirja saamiseks on vaja kasutada _dir()_ funktsiooni.

```python
# Impordib mooduli
import math

# Prindib funktsioonide nimekirja
print(dir(math))

"""
Väljund
['__doc__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'cbrt', 'ceil', 'comb', 'copysign', 'cos', 'cosh', 'degrees', 'dist', 'e', 'erf', 'erfc', 'exp', 'exp2', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf', 'isclose', 'isfinite', 'isinf', 'isnan', 'isqrt', 'lcm', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'nextafter', 'perm', 'pi', 'pow', 'prod', 'radians', 'remainder', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau', 'trunc', 'ulp']
"""
```