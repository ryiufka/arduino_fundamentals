# Rozdział 2  
## Inteligentna lampka, która wie, kiedy jest ciemno  
### czyli jak mikrokontroler uczy się patrzeć

[ MIKROKONTROLER PŁYTKA_STYKOWA DIODA_LED FOTOREZYSTOR PRZEWODY ]

---

## Co dziś zrobimy?

W tym rozdziale zbudujemy **inteligentną lampkę**.

Będzie działać tak:
- gdy zrobi się ciemno, lampka się włączy  
- gdy zrobi się jasno, lampka się wyłączy  

Nie będziemy nic zgadywać ani naciskać przycisków.  
Lampka **sama podejmie decyzję**.

---

## Jak to w ogóle możliwe?

Mikrokontroler sam z siebie nic nie widzi.  
Ale może dostać **czujnik światła**.

Czujnik światła:
- reaguje na jasność  
- zamienia ją na liczbę  
- a mikrokontroler może tę liczbę porównać  

Jeśli liczba jest mała, to znaczy, że jest ciemno.  
Jeśli duża, to znaczy, że jest jasno.

To nie magia.  
To proste porównywanie wartości.

---

## Co będzie potrzebne?

Z zestawu weź:
- mikrokontroler  
- płytkę stykową  
- diodę LED  
- rezystor do diody  
- fotorezystor  
- rezystor do fotorezystora  
- kilka przewodów  

---

### Jak działa płytka stykowa (w 2 minuty)

Płytka stykowa wygląda jak plastik z dziurkami,
ale w środku ma **ukryte połączenia**.

Jeśli tego nie wiesz, wszystko wydaje się losowe.
Jeśli to wiesz, nagle wszystko zaczyna mieć sens.

---

### Najważniejsza zasada

Dziurki **nie są połączone wszystkie ze sobą**.

Są połączone tylko w **małych grupach**.

---

### Środkowa część płytki

W środkowej części:
- każda **kolumna 5 dziurek** jest połączona razem,
- prąd może płynąć tylko w tej piątce,
- obok już nie.

Czyli:
- włożysz dwa elementy w tę samą kolumnę → są połączone,
- w inną kolumnę → już nie.

To dlatego elementy „trzymają się” razem bez lutowania.

---

### Dwie połówki płytki

Płytka stykowa ma **przerwę pośrodku**.

Ta przerwa jest bardzo ważna:
- elementy po lewej i prawej stronie **nie są połączone**,
- dzięki temu można włożyć układy scalone dokładnie pośrodku.

Na początku po prostu zapamiętaj:
> przerwa = brak połączenia

---

### Długie linie po bokach

Po bokach płytki są długie linie.

W tych liniach:
- wszystkie dziurki w jednej linii są połączone,
- to taki „przedłużacz” dla prądu.

---

### Jedna ważna rzecz

Jeśli coś nie działa, bardzo często:
- element jest w **złej kolumnie**,
- przewód jest **obok, a nie razem**,
- wygląda dobrze, ale **nie jest połączone**.

To normalne.
Każdemu się zdarza.

---

### Jak sprawdzić, czy coś jest połączone?

Zadaj sobie pytanie:
> „Czy te dwa elementy są w tej samej kolumnie (w środku płytki) albo tej samej linii (po bokach)?”

Jeśli tak → są połączone.  
Jeśli nie → nie są.

To wystarczy na początek.

---

## Krok 1: przygotuj płytkę stykową

Połóż płytkę stykową obok mikrokontrolera.  
Wszystkie elementy połączymy **bez lutowania**, tylko na wcisk.
Podłącz 5V i GND z mikrokontrolera do bocznych linii płytki stykowej.
Dzięki temu wszystkie elementy będą miały zasilanie.

---

## Krok 2: podłącz diodę LED

Dioda LED to nasza lampka.
Weź diodę LED i jeden rezystor.

Ważne:
- dioda ma dwie nóżki  
- jedna jest dłuższa, druga krótsza  

Podłącz:
- jedną nóżkę rezystora do pinu cyfrowego mikrokontrolera (np. 8)
- dłuższą nóżkę diody do drugiej nóżki rezystora  
- krótszą nóżkę diody do GND

Na razie dioda się nie świeci.  
To normalne.

---

## Krok 3: podłącz czujnik światła

Fotorezystor zmienia swoje zachowanie w zależności od światła.
Weź fotorezystor i kolejny rezystor.

Podłącz:
- jedną nóżkę fotorezystora do 5V  
- drugą nóżkę fotorezystora do wejścia analogowego A0  
- rezystor między A0 a GND

To połączenie sprawia, że mikrokontroler dostaje liczbę, która mówi mu, jak jasno jest w pokoju.

---

## Krok 4: wgraj program do inteligentnej lampki

Teraz czas na program.

W Arduino IDE wpisz kod do lampki.

```cpp
int ledPin = 8;
int lightSensor = A0;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  int lightLevel = analogRead(lightSensor);

  if (lightLevel < 400) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
}
```

Kliknij **Sprawdź**, a potem **Wgraj**.

---

## Co powinno się wydarzyć?

Zrób test:
- zakryj palcem czujnik światła  
- albo zgaś światło w pokoju  

Dioda powinna się zapalić.

Teraz:
- oświetl czujnik latarką  
- albo zapal światło  

Dioda powinna zgasnąć.

Jeśli tak się dzieje,  
**właśnie zbudowałeś inteligentną lampkę**.

---

## Jeśli coś nie działa

Sprawdź:
- czy dioda LED jest w dobrą stronę  
- czy rezystory są dobrze wpięte  
- czy pin w kodzie zgadza się z pinem na płytce  

Najczęstszy błąd:
„To był inny pin, niż myślałem”.

---

## Co tu się naprawdę wydarzyło?

Mikrokontroler:
- zmierzył światło  
- porównał liczbę  
- podjął decyzję  
- wykonał akcję  

To dokładnie schemat:
**jeśli coś się wydarzy, wykonaj jakąś akcję**.

---

## Spróbuj sam

Poniżej masz kilka eksperymentów.  
Nie musisz robić ich wszystkich. Wybierz jeden albo dwa.

### 1. Lampka nocna
Spraw, żeby lampka:
- zapalała się tylko wtedy, gdy jest **naprawdę bardzo ciemno**  
- w zwykłym półmroku pozostawała zgaszona  

Podpowiedź: zmień wartość 400 w programie.

---

### 2. Alarm przeciwsłoneczny
Zmień działanie lampki tak, żeby:
- zapalała się, gdy jest **za jasno**  
- gasła, gdy światło spadnie  

To już nie będzie lampka, tylko urządzenie alarmujące, że jest zbyt jasno.

Podpowiedź: Zmień < na > w programie

---

### 3. Lampka strachliwa
Zrób lampkę, która:
- zapala się, gdy zrobi się ciemno  
- ale gaśnie dopiero wtedy, gdy zrobi się **bardzo jasno**  

To sprawi, że lampka nie będzie „migać” przy małych zmianach światła.

Podpowiedź: zamiast
```cpp
  } else {
```
wpisz
```
  }
  if (lightLevel > 800) {
```

---

## Co dalej?

W następnym rozdziale zrobimy prosty **instrument muzyczny**  
