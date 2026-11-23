# M162 Lernjournal

<details>
<summary><b>Tag 1</b></summary>

### Was haben wir gemacht?

Wir haben angeschaut, wie man bei einer Art Bewerbung die Informationen am besten und am verständlichsten hinüberbringt. Danach haben wir Merkmalstypen und Skalentypen angeschaut.

### Merkmalstypen

Häufbar: Man kann mehrere Ausprägungen gleichzeitig haben, z. B. mehrere Hobbys.

Diskret: Man kann es zählen, es gibt nur ganze Werte, z. B. Teilnehmeranzahl.

Stetig: Man muss es messen, es gibt auch Zwischenwerte, z. B. Gewicht.

| Merkmal | Typ | Begründung |
|---|---|---|
| Haarfarbe | häufbar | Man kann mehrere Farben haben |
| Gewicht | stetig | Wird gemessen, z. B. 62,4 kg |
| Strecke | stetig | Wird gemessen, z. B. 3,7 km |
| Hobby | häufbar | Man kann mehrere Hobbys haben |
| Geschlecht | häufbar | Keine Zahl, wie Haarfarbe |
| Zeitintervall | stetig | Wird gemessen, z. B. 12,5 s |
| Berufsausbildung | häufbar | Man kann mehrere machen |
| Teilnehmeranzahl | diskret | Wird gezählt, nur ganze Zahlen |
| Wasserpegel | stetig | Wird gemessen, z. B. 1,8 m |

### Skalentypen

Nominalskala: Die Werte sind nur Namen, es gibt keine Reihenfolge. Man kann nicht rechnen. Beispiel: Haarfarbe.

Ordinalskala: Die Werte haben eine Reihenfolge, aber man kann nicht rechnen. Beispiel: Kleidergrösse S, M, L.

Kardinalskala: Die Werte sind richtige Zahlen, man kann damit rechnen. Beispiel: Gewicht.

Metrische Skala: Das Gleiche wie die Kardinalskala, nur ein anderer Name. Beispiel: Strecke.

| Merkmal | Skala | Begründung |
|---|---|---|
| Zeitdauer | Kardinalskala (metrisch) | messbar, gleiche Abstände |
| Geschlecht | Nominalskala | keine natürliche Reihenfolge |
| Kontonummer | Nominalskala | Zahl ist nur ein Name |
| Zufriedenheit (Skala 1–5) | Ordinalskala | Reihenfolge, ungleiche Abstände |
| Streckenlänge | Kardinalskala (metrisch) | messbar, gleiche Abstände |
| Haarfarbe | Nominalskala | keine natürliche Reihenfolge |
| Telefonnummer | Nominalskala | Zahl ist nur ein Name |
| Militär-Dienstrang | Ordinalskala | klare Rangfolge vorhanden |
| Wassertiefe | Kardinalskala (metrisch) | messbar, gleiche Abstände |
| Präferenzrangfolge | Ordinalskala | Rangfolge ohne Abstände |
| Geschmacksrichtung | Nominalskala | keine natürliche Reihenfolge |

### Vergleich der Datenarten

| Tätigkeit | Unstrukturiert | Wenig strukturiert | Strukturiert |
|---|---|---|---|
| Initialisieren (Struktur festlegen) | sehr einfach, keine Struktur nötig | einfach, grobe Struktur reicht | sehr schwierig, Datenmodell planen |
| Erfassen (Daten eingeben) | sehr einfach, keine Regeln | einfach, Felder flexibel | mittelschwierig, Schema einhalten |
| Mutieren (Daten ändern) | sehr schwierig, Stelle schwer zu finden | mittelschwierig, Aufbau uneinheitlich | sehr einfach, UPDATE in SQL |
| Löschen (Daten entfernen) | mittelschwierig, Teile schwer entfernbar | einfach, Feld gezielt entfernen | sehr einfach, DELETE in SQL |
| Auswerten (suchen und filtern) | sehr schwierig, keine Felder zum Filtern | mittelschwierig, Daten uneinheitlich | sehr einfach, Abfragen mit SQL |

