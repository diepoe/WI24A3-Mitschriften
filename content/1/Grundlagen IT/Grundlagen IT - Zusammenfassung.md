
> [!quote] [[Zusammenfassung Grundlagen IT - Vincent]]
> 

# Digitalisierung
## Definition & Effekte
### Definitionen
> *Im Allgemeinen* versteht man unter Digitalisierung, dass analoge Leistungserbringung ganz oder teilweise durch ein computerhabbares Modell ersetzt wird

> *Im technischen Sinne* bedeutet Digitalisierung 
> die binäre Repräsentation von Medien (Texte, Bilder, Töne, Filme)
> sowie Eigenschaften physischer Objekte in Form aneinandergereihter Sequenzen aus "0" und "1",
> die von heutigen Computern mit extrem hoher Geschwindigkeit verarbeitet werden können

> *Im elektrotechnischen Sinne* bedeutet Digitalisierung die die Entwicklung elektronischer Schaltungen, die analoge Signale zeit- und wertediskret in digitale Signale überführen.

### Effekte
> [!info] Kontext
> innerbetrieblicher IT-Einsatz
#### Automatisierungseffekte
Digitale Automatisierung bislang analoger Abläufe & Prozesse beschleunigt und standardisiert diese.

> [!summary] Automatisierung
> manuell → automatisch

#### Informatisierungseffekte
Automatisierung macht die Informationen digital besser verfügbar.
**Folge:**
> [!summary] Informatisierung - Verfügbarkeit von Informationen
> Auswertung der zusätzlich verfügbaren Daten ermöglicht bessere Managmententscheidungen

