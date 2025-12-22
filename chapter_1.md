# Rozdział 1  
## Podłączamy mikrokontroler do komputera  
### czyli sprawdzamy, czy to naprawdę działa

[ TU WSTAW OBRAZEK: Mikrokontroler, kabel USB, laptop ]

---

## Zanim zaczniemy

Na pudełku i w internecie często pojawia się słowo **Arduino**.

To ważne, ale trzeba to uporządkować.

To, co masz w ręku, to **mikrokontroler na płytce zgodnej z Arduino**.
Mikrokontroler to mały komputer, który potrafi sterować rzeczami.

**Arduino** to nazwa projektu i programu, z którego będziemy korzystać,
żeby mówić mikrokontrolerowi, co ma robić.

To trochę jak z grą:
gra nazywa się Minecraft,
ale możesz w nią grać na różnych komputerach.

My będziemy robić tak:
- mówimy **mikrokontroler**, gdy chodzi o sprzęt,
- mówimy **Arduino**, gdy chodzi o program i przykłady.

I to w zupełności wystarczy.

---

## Po co w ogóle ten rozdział?

Zanim zaczniemy podłączać diody, czujniki i silniki,
musimy sprawdzić jedną prostą rzecz.

Czy komputer potrafi porozumieć się z mikrokontrolerem.

Jeśli to zadziała, reszta będzie już tylko ciekawsza.

---

## Krok 1: podłącz mikrokontroler do komputera

Weź mikrokontroler i kabel USB.

Podłącz kabel do płytki,
a drugi koniec do komputera.

[ TU WSTAW OBRAZEK: Mikrokontroler podłączony do laptopa ]

Na płytce powinny zapalić się małe diody.
To znak, że mikrokontroler dostał prąd
i że wszystko jest w porządku.

---

## Krok 2: zainstaluj Arduino IDE

Żeby wysyłać programy do mikrokontrolera,
potrzebujemy jednego programu.

Nazywa się **Arduino IDE**.

To jest:
- miejsce do pisania prostych programów,
- narzędzie, które wysyła je do mikrokontrolera.

Co robisz:
1. Wejdź na stronę **arduino.cc**
2. Pobierz **Arduino IDE**
3. Zainstaluj jak zwykły program

[ TU WSTAW OBRAZEK: Strona Arduino IDE i instalator ]

Nie zmieniaj żadnych dziwnych opcji.
Klikaj dalej.
To wystarczy.

---

## Krok 3: uruchom Arduino IDE

Po uruchomieniu zobaczysz okno z tekstem.

To normalne.
To jest po prostu program do pisania programów.

Na razie nic nie zmieniamy.

---

## Krok 4: wybierz płytkę i port

Teraz musimy powiedzieć programowi,
z jakim mikrokontrolerem ma rozmawiać.

W Arduino IDE:
- wejdź w menu **Narzędzia → Płytka**
- wybierz **Arduino Uno**

[ TU WSTAW OBRAZEK: Menu wyboru płytki ]

Potem:
- **Narzędzia → Port**
- wybierz port, który się pojawił

[ TU WSTAW OBRAZEK: Menu wyboru portu ]

Jeśli widzisz port,
to znaczy, że komputer widzi mikrokontroler.

To jest ważny moment.

---

## Krok 5: pierwszy program

Na początek nie będziemy nic wymyślać.

Skorzystamy z gotowego programu,
który zna każdy, kto zaczyna przygodę z elektroniką.

Nazywa się **Blink**.

Ten program robi tylko jedną rzecz.
Włącza i wyłącza diodę LED,
która jest już wbudowana w płytkę.

---

### Otwórz gotowy przykład

W menu wybierz:
**Plik → Przykłady → 01.Basics → Blink**

[ TU WSTAW OBRAZEK: Menu z przykładem Blink ]

Zobaczysz gotowy kod.
Nie zmieniaj go.

To jest eksperyment,
a nie sprawdzian z programowania.

---

## Krok 6: wgraj program do mikrokontrolera

Kliknij przycisk **Sprawdź**,
a potem **Wgraj**.

[ TU WSTAW OBRAZEK: Przyciski Sprawdź i Wgraj ]

Przez kilka sekund program będzie wysyłany do mikrokontrolera.
Diody na płytce mogą migać.
To normalne.

---

## Co powinno się wydarzyć?

Na płytce mikrokontrolera jest mała dioda,
najczęściej opisana literą **L**.

Jeśli wszystko poszło dobrze:
- dioda zapala się,
- po chwili gaśnie,
- i robi tak w kółko.

[ TU WSTAW OBRAZEK: Migająca dioda na płytce ]

To znaczy, że:
- komputer wysłał program,
- mikrokontroler go zrozumiał,
- i wykonuje dokładnie to, co było w instrukcji.

To jest pierwszy moment,
w którym elektronika robi coś dlatego,
że Ty jej tak kazałeś.

---

## Jeśli dioda nie miga

To się zdarza bardzo często.

Sprawdź spokojnie:
- czy wybrałeś dobrą płytkę,
- czy wybrałeś port,
- czy kabel USB jest dobrze podłączony.

W większości przypadków problem jest właśnie tutaj.

---

## Co dalej?

Ten program był bardzo prosty,
ale spełnił swoje zadanie.

Wiemy, że mikrokontroler działa
i że potrafimy wysyłać do niego programy.

W następnym rozdziale:
- podłączymy pierwsze elementy na płytce stykowej,
- dioda będzie osobnym elementem,
- i zaczniemy sterować czymś,
co sami fizycznie podłączyliśmy.

To dopiero początek.