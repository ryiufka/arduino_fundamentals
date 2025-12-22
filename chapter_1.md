# Rozdział 1  
## Podłączamy mikrokontroler i sprawdzamy, czy działa  
### pierwszy test: czy komputer i mikrokontroler potrafią się dogadać

[ TU WSTAW OBRAZEK: Mikrokontroler, kabel USB A–B, komputer ]

---

## Co dziś robimy?

W tym rozdziale zrobimy jedną, bardzo konkretną rzecz.

Sprawdzimy, czy:
- komputer,
- kabel,
- program Arduino,
- i mikrokontroler

potrafią ze sobą współpracować.

Jeśli na końcu **dioda zacznie migać**, to znaczy, że wszystko działa  
i możemy iść dalej.

---

## Najpierw jedno ważne wyjaśnienie

To, co masz na biurku, to **mikrokontroler na płytce zgodnej z Arduino**.

- **Mikrokontroler** to mały komputer, który wykonuje program.
- **Arduino** to nazwa programu i gotowych przykładów,  
  z których korzystamy, żeby było prościej.

Na razie nie musisz tego zapamiętywać.  
Wystarczy, że zobaczysz, że **to działa**.

---

## Krok 1: podłącz mikrokontroler do komputera

Weź:
- mikrokontroler,
- kabel USB A–B.

Podłącz kabel:
- jednym końcem do mikrokontrolera,
- drugim do komputera.

[ TU WSTAW OBRAZEK: Mikrokontroler podłączony do laptopa ]

Na płytce powinny zapalić się małe diody.  
To znak, że mikrokontroler dostał prąd.

Jeśli diody świecą, możemy iść dalej.

---

## Krok 2: zainstaluj Arduino IDE

Żeby wysłać program do mikrokontrolera,
potrzebujemy jednego programu.

Nazywa się **Arduino IDE**.

### Co robisz:
1. Wejdź na stronę **arduino.cc**
2. Pobierz **Arduino IDE**
3. Zainstaluj jak zwykły program

[ TU WSTAW OBRAZEK: Strona Arduino IDE / instalator ]

Nie zmieniaj ustawień.
Klikaj „Dalej”.
To wystarczy.

---

## Krok 3: uruchom Arduino IDE

Po uruchomieniu zobaczysz okno z tekstem.
To normalne.

Na razie nic nie piszemy  
i niczego nie zmieniamy.

---

## Krok 4: wybierz płytkę i port

Teraz musimy powiedzieć programowi,
z jakim mikrokontrolerem ma rozmawiać.

W Arduino IDE:
- wejdź w **Narzędzia → Płytka**
- wybierz **Arduino Uno**

[ TU WSTAW OBRAZEK: Menu wyboru płytki ]

Potem:
- **Narzędzia → Port**
- wybierz port, który się pojawił

[ TU WSTAW OBRAZEK: Menu wyboru portu ]

Jeśli widzisz port,
to znaczy, że komputer widzi mikrokontroler.

To kluczowy moment.

---

## Krok 5: test „Blink”

Na początek nie będziemy nic wymyślać.
Skorzystamy z gotowego testu.

Nazywa się **Blink**  
i robi jedną rzecz:

> zapala i gasi diodę LED na płytce.

To nie jest program do nauki.
To jest **test połączenia**.

---

### Otwórz gotowy przykład

W menu wybierz:
**Plik → Przykłady → 01.Basics → Blink**

[ TU WSTAW OBRAZEK: Menu z przykładem Blink ]

Zobaczysz gotowy kod.
Nic nie zmieniaj.

---

## Krok 6: wgraj program do mikrokontrolera

Kliknij:
- **Sprawdź**,
- a potem **Wgraj**.

[ TU WSTAW OBRAZEK: Przyciski Sprawdź i Wgraj ]

Przez kilka sekund:
- program jest wysyłany,
- diody na płytce mogą migać.

To normalne.

---

## Co powinno się wydarzyć?

Na płytce jest mała dioda,
najczęściej opisana literą **L**.

Jeśli wszystko poszło dobrze:
- dioda zapala się,
- po chwili gaśnie,
- i robi tak w kółko.

[ TU WSTAW OBRAZEK: Migająca dioda LED na płytce ]

To znaczy, że:
- komputer wysłał program,
- mikrokontroler go odebrał,
- i wykonuje dokładnie to, co dostał.

---

## Jeśli dioda nie miga

Spokojnie. To się zdarza.

Sprawdź:
- czy wybrałeś właściwą płytkę,
- czy wybrałeś port,
- czy kabel USB jest dobrze podłączony.

W większości przypadków problem jest właśnie tutaj.

---

## Co właśnie osiągnąłeś?

Jeśli dioda miga, to znaczy, że:
- komputer,
- kabel,
- program Arduino,
- i mikrokontroler

właśnie się dogadały.

To **najtrudniejszy moment** masz już za sobą.

W następnym rozdziale:
- podłączymy pierwsze elementy,
- i zaczniemy sterować czymś,
  co sam dołożyłeś do układu.

Idziemy dalej.