### Redundanz

Redundanz bedeutet, dass die gleiche Information mehrfach gespeichert ist, zum Beispiel die Adresse eines Kunden in jeder seiner Bestellungen. Das braucht mehr Speicherplatz, und wenn man die Daten nur an einer Stelle ändert, widersprechen sie sich (Inkonsistenz). Darum teilt man die Daten in einer Datenbank auf mehrere Tabellen auf (Normalisierung). Ausser die Redundanz ist gewollt, zum Beispiel bei Backups zur Datensicherheit.

</details>

<details>
<summary><b>Tag 2</b></summary>

# Datentjpen
### Zahlenumwandlung (Unsigned)

1. Wandle die Dezimalzahl 27 in ihr binäres «Unsigned»-Äquivalent um.

   Antwort: 0001'1011

2. Welchem Dezimalwert entspricht unsigned 1001'0011B?

   Antwort: 147

3. Welchem hexadezimalen Wert entspricht unsigned 1011'0111B?

   Antwort: B7

4. Das letzte Oktett einer IP-Adresse lautet in Hexadezimal 3D. Welchem Binärwert entspricht dies?

   Antwort: 0011'1101

### Zahlenumwandlung (Signed)

Aufgabe 1:

```
27 ÷ 2 = 13  Rest 1
13 ÷ 2 = 6   Rest 1
6  ÷ 2 = 3   Rest 0
3  ÷ 2 = 1   Rest 1
1  ÷ 2 = 0   Rest 1
```

Von unten nach oben: 11011

In 8 Bit: 0001'1011

Aufgabe 2: -109

### Einfache numerische Datentypen

INTEGER (signed int): Ganze Zahlen mit Vorzeichen, z. B. -2, -1, 0, 1, 2

INTEGER (unsigned int): Ganze Zahlen ohne Vorzeichen (nur positiv), z. B. 0, 1, 2

FLOAT (float): Fliesskommazahlen, z. B. -2.1426, +0.1393 · 10³, -0.725 · 10⁻³

BOOLEAN (boolean): Logischer Datentyp, z. B. true, false

Normalisiertes Float-Format: x = v · m · b^e

- v = Vorzeichen (1 Bit)
- m = Mantisse (23 Bit)
- b = Basis (2)
- e = Exponent (8 Bit)
- Total: 32 Bit

### Datentypen und Wertebereich

Unsigned: 0 bis 2^n − 1

Signed: −2^(n−1) bis 2^(n−1) − 1

1. 0 bis 255 (2^8 = 256, minus 1 = 255)
2. −32'768 bis +32'767
3. 2^16 = 65'536
4. Mehr als eine Million: 2^20 = 1'048'576, also 20 Bit
5. Anzahl Werte: 999 + 999 + 1 (die Null) = 1999

   2^10 = 1024, zu wenig

   2^11 = 2048, reicht, also 11 Bit

### Aufgabe 8: 300'000'000 + 1

Ein Float kann nicht jede Zahl speichern. Bei grossen Zahlen kann er nur in Sprüngen zählen.

Schritt 1: Welche Zweierpotenz passt zu 300'000'000?

2^28 = 268'435'456, das passt (ist knapp kleiner).

Schritt 2: Wie gross sind die Sprünge?

28 − 23 = 5, also 2^5 = 32 (23 = Anzahl Mantissen-Bits beim Float).

Schritt 3: Der Float kann also nur speichern:

300'000'000, 300'000'032, 300'000'064 …

Schritt 4: 300'000'001 liegt fast genau auf 300'000'000, also wird gerundet.

Antwort: Es bleibt 300'000'000. Die +1 ist zu klein und geht verloren.

### Aufgabe 9: Boolean bei 100'000 Kunden

Ein Boolean ist nur «Ja» oder «Nein». Dafür reicht 1 Bit. Der Computer nimmt aber 1 Byte (= 8 Bit).

Theoretisch (1 Bit pro Kunde): 100'000 Bit ÷ 8 = 12'500 Byte = 12,5 kB

