---
title: "Tähed ja numbrid arvutis"
last_modified_at: 2023-08-16
categories:
  - Eesti, Estonia
tags:
  - Begginer

---


# Tähed ja numbrid arvutis

Igale tähele vastab arvuti number, et arvuti teaks mis see on. 
ASCII karkteri koodid on numbri koodid mis on määratud tähtedele, sümbolitele ja numbritele kuna see muudab need kümnendsüsteemi, et arvuti neist aru saaks.

Dec  Char| Dec  Char | Dec  Char | Dec  Char    
---------|-----------|-----------|----------
         |  64  @    |  96  `    | 196   Ä 
33  !    |  65  A    |  97  a    | 213   Õ
34  "    |  66  B    |  98  b    | 214   Ö
35  #    |  67  C    |  99  c    | 220   Ü
36  $    |  68  D    | 100  d    | 228   ä
37  %    |  69  E    | 101  e    | 245   õ
38  &    |  70  F    | 102  f    | 246   ö
39  '    |  71  G    | 103  g    | 252   ü
40  (    |  72  H    | 104  h    |    
41  )    |  73  I    | 105  i    |    
42  *    |  74  J    | 106  j    |    
43  +    |  75  K    | 107  k    |
44  ,    |  76  L    | 108  l    |
45  -    |  77  M    | 109  m    |   
46  .    |  78  N    | 110  n    |
47  /    |  79  O    | 111  o    |
48  0    |  80  P    | 112  p    |
49  1    |  81  Q    | 113  q    |
50  2    |  82  R    | 114  r    |
51  3    |  83  S    | 115  s    |
52  4    |  84  T    | 116  t    |
53  5    |  85  U    | 117  u    |
54  6    |  86  V    | 118  v    |
55  7    |  87  W    | 119  w    |
56  8    |  88  X    | 120  x    |
57  9    |  89  Y    | 121  y    |
58  :    |  90  Z    | 122  z    |
59  ;    |  91  [    | 123  {    |
60  <    |  92  \    | 124  |    |
61  =    |  93  ]    | 125  }    |
62  >    |  94  ^    | 126  ~    |
63  ?    |  95  _    | 127  DEL  |

### ord()

ASCII numbri saamiseks on pythonil lihtne sisse ehitatud funktsioon _ord()_.

```python
print(ord("A"))
# Väljund 65
```

### chr()

ASCII numbri muutmine täheks, numbriks või sümboliks saab kasutada pythonisse sisse ehitatud koodi _chr()_

```python
print(chr(65))
# Väljund A
```