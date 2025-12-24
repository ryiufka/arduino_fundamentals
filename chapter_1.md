# Rozdział 1  
## Podłączamy mikrokontroler i sprawdzamy, czy działa  
### pierwszy test: czy komputer i mikrokontroler potrafią się dogadać

[ LAPTOP MIKROKONTROLER ]

---

## Co dziś robimy?

W tym rozdziale zrobimy jedną, bardzo konkretną rzecz.

Nauczymy komputer i mikrokontroler ze sobą współpracować.

Jeśli na końcu rozdziału **dioda zacznie migać**, to znaczy, że wszystko działa i możemy iść dalej.

---

## Najpierw jedno ważne wyjaśnienie

To, co masz w zestawie, to **mikrokontroler na płytce zgodnej z Arduino**.

- **Mikrokontroler** to taki mały komputer posiadający wejścia, wyjścia i pamięć. Może wykonywać zaprogramowane przez nas polecenia
- **Arduino** to otwarty projekt mikrokontrolerów oraz dedykowanego środowiska do ich programowania. Otwarty oznacza, że każdy może wykonać na jego podstawie własne układy zgodne z arduino. Klony to nic innego jak Arduino pod nieoficjalną nazwą i w większości przypadków nie różnią się od oryginałów.

Zazwyczaj na wszystkie mikrokontrolery zgodne z Arduino (klony Arduino) mówimy po prostu Arduino.

Na razie nie musisz tego wszystkiego zapamiętywać.  
Ale przekonajmy się, czy **to działa**.

---

## Krok 1: podłącz mikrokontroler do komputera

Weź:
- mikrokontroler,
- kabel USB A–B.

Podłącz kabel:
- jednym końcem do mikrokontrolera,
- drugim do komputera.

Na płytce powinny zapalić się małe diody.  
To znak, że mikrokontroler dostał prąd.

Jeśli diody świecą, możemy iść dalej.

---

## Krok 2: zainstaluj Arduino IDE

Żeby wysłać program do mikrokontrolera, potrzebujemy jednego programu.
Nazywa się **Arduino IDE**.

### Co robisz:

1. Wejdź na stronę **arduino.cc**
2. Pobierz **Arduino IDE**
3. Zainstaluj jak zwykły program

Nie zmieniaj ustawień.
Klikaj „Dalej”.
To wystarczy.

---

## Krok 3: uruchom Arduino IDE

Po uruchomieniu zobaczysz okno z tekstem.
To normalne.

Na razie nic nie piszemy i niczego nie zmieniamy.

---

## Krok 4: wybierz płytkę i port

Teraz musimy powiedzieć programowi, z jakim mikrokontrolerem ma rozmawiać.

W Arduino IDE:
- wejdź w **Narzędzia → Port**
- wybierz port, do którego jest podpięty mikrokontroler

Jeśli widzisz port z nazwą mikrokontrolera, to znaczy, że komputer go widzi.
To kluczowy moment. Jeśli nie zobaczysz nazwy mikrokontrolera - poproś o pomoc rodzica. Możliwe, że komputer będzie potrzebować pomocy w zrozumieniu co do niego podłączasz (czyli będziecie musieli poszukać sterowników).

Potem:
- wejdź w **Narzędzia → Płytka**
- wybierz **Arduino Uno** (tą samą nazwę, którą zobaczysz wcześniej)

---

## Krok 5: test „Blink”

Na początek nie będziemy nic wymyślać.
Skorzystamy z gotowego testu.

Nazywa się **Blink** i robi jedną rzecz:

> zapala i gasi diodę LED na płytce.

To nie jest program do nauki.
To jest **test połączenia**.

---

### Otwórz gotowy przykład

W menu wybierz:
**Plik → Przykłady → 01.Basics → Blink**

Zobaczysz gotowy kod.
Nic nie zmieniaj.

---

## Krok 6: wgraj program do mikrokontrolera

Kliknij:
- **Sprawdź**,
- a potem **Wgraj**.

Przez kilka sekund:
- program jest wysyłany,
- diody na płytce mogą migać.

To normalne.

---

## Co powinno się wydarzyć?

Na płytce jest mała dioda, najczęściej opisana literą **L**.

Jeśli wszystko poszło dobrze:
- dioda zapala się,
- po chwili gaśnie,
- i robi tak w kółko.

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

Jeśli dioda miga, to znaczy, że komputer i mikrokontroler właśnie się dogadały.

To **najtrudniejszy moment** masz już za sobą.

W następnym rozdziale:
- podłączymy pierwsze elementy,
- i zaczniemy sterować czymś, co sam dołożyłeś do układu.

Idziemy dalej.