#### Transformationseffekte
Digitale Technologien ermöglichen es, neben den [[#Automatisierungseffekte]]n auch komplett neue Geschäftsprozesse zu entwicklen

> [!summary] Transformation
> neuartige Prozesse


# (IT-Infrastruktur)
---
# Datenspeicherung
## Größeneinheiten
### SI-Einheiten (Basis 10)
**Kilo, Mega, usw. sind nach ==SI-Norm zur Basis 10== definiert.**
```
1 Byte = 8 Bits
1 Kilobyte = 1000 Bytes
1 Megabyte = 1000 Kilobyte
1 Gigabyte = 1000 Megabyte
1 Terabyte = 1000 Gigabyte
```
### IEC-Einheiten (Basis 2)
**Angaben zur Basis 2 werden nach IEC-Norm folgendermaßen bezeichnet:**
==KiB, MiB, GiB, TiB (**Ki**bi-, **Me**bi-, **Gi**bibyte, **Te**bibyte)==
```
1 Byte = 8 Bits
1 Kibibyte = 1024 Bytes
1 Mebibyte = 1024 Kibibyte
1 Gibibyte = 1024 Mebibyte
1 Tebibyte = 1024 Gibibyte
```
### Auswirkungen auf Speichergrößen

> [!warning] Auswirkungen
> - Arbeitsspeicher verwenden i.d.R. das 2er-System
> - ==Festplatten verwenden in der Regel das 10er-System ⇒ Festplatten *schrumpfen* im System==
## Zahlensysteme
**Dezimal:** $D_{10} =\{0, 1, 2, 3, 4, 5, 6, 7, 8, 9\}$
**Dual:** $D_{2} =\{0, 1\}$
**Oktal:** $D_{8} =\{0, 1, 2, 3, 4, 5, 6, 7\}$
	*Verwendung im Unix-Rechtesystem für Dateien*
**Hexadezimal:** $D_{16} =\{0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F\}$
	*Vorteil: ermöglicht Anzeigen eines Bytes mit nur zwei Ziffern*

> [!question] KLAUSURRELEVANT
> Umrechnung zwischen den Systemen beherrschen

## Komplementdarstellung
### Einerkomplement
Darstellung negativer Zahlen durch ==Invertierung==, **erstes Bit** fungiert indirekt **als Vorzeichenbit** `0 → +` und `1 → -`:

| Dezimalzahl | positiv | negativ |
| ----------- | ------- | ------- |
| 1           | `0001`  | `1110`  |
| 2           | `0010`  | `1101`  |
| 3           | `0011`  | `1100`  |
| 4           | `0100`  | `1011`  |

> [!danger] Probleme des Einerkomplements
> 
> Zwei Darstellungen von `0` möglich, z.B. `0000` und `1111`.
> 
> Beim Rechnen mit Übertrag muss beim Überschreiten des ersten Bits der Übertrag nochmals zum Zwischenergebnis addiert werden!

> [!quote] [Erklärvideo Einerkomplement](https://youtu.be/6Mlj3N8DL_I)

### Zweierkomplement
Darstellung negativer Zahlen durch ==Invertierung, dann Addieren von 1==, **erstes Bit** fungiert indirekt **als Vorzeichenbit** `0 → +` und `1 → -`:

| Dezimalzahl | positiv | negativ |
| ----------- | ------- | ------- |
| 1           | `0001`  | `1111`  |
| 2           | `0010`  | `1110`  |
| 3           | `0011`  | `1101`  |
| 4           | `0100`  | `1100`  |

> [!check] Vorteile des Zweierkomplements
> 
> ==Nur noch **eine** Darstellung der Null möglich== ⇒ größerer darstellbarer Zahlenraum
>
>Beim Rechnen mit Übertrag muss beim Überschreiten des ersten Bits der Übertrag ==nicht mehr== zum Zwischenergebnis addiert werden!
>
>Subtraktion einfach möglich, indem man den Subtrahenden einfach als negative Zahl zum Minuenden addiert.

> [!quote] [Erklärvideo Zweierkomplement](https://youtu.be/utqzSGXd4X4)

## Fließkommadarstellung (Floating Point)
![[Fliesskommadarstellung.pdf]]
- **Vorzeichenbit** $v$
- **Mantisse** $m$
	- nicht ganzzahliger Anteil
	- Komma i.d.R. zwischen erster und zweiter positioniert
	  ==⇒ Mantisse ist dann normalisiert==
- **Basis** $b$
	- Zahl, die zu potenzieren und anschließend mit der Mantisse zu multiplizieren ist
	- **Exponent** $e$ der Basis $b$

# Digitalisierung analoger Vorlagen/Signale
### Qualität beeinflussende Parameter
- Abtastrate (*Dichte*)
- Anzahl der Quantisierungsstufen (Umfang des Wertebereichs) (*Genauigkeit*)

### Wandlungsfehler
> [!tldr] Definition: Wandlungsfehler
> - in Abtastgrafik als Leerräume zwischen realem Signalverlauf und digital gespeichertem Verlauf
> ![[Wandlungsfehler.png]]
# Kodierung

> [!check] Warum Kodierung
> - **Ziel**: Texte auf verschiedenen Computersystemen einheitlich Darstellung
> - **Lösung:** standardisierte Zeichentabllen
### Ältere Standards
#### ASCII
American Standard Code for Information Interchange
- erste systemübergreifende Kodierung
- **7-Bit Kodierung**: $2^7 = 128$ verschiedene Zeichen
	- 33 nicht druckbare, 95 druckbare Zeichen
- 8. Bit ist **Paritätsbit** für die Fehlererkennung

#### ISO-8859
- **Erweiterung** des Zahlenraums **auf 8 Bit** → $2^8 = 256$ Zeichen
- Zeichen 0-127 = ASCII
- Zeichen 128-255 je nach Sprachraum unterschiedlich belegt (ISO-8859-1 bis ISO 8859-16)

> [!example] Beispiele
> *unterschiedliche europäische Ausprägungen* (==Latin==), kyrillisch, arabisch, griechisch, hebräisch usw.
### Unicode (ISO 10636)
- Zeichenkodierung, ==die alle menschlichen Schriftzeichen oder Textelemente enthalten soll==
- erste 128 identisch mit ASCII
- jedem Zeichen ist eindeutige Nummer zugeordnet
	- von `U+0000` bis `U+10FFFF`(U=Unicode, +=Trennzeichen, Zahlencode in Hexadezimal)
- **plattformunabhängig**
- Varianten (**untereinander kompatibel**)
	- UTF-8 (Linux, WWW, E-Mail)
	- UTF-16 (Windows, macOS)
	- UTF-32
	- ==Zahl hinter UTF ist die Anzahl der Bits, mit denen Zeichen mindestens kodiert wird==

# Aussagen- und Schaltungslogik
## Boolsche Algebra
- es gibt **nur zwei Werte**
	- **0** = **falsch**/**false** (*keine Spannung/Strom*)
	- **1** = **wahr**/**true** (*Strom / Spannung*)
### Boolsche Basisoperatoren

| Operator | Zeichen | Darstellung in Logikgatter | *Beschreibung* |
| -------- | ------- | -------------------------- | -------------- |
| OR       | \|      | >=1                        | oder           |
| AND      | &       | & *(2)*                    | und            |
| XOR      | ⊕       | =1                         | entweder-oder  |
| NOT      | ¬       | 1○                         | Negation       |
### Darstellung in Schaltung
- `OR` in **Parallelschaltung**
- `AND`in **Serienschaltung**

---
---
# Rechnerarchitektur
## Von-Neumann-Rechner
![[Von-Neumann-Architektur.pdf]]
- **ALU** (Arithmetic Logic Unit)
	- Rechenwerk
- **Control Unit** (Steuerwerk)
	- interpretiert Anweisungen eines Programms
	- verschaltet Datenquelle, -senke und notwendige ALU-Komponenten
	- regelt Befehlsabfolge
- **BUS** (Bus-System)
	- Kommunikation zwischen Komponenten
- **Memory** (Speicherwerk)
	- Arbeitsspeicher
	- speichert Programme & Daten zugänglich für das Rechenwerk
- **I/O Unit** (Eingabe-/Ausgabewerk)
	- Ein- und Ausgabe von Daten zum Anwender oder anderen Systemen (Schnittstellen)
### Unterschied zur Harvard Architektur

> [!warning] Wesentlicher Unterschied
> Bei der Harvard-Architektur sind ==die Speicher für Befehle und zu verarbeitende Daten== voneinander ==getrennt==

> [!check] Vorteile
> - Speicherschutz & Berechtigungen einfacher umsetzbar
> - schadhafte/maliziöse Daten können nicht als Programmcode ausgeführt werden
> - Paralleles Laden von Daten und Programmcode möglich
> - unterschiedliche Speichertechnik für jeweiligen Einsatzzweck einsetzbar

> [!danger] Nachteile
> - **effiziente Speichernutzung:** ungenutzter Speicher einen Typs kann nicht für Zwecke des anderen Typs benutzt werden (insbesondere bei Speicherknappheit)

### Von-Neumann-Zyklus
1. **FETCH**: abzuarbeitenden Befehl aus *Speicher* in Befehls-Register (*Steuerwerk*) laden
2. **DECODE**: *Steuerwerk* übersetzt Befehl in Schaltinstruktionen für das *Rechenwerk*
3. **FETCH OPERANDS**: Parameter (Operanden) für Befehl aus dem *Speicher* holen
4. **EXECUTE**: *Rechenwerk* führt Operation aus
5. **UPDATE INSTRUCTION POINTER**: Erhöhung Befehlszähler. Neubeginn des Zyklus, Ausführung des nächsten Befehls

## Rechnerkomponenten
### Aufgaben der wesentlichen Komponenten
- **Mainboard**
	- verbindet Komponenten
	- bietet interne & externe Anschlüsse (*zzgl. evtl. Zusatzfunktionen*)
- **CPU**
	- Hauptprozessor, welcher die meisten Arbeitn erledigt (Berechnungen, Datenkonvertierung/-verlagerung, Treffen von Entscheidungen)
- **Arbeitsspeicher**
	- enthält aktuell ausgeführte Programme und deren Daten
	- RAM = Random Access Memory (Gegensatz ROM = Read Only Memory)
	- Ansprechen jeder Speicherzelle direkt über Adresse (Random Access)
	- Inhalte der Speicherzelle werden ständig aufgefrischt
	- ohne elektrischen Strom Datenverlust
	- begrenzter Speicherplatz
- **Massenspeicher**
	- Speichermedium, wenn Computer keine Spannung hat und für große Datenmengen
- **Erweiterungskarten**
	- Nachrüsten nicht vorhandener Funktionen
	- z.B. Verbesserung bisher eingesetzter Hardware (z.B. Grafikkarten)

### Mainboard
#### Bestandteile & Steckplätze
- Steckplätze für Prozessor, Arbeitsspeicher & Erweiterungskarten
- [[#Chipsatz]]
- [[#interne & externe Anschlüsse]]
- [[#BIOS]]
- Energiesteuerung
- [[#Unterschied paralleler & serieller Bussysteme|Bussysteme]]
- Uhr
#### interne & externe Anschlüsse
- **SATA**
- **USB**
#### BIOS
- Power On Self-Test (POST)
- Hardwareinitialisierung
- Falls Konfiguriert: BIOS-Passwort- bzw. Datenträger-Passwort-Abfrage
- Darstellung Startbildschirm
- BIOS-Setup: Harware-Konfiguration
- Datenträgerüberprüfung für Boot, Laden des Startcodes des gewählten Betriebssystems vom Datenträger

> [!info] (U)EFI
> Unified Extensible Firmware Interface. 
> Nachfolger des klassischen BIOs.
> - <u>Ziele:</u>
> 	- einfachere Bedienung
> 	- erweiterte Netzwerkfähigkeiten
> 	- GUI
> 	- betriebssystemunabhänige Treiber
> 	- leichter aktualisierbar
> 	- größerer Funktionsumfang
> 	- leichter erweiterbar

#### Chipsatz
##### Northbridge
- **MCH: Memory Controller Hub**
- Bindeglied ==zwischen CPU-Komponenten und Arbeitsspeicher== (inkl. dem der GPU)
- dicht an CPU ⇒ schneller Datentransfer
- bei neuen Mainboards/CPU kein separater Chip mehr
- Anbindung [[#Southbridge]]
##### Southbridge
- **ICH: I/O Controller Hub**
- Datensteuerung und -transfer ==mit Peripherie und internen Erweiterungen== (PCIe/PCI-Steckplätze)
- BIOS auf EEPROM oder Flash-Speicher
- Anschlüsse
	- externe Anschlüsse
	- Massenspeicheranschlüsse

> [!info] PCH (Platform Controller Hub)
> Wenn Northbridge-Funktionen bereits in die CPU integriert sind, dann wird die Southbridge zusammen mit den verbleibenden Northbridge-Komponenten im **PCH** vereint.
#### Unterschied paralleler & serieller Bussysteme
##### parallel
- parallele Datenübertragung ==zeitgleich auf mehreren Leitungen== (Anzahl der Leitungen = Busbreite)

> [!danger] Probleme paralleler Bussysteme
> - Laufzeiten der Signale (unterschiedliche Leitungslängen bei Leitungslauf über Ecken)
> 	  → erst nach Eintreffen des Signals auf längster Leitung ist Übertragung komplett
> - hoher Platzbedarf auf Mainboard ⇒ erschwerte Leitungsverlegung
> - dicht beieinander verlegte Leitungen stören sich gegenseitig elektrisch
> - nur eine Komponente kann Daten übertragen

> [!example] Beispiele: Bussysteme (parallel)
> - Systemdatenbus
> 	- ISA
> 	- **PCI** (Periphal Component Interconnect)
> - Datenträger
> 	- IDE, **P-ATA** (Parallel ATA)

##### seriell
- serielle Datenübertragung von Bits eines oder mehrerer Bytes ==nacheinander über einzelne Leitungen==

> [!check] Vorteile serieller Bussysteme
> - höhere Taktdaten möglich ⇒ gleicht Wegfall paralleler Leitungen aus
> - vereinfachtes Platinendesign durch weniger Leitungen
> - Punkt-zu-Punkt-Verbindungen: zeitgleiche Übertragungen zwischen verschiedenen Komponenten aufgrund verschiedener Leitungen möglich

> [!example] Beispiele: Bussysteme (parallel)
> - Systemdatenbus
> 	- **PCIe** (Periphal Component Interconnect express)
> - Datenträger
> 	- **S-ATA** (Serial ATA)
> 	- **M.2**/PCIe
> - Universell
> 	- ==**USB** (Universal Serial Bus)==


> [!question] ÜBUNGSAUFGABE
> 1. Erläutern Sie die Unterschiede zwischen PCI und PCIe.
- **graphische Darstellung der Unterschiede**
	 ![[Parallel-Seriell-Bus.png]]
### CPU
#### Bestandteile & Aufgaben
- **Steuerwerk**
	  zentrales Element mit **Befehlsregister**, **Befehlszeiger** und **Befehlsdecoder**
- **Rechenwerk** (ALU)
	  arithmetisch-logische Einheit, arbeitet Befehle vom Steuerwerk ab (arithmetische und logische Operationen)
- **Speichermanager**
	  verwaltet Inhalte des Caches;
	  Verbindung von CPU zu Arbeitsspeicher;
	  Zuordnung realer Speicheradressen zum CPU-Adressraum
- **Register**
	  Speicherbereiche innerhalb eines Prozessors, direkt mit der Recheneinheit verbunden;
	  für Operanden & Berechnungsergebnisse;
	  schnellste, direkt zugängliche Speichereinheit des Prozessors;
	  wenige bis 100 pro CPU
- **Cache**
	  Zwischenspeicher zwischen Registern und RAM;
	  häufig verwendete Daten und Befehle;
	  direkte schnelle Verbindung ohne externen Bus;
	  ==Notwendig aufgrund des Ungleichgewichts CPU-Geschwindigkeit ↔️ Arbeitsspeicherzugriffsgeschwindigkeit==
- (**[[#Northbridge]]**)
- **CPU-Bus** 
	  ⇒ verbindet alle Komponenten miteinander
#### Cache-Hierarchie
![[Cache-Hierarchie.pdf]]
#### Ablauf Befehlszyklus
→ [[#Von-Neumann-Zyklus]]
### Interrupts
- **Grundkonzept**
	  Anforderung, laufendes Programm zu unterbrechen;
	  nach Verarbeitung der Unterbrechung wird das Programm weiter fortgesetzt
- **Auslöser** (Beispiele)
	- Tastendruck
	- Soundkarte braucht neue Daten
	- Netzwerkkarte empfängt neue Daten
	- Maus wurde bewegt
- *Verarbeitung durch Interrupt-Controller*
### Datenträger/Speicherkonzepte
#### optisch
##### Funktionsprinzip & Datenorganisation
- Daten werden von innen nach außen **in spiralförmiger Spur abgespeichert**
- **Leseeinheit** auf beweglichem Schlitten besteht aus ==Licht emittierender Laserdiode und lichtempfindlicher Fotozelle== zur Auswertung des reflektierten Lichts
##### Unterschied gepresst & gebrannt

| gepresst                                                                               | gebrannt                                                                                                                                                |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Daten werden mechanisch als Vertiefungen und Erhebungen aufgebracht (==Pits & Lands==) | *durch Anwender beschrieben*, Daten werden in Materialkombination gespeichert, deren ==Reflexionseigenschaft== beim Brennen ==punktuell geändert== wird |
| länger haltbar                                                                         | empfindlichere Reaktion auf Temperatureinflüsse und UV-Licht                                                                                            |

#### magnetisch
##### Magnetband
- magnetisch beschichtetes Plastikband wird an Schreib- & Lesekopf vorbeigeführt
- für Schreib- & Lesevorgänge wird jeweils an passende Stelle des Bandes gespult
- eigentlicher Übertraungsvorgang mit sehr hohen Bandbreiten
- *Skizze*
	![[Skizze_Magnetband.pdf]]
##### Festplatte
- **Bestandteile**
	- eine/mehrere mit magnetisierbaren Material beschichtete Scheiben rotieren in staubdichten Gehäuse
	- bewegliche Arme mit zwei Schreib- und Leseköpfen (für Ober- und Unterseite)
	- Schreib-/Leseköpfe schweben auf hauchdünnen Luftpolster	![[Skizze_MagnetischeFestplatte.pdf]]

> [!danger] Head Crash
> - **Anlass**: Schreib-/Leseköpfe berühren Magnetscheiben (z.B. aufgrund von Erschütterungen)
> 	  ⇒ Lesekopf fräst Magnetschicht von Trägermaterial
> - **Auswirkung**: Schäden & Datenverlust

- **==Datenorganisation (Spur/Zylinder, Sektor)==**
	- auf konzentrischen Ringen, den Spuren gespeichert
	- Spuren in Sektoren mit fester Bytegröße unterteilt
	- eine Datei erstreckt sich i.d.R. über mehrere Sektoren
	![[Skizze_MagnetischeFestplatte-Datenorganisation.pdf]]
#### elektrisch
##### grundsätzliches Funktionsprinzip
- ==Speichern der Information durch elektrische Ladungen (elektrischer Schalter ist geöffnet oder geschlossen)==
##### flüchtig ↔️ nicht flüchtig
- **flüchtig:** verliert ohne Stromversorgung seinen Inhalt (Register, Cache, RAM)
- **nicht-flüchtig**: Speicherinhalt bleibt auch ohne Stromversorgung erhalten (Flash-Speicher)
##### Speicherzellendichte
- **SLC** (Single-Level Cell)
	  Speichern von einem Bit je Schalter (0 oder 1)
- **MLC** (Multi-Level Cell)
	  Speichern von vier Zuständen je Schalter (zwei Bit)
- **TLC** (Triple-Level Cell)
	  Speichern von acht Zuständen je Schalter (drei Bit)
- **QLC** (Quadruple-Level Cell)
	  Speichern von 16 Zuständen je Schalter (vier Bit)
⇒ *Ab der Multi-Level Cell wird die abgestufte Durchlässigkeit als Zustandsmessung des Schalters genutzt* (z.B. zu-fast zu-fast offen-offen)

> [!example] Auswirkungen in der Realität
> - ==jeder Schreib-/Löschvorgang nutzt die Speicherzellen ab==
> - ==MLC/TLC/QLC sind in Herstellung *günstiger* als SLC==, da mehr Daten auf gleichem Raum gespeichert werden
> - dafür sind ==SLC-Speicher schneller und langlebiger==

##### Abnutzung und Gegenmaßnahmen
- **Wear Leveling** (steuerelektronische Maßnahmen ==gegen Abnutzung==)
	  gleichmäßiges Verteilen der Daten;
	  Umsortieren häufig genutzter Daten;
	  Zusammenfassen von Zugriffen
- **Cache**
- **SLC-Bereich**
#### Begriffe
- **Zugriffszeit/Latenz**
	  Zeit, die von Anforderung der Daten bis Übertragung vergeht
- **Übertragungsrate**
	  ==nach Abschluss der Zugriffsvorbereitungen== dauerhafte ==Datenübertragungsgeschwindigkeit==
- **IOPS** (Inputs and Outputs Per Second)
	  Anzahl verarbeitbarer Ein-/Ausgabeanforderungen je Sekunde
- **_Speicherhierarchie_**
### RAID
Redundant Array of Disks. 
Datenträgerverbund, wird vom Betriebssystem als einzelner, virtueller Datenträger wahrgenommen.

> [!warning] RAID ersetzt kein Backup!

#### Level
0. **Striping**
   Datenblöcke werden zerteilt und gleichmäßig auf alle beteiligten Datenträger verteilt;
   Maxmimierung der Lese- & Schreibgeschwindigkeit
   ==⚠︎ nicht redundant==
1. **Mirroring**
   Daten werden auf allen beteiligten Datenträgern komplett und identisch gespeichert;
   Bei Ausfall eines Datenträgers stehen Daten nach wie vor ohne Unterbrechung zur Verfügung → ==redundant==
5. **Striping** mit Absicherung (**Parity**)
   wie Level 0; 
   zusätzlich werden aus Daten generierte Zusatzinformationen (Parität/Prüfsumme) verteilt gespeichert;
   Zusatzinformationen ermöglichen Datenwiederherstellung bei Ausfall *maximal eines Datenträgers* → ==eingeschränkt redundant==
#### Vergleich

| Eigenschaft | RAID 0 (Striping) | RAID 1 (Mirroring) | RAID 5 (Distributed Parity) |
|------------|-------------------|--------------------|-----------------------------|
| **Schreibgeschwindigkeit** | Sehr schnell (Daten werden parallel geschrieben) | Langsam (Daten müssen auf mehrere Festplatten gespiegelt werden) | Mittel (Schreiben mit Paritätsinformationen) |
| **Lesegeschwindigkeit** | Sehr schnell (paralleler Zugriff) | Schnell (Daten können von verschiedenen Platten gelesen werden) | Schnell (paralleler Zugriff möglich) |
| **Speicherkapazität** | Maximale Nutzung (Summe aller Plattenkapazitäten) | 50% Kapazitätsverlust (Hälfte der Platten für Spiegelung) | ca. 80% Nutzbare Kapazität (Eine Platte für Paritätsinformationen) |
| **Redundanz** | Keine (Ausfall einer Platte führt zum Datenverlust) | Sehr hoch (Vollständige Datensicherung durch Spiegelung) | Mittel (Überlebens- und Rekonstruktionsfähigkeit bei Plattenausfall) |