Real (1 Byte pro Kunde): 100'000 Byte = 100 kB

Antwort: theoretisch 12,5 kB, real 100 kB

### Aufgabe 10: Wochentag als INTEGER

Es gibt nur 7 Wochentage. Dafür braucht man keine 4 Byte, 1 Byte reicht.

Mit INTEGER (4 Byte): 5'000'000 × 4 = 20 MB

Mit TINYINT (1 Byte): 5'000'000 × 1 = 5 MB

Verschwendet: 20 − 5 = 15 MB

Antwort: Nicht sinnvoll. INTEGER braucht 4-mal mehr Speicher als nötig. Besser ist TINYINT (1 Byte).

# Alphanumerische Codes
## Auftrag 1
Nein, die Umlaute werden nicht Korrecht dargestellt.
<img width="388" height="153" alt="image" src="https://github.com/user-attachments/assets/e2e976d0-5005-49b0-9cf0-b89d5401ee90" />

## Auftrag 2
Es hat nicht mehr die Spizeial Zeichen also man kann die Nachricht jetzt lesen.
## 3
<img width="377" height="189" alt="image" src="https://github.com/user-attachments/assets/39589e06-f931-4b03-9251-bfdf3a24e404" />
## Auftrag 4
Ich kann die Datei nicht mit einem Webbrouser öffnen
</details>


<details>
<summary><b>Tag 3</b></summary>

# Datenstrukturen – Übersicht

## 1. Hashmap / Hashtabelle
**Prinzip:** Schlüssel → Wert. Eine Hashfunktion bestimmt das Fach.
**Beispiel:** Garderobe: Nummer 42 → direkt zu Haken 42.

```
hash("Lena") = 3  →  [0: Tim] [1] [2] [3: Lena]
```
✅ sehr schnelles Suchen ❌ keine Sortierung

## 2. Binärer Suchbaum
**Prinzip:** Max. 2 Kinder pro Knoten. Links kleiner, rechts grösser.
**Beispiel:** Zahlenraten mit „höher / tiefer“.

```
      8
     / \
    3   10
   / \
  1   6
```
✅ schnelles Suchen ❌ ohne Balance wird er zur Kette

## 3. Linked List / Verkettete Liste
**Prinzip:** Jeder Knoten zeigt auf den nächsten.
**Beispiel:** Schnitzeljagd.

```
[A]──→[B]──→[C]──→ null
```
✅ schnelles Einfügen/Löschen ❌ langsames Suchen

## 4. Stack / Stapelspeicher (LIFO)
**Prinzip:** Oben rein, oben raus.
**Beispiel:** Tellerstapel, Ctrl+Z.

```
[C] ← zuerst raus
[B]
[A]
```
✅ letztes Element sofort ❌ kein Zugriff auf die Mitte

## 5. Heap
**Prinzip:** Baum, Eltern immer grösser (Max-Heap) oder kleiner (Min-Heap) als Kinder.
**Beispiel:** Chef steht immer oben.

```
     50
    /  \
  30    40
```
✅ Grösstes/Kleinstes sofort ❌ beliebig suchen

## 6. PriorityQueue / Vorrangwarteschlange
**Prinzip:** Wichtigstes zuerst raus. Meist mit Heap gebaut.
**Beispiel:** Notaufnahme im Spital.

```
Rein: Finger(2), Herzinfarkt(10), Beinbruch(6)
Raus: Herzinfarkt → Beinbruch → Finger
```

## 7. Queue / Warteschlange (FIFO)
**Prinzip:** Hinten rein, vorne raus.
**Beispiel:** Kassenschlange, Drucker.

```
raus ← [A] [B] [C] ← rein
```
✅ Reihenfolge bleibt ❌ kein Zugriff auf die Mitte

## Merksätze
- **Stack** = Tellerstapel, **Queue** = Kassenschlange
- **Heap** = das Wie, **PriorityQueue** = das Was
- **Suchbaum:** links < rechts, **Heap:** oben > unten
