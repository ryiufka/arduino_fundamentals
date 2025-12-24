# Rozdział 3  
## Instrument muzyczny, na którym da się grać  
### czyli uczymy mikrokontroler wydawać dźwięki

[ MIKROKONTROLER PŁYTKA_STYKOWA BUZZER_PASYWNY PRZYCISK ]

---

## Co dziś zrobimy?

W tym rozdziale zbudujemy **instrument muzyczny**.

Będzie działać trochę jak pianino:
- każdy przycisk to inny dźwięk,
- po naciśnięciu przycisku słychać nutę,
- po puszczeniu zapada cisza.

To nie będzie fortepian koncertowy.  
Ale **melodie da się zagrać**.

---

## Skąd bierze się dźwięk?

Dźwięk to drgania powietrza.  
Im szybciej coś drga, tym wyższy dźwięk słyszysz.

Buzzer to mały głośniczek, który:
- potrafi drgać bardzo szybko,
- a mikrokontroler może mu powiedzieć, **jak szybko ma drgać**.

Różne prędkości drgań to różne dźwięki.

---

## Co będzie potrzebne?

Z zestawu weź:
- mikrokontroler  
- płytkę stykową  
- buzzer pasywny (ten z generatorem gra tylko jeden dźwięk)
- 4 przyciski  
- 4 rezystory  
- kilka przewodów  

---

## Krok 1: przygotuj klawiaturę

Każdy przycisk będzie jednym „klawiszem”.

Podłącz przyciski do płytki stykowej tak, żeby:
- jeden pin przycisku był połączony z masą (GND),
- drugi pin był podłączony do wejścia mikrokontrolera,
- rezystor zapobiegał przypadkowemu włączaniu.

---

## Krok 2: podłącz buzzer

Buzzer będzie wydawał dźwięk.

Podłącz:
- jeden pin buzzera do pinu cyfrowego mikrokontrolera,
- drugi pin do GND.

Na razie cisza.  
To dobrze.

---

## Krok 3: wgraj program instrumentu

Teraz czas na program.

Program:
- sprawdza, który przycisk jest wciśnięty,
- przypisuje mu dźwięk,
- i każe buzzerowi zagrać nutę.

W Arduino IDE wklej kod instrumentu.

[ TU WSTAW KOD PROGRAMU INSTRUMENTU ]

Kliknij **Sprawdź**, a potem **Wgraj**.

---

## Co powinno się wydarzyć?

Naciśnij przycisk:
- powinieneś usłyszeć dźwięk.

Naciśnij inny przycisk:
- powinien być inny dźwięk.

Jeśli:
- każdy przycisk gra inną nutę,
- dźwięk znika po puszczeniu,

to znaczy, że **instrument działa**.

---

## Jeśli coś nie gra

Sprawdź:
- czy buzzer jest dobrze podłączony,
- czy przyciski mają rezystory,
- czy piny w kodzie zgadzają się z pinami na płytce.

Najczęstszy problem:
„Gra cały czas” albo „nie gra wcale”.

To prawie zawsze kwestia przycisku.

---

## Co tu się naprawdę wydarzyło?

Mikrokontroler:
- sprawdził, czy przycisk jest wciśnięty,
- wybrał odpowiedni dźwięk,
- włączył drgania buzzera,
- i wyłączył je, gdy puściłeś klawisz.

To dokładnie ten sam schemat, co wcześniej:
**jeśli coś się wydarzy, zrób coś**.

Tylko że teraz:
- „coś się wydarzy” to naciśnięcie klawisza,
- „zrób coś” to zagranie dźwięku.

---

## Spróbuj sam

Wybierz jeden pomysł i spróbuj go zrealizować.

### 1. Pianino z większą liczbą klawiszy
Dodaj:
- więcej przycisków,
- więcej dźwięków.

Ile klawiszy da się sensownie obsłużyć?

---

### 2. Zagraj melodię
Zrób program, który:
- po naciśnięciu jednego przycisku
- zagra krótką melodię zamiast jednej nuty.

---

### 3. Instrument perkusyjny
Zmień wydawane dźwięki tak, żeby:
- jeden przycisk był „bębnem”,
- inny „hi-hatem”,
- jeszcze inny „klaskaniem”.

To już nie pianino.  
To perkusja.

---

### 4. Instrument reagujący na czas
Spraw, żeby:
- im dłużej trzymasz przycisk,
- tym dłużej albo głośniej gra dźwięk.

---

## Co dalej?

W następnym rozdziale zbudujemy mechanizm otwierający drzwi za pomocą karty RFID.
