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
- kilka przewodów  

Najpierw podłącz GND z mikrokontrolera do bocznej linii płytki stykowej.

---

## Krok 1: przygotuj klawiaturę

Każdy przycisk będzie jednym „klawiszem”.

Użyj przycisków tact-switch i włóż je **w poprzek przerwy**
na płytce stykowej.
Dzięki temu przycisk nie będzie cały czas wciśnięty.

Podłącz:
- jedną stronę przycisku do GND,
- drugą stronę przycisku do pinu mikrokontrolera (np. 2, 3, 4, 5).

Nie używamy dodatkowych rezystorów.
Mikrokontroler ma je w środku.

---

## Krok 2: podłącz buzzer

Buzzer to element, który wydaje dźwięk.

Użyj **buzzera pasywnego**  
(buzzer z generatorem gra tylko jeden dźwięk i tutaj się nie nadaje).

Buzzer ma dwie nóżki:
- jedna to sygnał,
- druga to masa (GND).

Podłącz:
- nóżkę sygnałową buzzera do pinu cyfrowego mikrokontrolera (np. 8),
- drugą nóżkę buzzera do GND.

Nie potrzebujesz rezystora.
Buzzer pasywny może być bezpiecznie podłączony bezpośrednio do pinu.

Na razie cisza.  
To dobrze.

---

## Krok 3: wgraj program instrumentu

Teraz czas na program.

Program:
- sprawdza, który przycisk jest wciśnięty,
- przypisuje mu dźwięk,
- i każe buzzerowi zagrać nutę.

W Arduino IDE wpisz kod instrumentu.

```
int buzzerPin = 8;

int key1 = 2;
int key2 = 3;
int key3 = 4;
int key4 = 5;

void setup() {
  pinMode(buzzerPin, OUTPUT);

  pinMode(key1, INPUT_PULLUP);
  pinMode(key2, INPUT_PULLUP);
  pinMode(key3, INPUT_PULLUP);
  pinMode(key4, INPUT_PULLUP);
}

void loop() {

  if (digitalRead(key1) == LOW) {
    tone(buzzerPin, 262);   // C
  }
  else if (digitalRead(key2) == LOW) {
    tone(buzzerPin, 294);   // D
  }
  else if (digitalRead(key3) == LOW) {
    tone(buzzerPin, 330);   // E
  }
  else if (digitalRead(key4) == LOW) {
    tone(buzzerPin, 349);   // F
  }
  else {
    noTone(buzzerPin);
  }
}
```

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
- czy przyciski są włożone w poprzek przerwy w płytce,
- czy piny w kodzie zgadzają się z pinami na mikrokontrolerze.

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

---

## Spróbuj sam

### 1. Zabawa dźwiękami
Zmień wydawane dźwięki i sprawdź jak brzmią

---

### 2. Zagraj melodię
Zrób program, który:
- po naciśnięciu jednego przycisku
- zagra krótką melodię zamiast jednej nuty.

---

### 3. Pianino z większą liczbą klawiszy
Dodaj:
- więcej przycisków,
- więcej dźwięków.

Ile klawiszy da się sensownie obsłużyć?

---

## Co dalej?

W następnym rozdziale zbudujemy mechanizm otwierający drzwi za pomocą karty RFID.
