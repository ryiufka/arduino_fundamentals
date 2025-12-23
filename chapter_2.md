# Rozdział 2  
## Inteligentna waxlampka, która wie, kiedy jest ciemno  
### czyli jak mikrokontroler uczy się patrzeć

[ TU WSTAW OBRAZEK: Płytka stykowa, dioda LED, fotorezystor, kilka przewodów ]

---

## Co dziś zrobimy?

W tym rozdziale zbudujemy **smart lampkę**.

Będzie działać tak:
- gdy zrobi się ciemno, lampka się włączy  
- gdy zrobi się jasno, lampka się wyłączy  

Nie będziemy zgadywać ani naciskać przycisków.  
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
To po prostu liczenie.

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

[ TU WSTAW OBRAZEK: Elementy potrzebne do projektu ]

---

## Krok 1: przygotuj płytkę stykową

Połóż płytkę stykową obok mikrokontrolera.  
Wszystkie elementy połączymy **bez lutowania**, tylko na wcisk.

---

## Krok 2: podłącz diodę LED

Dioda LED to nasza lampka.

Ważne:
- dioda ma dwie nóżki  
- jedna jest dłuższa, druga krótsza  

Podłącz:
- dłuższą nóżkę diody do rezystora  
- rezystor do pinu cyfrowego mikrokontrolera (np. 8)  
- krótszą nóżkę diody do GND  

[ TU WSTAW OBRAZEK: Podłączenie diody LED z rezystorem ]

Na razie dioda się nie świeci.  
To normalne.

---

## Krok 3: podłącz czujnik światła

Fotorezystor zmienia swoje zachowanie w zależności od światła.

Podłącz:
- jedną nóżkę fotorezystora do 5V  
- drugą nóżkę do wejścia analogowego A0  
- między tę drugą nóżkę a GND podłącz rezystor  

[ TU WSTAW OBRAZEK: Podłączenie fotorezystora jako dzielnika napięcia ]

To połączenie sprawia, że mikrokontroler dostaje liczbę,
która mówi mu, jak jasno jest w pokoju.

---

## Krok 4: wgraj program do smart lampki

Teraz czas na program.

W Arduino IDE wpisz kod do smart lampki.

[ TU WSTAW KOD PROGRAMU SMART LAMPKI ]

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
**właśnie zbudowałeś smart lampkę**.

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

Podpowiedź: zmień wartość graniczną w programie.

[ TU ZMIANA W KODZIE – PRÓG JASNOŚCI ]

---

### 2. Lampka strachliwa
Zrób lampkę, która:
- zapala się, gdy zrobi się ciemno  
- ale gaśnie dopiero wtedy, gdy zrobi się **bardzo jasno**  

To sprawi, że lampka nie będzie „migać” przy małych zmianach światła.

[ TU ZMIANA W KODZIE – DWA RÓŻNE PROGI ]

---

### 3. Alarm przeciwsłoneczny
Zmień działanie lampki tak, żeby:
- zapalała się, gdy jest **za jasno**  
- gasła, gdy światło spadnie  

To już nie jest lampka.
To czujnik.

[ TU ZMIANA W KODZIE – ODWROTNA LOGIKA ]

---

### 4. Licznik dnia i nocy
Zrób program, który:
- zapamięta, ile razy zrobiło się jasno i ciemno  
- po kilku zmianach będzie migał diodą inaczej  

To ćwiczenie uczy pamięci.

[ TU ROZSZERZENIE KODU – ZLICZANIE ZDARZEŃ ]

---

### 5. Lampka z opóźnieniem
Spraw, żeby:
- lampka zapalała się dopiero po kilku sekundach ciemności  
- i gasła dopiero po kilku sekundach światła  

Tak działa wiele prawdziwych urządzeń.

[ TU ROZSZERZENIE KODU – OPÓŹNIENIE CZASOWE ]

---

## Co dalej?

W następnym rozdziale:
- nauczymy mikrokontroler **słuchać**  
- dodamy dźwięk albo przycisk  
- albo sprawimy, że to Ty zdecydujesz, co jest „ciemno”  

Mikrokontroler już patrzy.  
Teraz zacznie reagować.