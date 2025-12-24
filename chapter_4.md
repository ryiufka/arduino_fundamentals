# 🔐 Rozdział 4  
## Drzwi, które wiedzą, kogo wpuścić  

[ TU WSTAW OBRAZEK: mikrokontroler + czytnik RFID + serwo SG90 + karta ]

---

## O co tu chodzi?

Do tej pory mikrokontroler:
- reagował na światło i zapalał diodę,
- reagował na przyciski i wydawał dźwięki.

Teraz zrobimy coś nowego.

> **Mikrokontroler sprawdzi, kim jesteś i zdecyduje, czy otworzyć drzwi.**

Dokładnie tak działają:
- breloki do drzwi na klatce schodowej,
- karty do biura.

---

## Co będzie potrzebne?

Z zestawu weź:
- mikrokontroler  
- płytkę stykową  
- **czytnik RFID (13,56 MHz)**  
- **brelok RFID**  
- **serwo SG90**  
- kilka przewodów  

Na tym etapie nie otwieramy prawdziwych drzwi.
Serwo będzie udawało **zamek**.

---

## Jak działa RFID? (bardzo krótko)

RFID to technologia, w której:
- karta **nie ma baterii**,
- czytnik wysyła energię,
- karta odpowiada swoim **numerem**.

Ten numer to coś w rodzaju:
> **tajnego identyfikatora**

Każda karta ma **inny numer**.

---

## Jak działa serwo? (jeszcze krócej)

Serwo to silnik, który:
- **nie kręci się w kółko**,
- tylko ustawia się w **konkretnym miejscu**.

Na przykład:
- 0° → drzwi zamknięte  
- 90° → drzwi otwarte  

I dokładnie to wykorzystamy.

---

## Najważniejsza zasada tego rozdziału

> **Nie każda karta otwiera drzwi.  
> Tylko ta, którą wybierzesz.**

To nie jest zabawka.
To jest **kontrola dostępu**.

---

## Krok 1: przygotuj płytkę stykową

Najpierw podłącz:
- **GND** z mikrokontrolera do bocznej linii płytki stykowej,
- **5V** z mikrokontrolera do drugiej bocznej linii.

Dzięki temu wszystkie elementy będą miały zasilanie.

---

## Krok 2: podłącz czytnik RFID

Czytnik RFID ma kilka pinów.
Użyjemy tylko tych potrzebnych.

Podłącz:
- **VCC** → 5V  
- **GND** → GND  
- **SDA** → pin 10  
- **SCK** → pin 13  
- **MOSI** → pin 11  
- **MISO** → pin 12  
- **RST** → pin 9  

Nie musisz rozumieć nazw pinów.
Wystarczy, że połączysz je zgodnie z opisem.

---

## Krok 3: podłącz serwo (zamek)

Serwo SG90 ma **trzy przewody**:

- **brązowy lub czarny** → GND  
- **czerwony** → 5V  
- **pomarańczowy lub żółty** → sygnał  

Podłącz:
- przewód GND serwa → GND na płytce,
- przewód 5V serwa → 5V na płytce,
- przewód sygnałowy serwa → pin 6 mikrokontrolera.

Serwo może się lekko poruszyć po włączeniu zasilania.
To normalne.

---

## Krok 4: sprawdź numer swojej karty

Zanim zrobimy drzwi, musimy wiedzieć jedno:
> **jaki numer ma Twoja karta**

Wgraj program testowy, który:
- odczyta numer karty,
- pokaże go w komputerze.

```
#include <SPI.h>
#include <MFRC522.h>

#define SS_PIN 10
#define RST_PIN 9

MFRC522 rfid(SS_PIN, RST_PIN);

void setup() {
  Serial.begin(9600);
  SPI.begin();
  rfid.PCD_Init();

  Serial.println("Zbliz karte do czytnika...");
}

void loop() {

  // Czy jest nowa karta?
  if (!rfid.PICC_IsNewCardPresent()) {
    return;
  }

  // Czy mozna odczytac dane karty?
  if (!rfid.PICC_ReadCardSerial()) {
    return;
  }

  // Wyswietl numer karty
  Serial.print("Numer karty: ");

  for (byte i = 0; i < rfid.uid.size; i++) {
    Serial.print(rfid.uid.uidByte[i], HEX);
    Serial.print(" ");
  }

  Serial.println();

  // Zatrzymaj komunikacje z karta
  rfid.PICC_HaltA();
}
```

### Jak zobaczyć numer karty w komputerze

Żeby mikrokontroler mógł pokazać numer karty, musi „porozmawiać” z komputerem.
Do tego służy **Monitor portu szeregowego**.

---

### Krok po kroku

1. Wgraj program do mikrokontrolera.
2. W Arduino IDE kliknij:
   **Narzędzia → Monitor portu szeregowego**.
3. W prawym dolnym rogu okna ustaw prędkość na **9600**.
4. Zbliż kartę do czytnika.

Jeśli wszystko działa poprawnie,
w oknie pojawi się numer karty.

---

### Co to jest ta „prędkość 9600”?

To tylko informacja:
> **jak szybko mikrokontroler wysyła tekst do komputera**

Jeśli prędkość jest inna:
- pojawią się krzaki,
- albo nie pojawi się nic.

Dlatego zawsze ustaw **9600**.

---

### Jak wygląda poprawny wynik?

Na ekranie zobaczysz coś w tym stylu: **Numer karty: 4A 7F 2C 91**
Zapisz ten numer, będzie nam potrzebny w kolejnym kroku.

---

## Krok 5: instrukcja dla mikrokontrolera

Teraz mówimy mikrokontrolerowi:

> **JEŚLI numer karty jest taki jak zapisany  
> TO otwórz drzwi  
> W PRZECIWNYM RAZIE nie rób nic**

To jest dokładnie ta sama zasada,
którą znasz z poprzednich rozdziałów.

Tylko zamiast:
- światła,
- albo przycisku,

sprawdzamy **kartę**.

---

## Co właśnie zbudowałeś?

Zbudowałeś:
- system kontroli dostępu,
- zamek sterowany kartą,
- urządzenie, które **rozpoznaje i decyduje**.

Mikrokontroler:
- odczytuje numer karty,
- porównuje go z zapisanym,
- **porusza serwem**, czyli „otwiera drzwi”.

To już nie jest zabawka.
To jest **prawdziwa logika systemów**.

---

## Spróbuj sam

Jeśli chcesz pójść dalej:

- 🔄 zmień kąt otwarcia serwa  
- ⏱ zmień czas, na jaki drzwi są otwarte  
- 🔐 dodaj drugą kartę z dostępem  
- 🚫 spraw, żeby „zła” karta nic nie robiła  
- 🔊 dodaj dźwięk przy otwarciu  

Nie zmieniasz elektroniki.
Zmienia się tylko **instrukcja w programie**.

---

## Jeśli coś nie działa

Sprawdź:
- czy karta jest RFID 13,56 MHz,
- czy przewody serwa są dobrze podłączone,
- czy piny w kodzie zgadzają się z podłączeniem,
- czy czytnik RFID ma zasilanie.

Najczęściej:
> to jeden kabel w złym miejscu.

I to jest normalne.

---

## Co dalej?

W kolejnym rozdziale możemy:
- połączyć kartę z kodem PIN,
- zrobić alarm,
- albo użyć prawdziwego przekaźnika.

Ale najpierw zapamiętaj jedno:

> **Nauczyłeś mikrokontroler rozpoznawać, kto stoi przed drzwiami.**
