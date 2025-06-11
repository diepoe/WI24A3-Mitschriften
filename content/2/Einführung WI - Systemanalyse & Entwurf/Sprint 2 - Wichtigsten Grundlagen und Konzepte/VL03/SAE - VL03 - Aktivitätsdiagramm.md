
> [!question] Zentrale Frage
> Wie realisiert ein System bestimmtes Verhalten?

> [!info] Diagrammtyp
Verhaltensdiagramm.

# Aktivität
- gerichteter Graph
	- Knoten: Aktionen
	- Kanten: Kontroll- und Datenflüsse

# Aktionen
- kleinste Einheit → atomar
- enthält immer ein Verb
- kann Eingaben zu Ausgaben verarbeiten

## Kategorisierung von Aktionen
> [!PDF|yellow] [[SAE - VL03 - Aktivitätsdiagramm.pdf#page=9&selection=35,0,55,94&color=yellow|Kategorisierung der in UML vordefinierten Aktionen: ]]
> - **Kommunikationsbezogene** Aktionen (z.B. Signale und Ereignisse) 
> - **Objektbezogene** Aktionen (z.B. Erzeugen und Löschen von Objekten) 
> - **Strukturmerkmals- und variablenbezogene** Aktionen (z.B. Setzen und Löschen einzelner Werte von Variablen)
> - **Linkbezogene** Aktionen (z.B. Erzeugen und Löschen von Links zwischen Objekten sowie Navigation)
# Kanten
- verbinden Knoten und legen mögliche Aktivitätsabläufe fest
- Kanten lassen sich mit guards synchronisieren, womit man die Häufigkeit der Ausführbarkeit einer Aktion singularisieren kann
## Arten von Kanten
> [!PDF|yellow] [[SAE - VL03 - Aktivitätsdiagramm.pdf#page=10&selection=15,0,40,60&color=yellow|SAE - VL03 - Aktivitätsdiagramm, p.10]]
> - **Kontrollflusskanten (ControlFlow)** 
> 	- Drücken eine reine Kontrollabhängigkeit zwischen Vorgänger- und Nachfolgerknoten aus 
> - **Objektflusskanten (ObjectFlow)**
> 	- Transportieren zusätzlich Daten und drücken dadurch auch eine Datenabhängigkeit zwischen Vorgänger- und Nachfolgerknoten aus
> - **Überwachungsbedingung (guard)**
> 	- Bestimmt, ob Kontroll- und Datenfluss weiterläuft oder nicht
# Start und Ende von Aktivitäten & Abläufen
> [!PDF|yellow] [[SAE - VL03 - Aktivitätsdiagramm.pdf#page=11&selection=9,0,41,36&color=yellow|SAE - VL03 - Aktivitätsdiagramm, p.11]]
> - **Initialknoten**
> 	- Beginn eines Aktivitätsablaufs
> 	- Pro Aktivität keine oder mehrere Initialknoten erlaubt – letzteres ermöglicht Nebenläufigkeit 
> - **Aktivitätsendknoten**
> 	- Beendet alle Abläufe einer Aktivität sowie den Lebenszyklus eines Objekts 
> 	- Keine Ausführung weiterer Aktionen
> 	- Pro Aktivität mehrere Aktivitätsendknoten erlaubt
> - **Ablaufendknoten**
> 	- Beendet einen Ablauf einer Aktivität
# Alternative Abläufe

> [!info] Prozessende nach Knoten
> (*Kann man von einem Entscheidungsknoten direkt in einen Endknoten gelangen?*)
> 
> Ein Entscheidungs-/Vereinigungsknoten kann direkt auf ein Prozess-/Aktivitätsende führen.

> [!warning] Vermeiden!
> Vermeiden, dass mehrere Pfeile gleichzeitig auf eine Aktivität weisen. Stattdessen Entscheidungs-/Vereinigungsknoten verwenden

## Entscheidungsknoten
> [!PDF|yellow] [[SAE - VL03 - Aktivitätsdiagramm.pdf#page=14&selection=9,0,41,83&color=yellow|SAE - VL03 - Aktivitätsdiagramm, p.14]]
> - Definiert alternative Zweige und repräsentiert eine »**Weiche**«
> 	- Verwendung auch zur Modellierung von Schleifen
> - **Überwachungsbedingungen**
> 	- Wählen den Zweig aus 
> 	- Müssen wechselseitig ausschließend sein
> 	- [else] ist vordefiniert 
> - **Entscheidungsverhalten**
> 	- Ermöglicht detailliertere Spezifikation der Auswahlentscheidung an zentraler Stelle
## Vereinigungsknoten
- führt alternative Abläufe zusammen (**keine Nebenläufigen!!**)
- kombinierter Entscheidungs- & Vereinigungsknoten

# Nebenläufige Abläufe

> [!danger] Darstellung
> Darstellung nebenläufiger Abläufe niemals ohne Parallelisierungsknoten entwerfen

## Paralllelisierungsknoten

- modelliert die Aufspaltung von Abläufen
## Synchronisierungsknoten
- führt nebenläufige Abläufe zusammen
- kann auch kombiniert Parallelisierungsknoten sein → nach Synchronisierung wird neuer Parallelprozess ausgelöst
> [!warning] Der Synchronisiserungsknoten wartet immer auf **beide** Eingaben.
> Das bedeuted, wenn zuvor ein Entscheidungsknoten verwendet wurde, wartet der Synchronisierungsknoten unendlich auf den nicht ausgelösten Parallelprozess.

---
# Token

> [!abstract] Der Stein, der alles ins Rollen bringt

- **logisches Konzept**
- **nich modelliert**
- beschreibt **möglichen Aktivitätsablauf**
- eine Aktivität enthält beliebig viele Tokens
- Tokens fließen entlang der Kanten von Vorgänger- zu Nachfolgerknoten
	- warten nicht auf einer Kante (Ausnahme: Synchronisierungsknoten)
	- lösen Verarbeitung aus


| Kontrolltoken                                  | Datentoken                                       |
| ---------------------------------------------- | ------------------------------------------------ |
| "Ausführungserlaubnis" für den Nachfolgeknoten | Transport von Datenwert oder Referenz auf Objekt |


> [!danger] Ausnahme vom Tokenkonzept #KLAUSURRELEVANT 
> Der erste Token der am Aktivitätsendknoten ankommt, beendet die Aktivität

---
# Objektknoten
#KLAUSURRELEVANT 
- enthält **Datentoken**
- Inhalt ist
	- **Ergebnis einer Aktion**
	- & **Eingabe für weitere Aktion**

Objektknoten kann man als Eingangsparameter für
	- Aktivitäten
	- Aktionen
verwenden

## Effekte einer Aktion auf Objekte
CREATE, READ, UPDATE, DELETE (CRUD)

## Pufferknoten
Zentrale Pufferung von Datentoken
### transienter Pufferknoten 
→ **löscht Datentoken nach Weitergabe**
### persistenter Pufferknoten
→ **bewahrt Datentoken auf** & gibt Duplikate weiter
- keine Mehrfachspeicherung gleicher Objekte
- explizites "Abholen" bestimmter Datentoken ist möglich

# Objektfluss
## Objektfluss
Reihenfolge, in der Datentoken an ausgehende Kante weitergegeben werden
### FIFO
first in, first out
### LIFO
last in, first out
### Geordnet
benutzerdefinierte Reihenfolge
### Ungeordnet
Reihenfolge des Tokeneingangs hat keinen Einfluss auf die Reihenfolge der Weitergabe

## Kapazitätsobergrenze und Gewicht
**Obergrenze** → max. Anzahl von Token, die sich zu einem Zeitpunkt in Knoten befinden dürfen
**Gewicht** → min. Anzahl der anzuliegenden Token an Kante, bevor sie an Nachfolgeknoten weitergegeben werden dürfen

## Selektionsverhalten
Auswahl bestimmter Token zur Weitergabe aus Datastore

# Partitionen
Gliederung des Diagramms nach Stakeholder(gruppen)
🔗 [[SAE - VL03 - Aktivitätsdiagramm.pdf#page=41&selection=5,0,5,11|SAE - VL03 - Aktivitätsdiagramm, p.41]]

# Signale & Ereignisse
🔗 [[SAE - VL03 - Aktivitätsdiagramm.pdf#page=42&selection=5,27,5,49|SAE - VL03 - Aktivitätsdiagramm, p.42]]

# Schachtelung von Aktivitäten
#KLAUSURRELEVANT 
Aktion, die Aktivität aufruft