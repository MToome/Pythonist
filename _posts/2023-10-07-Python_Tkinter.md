---
title: "Python Tkinter"
last_modified_at: 2023-10-07
categories:
  - Eesti, Estonia
tags:
  - Begginer

---

# Tkinter

Tkinter on python library grafiliste kasutaja liideste(GUI) tegemisteks. See pakub  erinevaid tööriistu ja vidinaid mis võimaldavad luua töölaua rakendusi grafilise liidesega. Tkinter on algaja sõbralik ja lihtsalt mõistetav. Tkinter on samas suhteliselt algeline võrreldes kaasaegsete GUI library tega nagu PyQt või Kivy. Tkinter on avatud lähtekoodiga tänu millele leiab otsides palju infot selle kasutamiseks.  Kokkuvõtlikult Pythoni Tkinterist:

1. Grafiliste kasutaja liideste(GUI) arendamine: Tkinter kasutatakse GUI rakenduste tegemiseks töölauaplatvormide jaoks nagu macOS, Windows ja Linux.

```python
import tkinter as tk

root = tk.Tk()
root.title("Tere, Tkinter!")
root.mainloop()

```

2. Tkinter on kaasas Pythoniga niiet seda ei ole vaja eraldi installida ja saab lihtsalt kasutada erinevatel operatsiooni süsteemidel ilma muudatusi tegemata. Selle kasutamiseks on vaja library kõiges importida.

```python
# Import Tkinter impordib Tkinter library ja as tk teeb nii, et ei peaks pikalt kirjutama vaid piisab tk.
import Tkinter as tk

# Siin määratakse tk muutujale root, et saaks suhelda rakenduse aknaga ja seda muuta kasutades root muutujat 
root = tk.Tk()

# Rakendusele määratakse pealkirjaks "Tere, Tkinter!"
root.title("Tere, Tkinter!")

# Ekraanile rakenduse kuvamiseks peab kutsuma lõpus mainloop
root.mainloop()
```

3. Tkinter pakub erinevaid vidinaid nagu nuput, sildid, teksti aknad, märkekastid, raadio nupud ja palju muud millega saab luua kasutaja liidese rakendusele.

```python
import tkinter as tk

root = tk.Tk()
# Loob sildi: "Tere, Tkinter!"
label = tk.Label(root, text="Tere, Tkinter!")
# Loob nupu kirjaga: " Vajuta mind!"
button = tk.Button(root, text="Vajuta mind!")
# Kutsub sildi(muidu ei ilmuks silti)
label.pack()
# Kutsub nupu(muidu ei ilmuks nuppu)
button.pack()
root.mainloop()

```

4. Tkinterit saab kasutada sündmuse juhitud rakenduste loomiseks. Luues funktsiooni mis haldab mingit sündmust(sündmuse haldur) reageerides mingi nuppu vajutusele või hiire liikumisele. 

```python
import tkinter as tk

# Sündmuse haldur
def button_click():
  # Nuppu vajutades muudab sildi ära:"Nuppule vajutati"
    label.config(text="Nupule vajutati")
    
root = tk.Tk()
label = tk.Label(root, text="Hello, Tkinter!")
# Siin on määratud, et peale nupule vajutamist kutsub funktsiooni nuppule vajutatud
button = tk.Button(root, text="Click Me", command=button_click)
label.pack()
button.pack()
root.mainloop()
```

5. Tkinter pakub erinevaid vahendeid rakenduses vidinate ja teksti paigutus haldamiseks(Geoometry Managers). 

```python
import tkinter as tk
# Siin näite kasutamiseks peab kustutama või kommentaarideks tegema teised kaks lahendust,
# näiteks kui soovite packi proovida siis grid ja place tulev välja võtta
root = tk.Tk()
root.title("Geometry Managers Example")

# Kasutades pack geometry manager, text näitab mis on peal kirjas, bg mis on tausta värv ja fg mis on kirja värv
label1 = tk.Label(root, text="Pack 1", bg="red", fg="white")
# Kasutades pack siis tuleb määrata side, varjandid on left, right, top või bottom, 
# kasutades anchor saab kinnitada selle teatud orientatsiooni kasutades ilmakaari n(põhi), ne(kirre), e(ida), se(kagu), s(lõuna), sw(edel), w(lääs), nw(loe)
label1.pack(side="left", anchor="nw")


label2 = tk.Label(root, text="Pack 2", bg="green", fg="white")
label2.pack(side="right")

label3 = tk.Label(root, text="Pack 3", bg="blue", fg="white")
label3.pack(side="top")

# Kasutades grid geometry manager
label3 = tk.Label(root, text="Grid 1", bg="blue", fg="white")
# Grid puhul kasutatakse tupli(column) ja rida(row) paigutamiseks
label3.grid(row=0, column=2)

label4 = tk.Label(root, text="Grid 2", bg="orange", fg="white")

label4.grid(row=1, column=2)

# Kasutades place geometry manager
label5 = tk.Label(root, text="Place 1", bg="purple", fg="white")
# Kasutatakse x ja y telgi mis algavad vasakult ülevalt
label5.place(x=50, y=100)

label6 = tk.Label(root, text="Place 2", bg="pink", fg="white")
label6.place(x=100, y=150)

root.mainloop()

```

6. Tkinteril on võimalik mitmeid aspekte muuta rakendusel

```python
import tkinter as tk

root = tk.Tk()
# Siin font määrab tektsi tüübi ja suuruse ja fg teksti värvi
label = tk.Label(root, text="Hello, Tkinter!", font=("Helvetica", 16), fg="blue")
label.pack()
root.mainloop()
```

7. Tkinter saab ühendada teiste library tega, et luua keerulisemaid rakendusi nagu graafikud, andmebaasi sissepääs ja neti ühendus.

```python
# Selles näites on ühendatud matplotlib ja Tkinter tabeli kuvamiseks
import tkinter as tk
from tkinter import ttk
import matplotlib.pyplot as plt
from matplotlib.backends.backend_tkagg import FigureCanvasTkAgg

# Loob Tkinteri akna
root = tk.Tk()
root.title("Tkinter ja Matplotlib tabel")

# Loob raami tabeli kuvamiseks
frame = ttk.Frame(root)
frame.pack(padx=10, pady=10)

# Loob matplotlib kujundi
fig, ax = plt.subplots(figsize=(6, 4), dpi=80)
ax.set_title("Näite tabel")

# Näite andmed
x_values = [1, 2, 3, 4, 5]
y_values = [10, 15, 7, 12, 8]

# tulba tabeli loomine matplotlib abil
ax.bar(x_values, y_values)

# Loob Tkinteri Canvase andmete kuvamiseks
canvas = FigureCanvasTkAgg(fig, master=frame)
canvas_widget = canvas.get_tk_widget()
canvas_widget.pack()

# Kuvab tabeli
root.mainloop()
```

