
> [!example] [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=6&selection=2,0,2,22&color=important|Slides]]


> [!info] Diagrammtyp
Verhaltensdiagramm.
# Anwendungsfälle

- **Sequenz von Transaktionen** innerhalb eines Systems
- erzeugt für einzelnen Anwender einen **identifizierbaren Nutzen**

- Transaktionen implizieren, dass dem User die **Kommunikation mit dem System möglich ist**.
- **messbarer Nutzen** ⇒ Ausführung einer Transaktion hat Auswirkung auf Dinge außerhalb des Systems (speziell dem Akteur)
# Notationselemente
## System
> [!question] Was wird beschrieben?

Abgrenzung von der Umwelt

## Akteur
> [!question] Wer benutzt das System?

- repräsentiert Rolle eines Benutzers des Systems
- ==ist **niemals** selbst im System==, sondern klar außerhalb
- Interaktionsmöglichkeiten
	- Akteur benutzt das System (steht links) → aktiv
	- Akteur wird vom System benutzt (steht rechts im Diagramm) → passiv

mehrere Akteure gleichen Typs können mit Multiplizitätsnummer an Akteurssymbol gekennzeichnet werden

### Klassifikation der Akteure
- menschlich
- nicht-menschlich
- primär
- sekundär
- aktiv
- passiv

## Anwendungsfall
> [!question] Was machen die Akteure?

- beschreibt Verhalten, welches vom System erwartet wird
- *Notation: Ellipse mit Text*
	- Kurzbeschreibung als Notiz möglich

---
# Beziehungen

> [!check] Best Practice
> Bei include- und extends-Beziehung wird der Akteur nur mit dem Haupt-Use-Case verbunden

## `<<include>>` Beziehung


> [!information] Einbindung
> Das **Verhalten** des benutzten Anwendungsfalls wird **zwingend** in den aktuellen Anwendungsfall eingebunden.

> [!example]
> - B ist unbedingt notwendig, um die Funktionalität von A sicher zu stellen
> - B kann seperat ausgeführt werden
> 
> 🔗 [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=18&selection=59,0,59,9&color=important|Beispielvisualisierung, Slides S.18]]


## `<<extends>>` Beziehung

> [!information] Einbindung
> Das **Verhalten** des benutzten Anwendungsfalls **kann** in den aktuellen Anwendungsfall eingebunden werden.


> [!example]
> - B kann von A aktiviert werden, muss aber nicht
> - A bzw. B können seperat ausgeführt werden
> 
> 🔗 [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=19&selection=58,0,58,9&color=important|Beispielvisualisierung, Slides S. 19]]

## Generalisierung
> [!PDF|note] [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=23&selection=10,0,29,48&color=note|Bei Anwendungsfällen]]
> - B erbt das Verhalten von A und kann dieses überschreiben oder ergänzen 
> - B erbt alle Beziehungen von A 
> - B benötigt A (übernimmt Grundfunktionalität von A) 
> - B entscheidet, was von A ausgeführt bzw. geändert wird
> ---
> - Modellierung abstrakter Anwendungsfälle möglich: {abstract} abstrakte Anwendungsfälle sind nicht ausführbar!

> [!PDF|note] [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=24&selection=10,0,24,29&color=note|Bei Akteuren]]
> - Akteur A erbt von Akteur B 
> - A kann mit den Anwendungsfällen X und Y kommunizieren
> - B kann nur mit Y kommunizieren
> - Mehrfachvererbung ist erlaubt

---
# [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=37&selection=2,0,2,24&color=important|Aufgabe: Use Case Puzzle]]

![[UseCasePuzzle_ATM_Loesung.png]]

---
03.04.2025

---
# Anwendungsfallbeschreibung
🔗 [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=30&selection=2,0,2,26&color=note|vgl. Slides S.30]]

# Identifikation von Akteuren
> [!PDF|note] [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=32&selection=8,0,45,12&color=note|S.32]]
> - Wer benutzt die wesentlichen Anwendungsfälle? 
> - Wer braucht Systemunterstützung für die tägliche Arbeit? 
> - Wer ist für die Systemadministration zuständig?
> - Mit welchen externen Geräten / (Software-)Systemen muss das System kommunizieren können?
> - Wer oder was interessiert sich für die Ergebnisse des Systems?

# Identifikation von Anwendungsfällen

> [!PDF|note] [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=33&selection=8,0,28,81&color=note|p.33]]
> - Nach der Identifikation der Akteure
> - Trigger für Anwendungsfälle suchen 
> 	- Trigger = Ereignisse, die eintreten müssen, damit das System veranlasst wird ein Ergebnis zu produzieren.
> - Der Aufruf des Systems erfolgt oft durch einen Akteur, der damit Akteur des Anwendungsfalles wird.
> - Es werden folgende Trigger unterschieden: **interne**, **externe** und **zeitliche** Trigger.
# Regeln zur Anwendungsfallmodellierung
> [!PDF|red] [[SAE - VL02 - Anwendungsfalldiagramm.pdf#page=34&selection=10,0,18,6&color=red|Hauptregel]]
> Die **wichtigsten funktionalen Anforderungen** müssen in den Anwendungsfällen **festgehalten** werden

## Iteratives Vorgehen
- zunächst sind Anwendungsfälle bei der Anforderungserhebung entstehend Grundlage für Folgeentwicklung, aber können dann im Laufe des Prozesses bei Bedarf angepasst bzw. erweitert werden

# Typische Modellierungsfehler
1. Akteur "Mitarbeiter" ist im System
2. System fehlt, Use Cases sind zu detailliert beschrieben
3. "Kalender aktualisieren" und "Teilnehmer verstaendigen" hängen nicht per include zusammen, da nicht mit jeder Aktualisierung eine Benachrichtigung der Teilnehmer mit einher geht
4. Diagramm kann durch abstrakte Klassen/Generalsierung vereinfacht werden
5. Anwendungsfälle sind zu detailliert und können zusammengefasst werden
6. Einezelschritte eines Anwendungsfalls einzeln modelliert, richtig wäre die Zusammenfassung in einem Anwendungsfal

## Modellierungsfehler in Use Case Diagramm finden - Schema
#KLAUSURRELEVANT 
1. System vorhanden?
2. Akteur außerhalb des Systems?
3. UseCase innerhalb des Systems?
4. Detailgrad des Diagramms angemessen?


> [!quote] Weiterführend
> 🔗 [[Assignment - SuperStudyOrg|Aufgabe zu Anwendungsfalldiagrammen]]


