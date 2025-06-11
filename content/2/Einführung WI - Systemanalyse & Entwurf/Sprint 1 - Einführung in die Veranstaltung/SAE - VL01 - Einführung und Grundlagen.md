# Scrum
> [!quote] Überblick Scrum 
> SCRUM: Begriffe
[[SAE - VL01 - Einführung und Grundlagen.pdf#page=4&selection=2,0,2,15|SAE - VL01 - Einführung und Grundlagen, Seite 4]]

## Hierarchische Gliederung
strategisch -------------------→ technisch
**Theme** > **Epic** > **UserStory** > **Task**

# Motivation - wieso das ganze?
> [!quote] 
> Etwa 75 % der Softwareprojekte überschreiten Zeit- und Budgetrahmen und liefern nicht die erwarteten Ergebnisse
[[SAE - VL01 - Einführung und Grundlagen.pdf#page=12&selection=4,0,5,10|SAE - VL01 - Einführung und Grundlagen, Seite 12]] → #KLAUSURRELEVANT

# Definitionen
## Software

> [!warning] #KLAUSURRELEVANT Definition Software
> [[SAE - VL01 - Einführung und Grundlagen.pdf#page=13&selection=2,0,2,30|SAE - VL01 - Einführung und Grundlagen, Seite 13]]

## System (technisch)
> [!warning] #KLAUSURRELEVANT Definition System
> [[SAE - VL01 - Einführung und Grundlagen.pdf#page=14&selection=2,0,2,30|SAE - VL01 - Einführung und Grundlagen, Seite 14]]
## Systemanalyse
> [!warning] #KLAUSURRELEVANT objektorientierte Systemanalyse
> [[SAE - VL01 - Einführung und Grundlagen.pdf#page=15&selection=2,0,2,26|SAE - VL01 - Einführung und Grundlagen, Seite 15]]

→ lediglich Konzeptionierung, keine konkrete Implementierung bzw. Entwicklung

## Systementwurf
> [!warning] #KLAUSURRELEVANT objektorientierter Systementwurf
> [[SAE - VL01 - Einführung und Grundlagen.pdf#page=15&selection=24,0,24,91|SAE - VL01 - Einführung und Grundlagen, Seite 15]]

## Softwareentwicklung

> [!info] Unterscheidungsaspekte von Software zu anderen Produkten #KLAUSURRELEVANT 
> - Software ist ein immaterielles Produkt:
> 	- Software kann man nicht „anfassen“, nicht „sehen“
> - Software unterliegt keinem Verschleiß, altert aber trotzdem:
> 	- Software kann beliebig oft ablaufen, ohne dass Abnutzungserscheinungen auftreten
> 	- Sie altert aber trotzdem, da die Umgebung, in der eine Software eingesetzt wird, sich ständig ändert
> - Software wird nicht durch physikalische Gesetze begrenzt:
> 	- Software ist ein künstliches Produkt des menschlichen Erfindungsgeistes
> 	- Es basiert nicht auf physikalischen Gesetzen
>   
> - Software ist (im Allgemeinen) leichter und schneller änderbar als ein (physisches) technisches Produkt:
> 	- Vorausgesetzt, Software ist gut strukturiert und modularisiert lassen sich Änderungen schnell/einfach durchführen
> 	- Für Veränderungen technischer Produkte oft neues Werkzeug notwendig • Für Software gibt es keine Ersatzteile
> - Bei technischen Produkten werden defekte Produktteile (oder gleich das ganze Produkt) ausgetauscht und durch in der Regel vorproduzierte Ersatzteile ersetzt. → nur eingeschränkt gültig für Backups • Bei Software gibt es keinen Verschleiß. Anpassungen werden erst vorgenommen, wenn Fehler auftreten und nicht „auf Halde“ entwickelt. Nicht zu verwechseln mit allgemeiner Weiterentwicklung/Verbesserung der Software • Software ist schwer zu „vermessen“ • Technische Produkte kann man i.d.R. sehr exakt vermessen. Sie können sowohl untereinander als auch mit anderen Standards verglichen werden. Das ist bei Software nur bedingt möglich
> 
🔗 [[SAE - VL01 - Einführung und Grundlagen.pdf#page=16&selection=12,0,42,44|SAE - VL01 - Einführung und Grundlagen, Seite 16]] - [[SAE - VL01 - Einführung und Grundlagen.pdf#page=17&selection=12,0,49,69|Seite 17]]

## Einflussparameter auf die Veränderungen in der Softwareeentwicklung

> [!warning] Einflussparameter #KLAUSURRELEVANT 
> Welche Veränderungen der letzten Jahre (Jahrzehnte) beeinflussen die Softwareentwicklung?
>🔗 [[SAE - VL01 - Einführung und Grundlagen.pdf#page=18&selection=4,0,4,89|SAE - VL01 - Einführung und Grundlagen, Seite 18ff.]]

---
# Überblick Anforderungsmanagment & Lebenszyklus
## Phasen der Softwareentwicklung
#KLAUSURRELEVANT 
> [!PDF|yellow] [[SAE - VL01 - Einführung und Grundlagen.pdf#page=22&selection=4,0,4,80&color=yellow|SAE - VL01 - Einführung und Grundlagen, p.22]]
> > Jede Komponente durchläuft grundsätzliche Phasen, unabhängig vom Vorgehensmodell
> 

### 1. Anforderungsanalyse
- Verständnis für Kundenwünsche erwerben und manifestieren
- Anforderungen gestellt durch Kunden & Stakeholder

> [!PDF|important] [[SAE - VL01 - Einführung und Grundlagen.pdf#page=23&selection=37,0,37,76&color=important|Ziel der Anforderungsanylse]]
> Das Ziel ist es, ganzheitlich Anforderungen zu erfassen und zu dokumentieren
> 

### 2. Designphase
- grob: Anforderungen SW-Modell, technische Architektur
- fein: Softwarestruktur, UI-Design, Schnittstellen
### 3. Implementierung
- Programmierung der funktionierenden Software
### 4. Test & Integration
- Prüfung der Software
- Integration in restliche Systeme
- Abnahme durch Kunden
### 5. Qualitätssicherung
- z.B. mit CI/CD-Pipeline

## Iterativ vs. Inkrementell
>[!quote] [[SAE - VL01 - Einführung und Grundlagen.pdf#page=25&selection=0,2,2,25|SAE - VL01 - Einführung und Grundlagen, p.25|Iterativ vs. Inkrementell]] #KLAUSURRELEVANT 

Iteration vs. Inkrement → Unterschied kennen #KLAUSURRELEVANT 



---
# UML (Unified Modeling Language)

> [!PDF|red] [[SAE - VL01 - Einführung und Grundlagen.pdf#page=27&selection=2,0,2,25&color=red|SAE - VL01 - Einführung und Grundlagen, p.27]] #KLAUSURRELEVANT 
> Unified Modeling Language
- standardisierte Diagrammtypen zur Beschreibung von Prozessen & Systemen
→ Visualisierungx ermöglicht besseres Verständnis

## Unterscheidung in Strukur- vs. Verhaltensdiagramm
**Struktur:** statische Sicht auf Systemkomponenten & Zusammenhänge
**Verhalten:** Veränderungen von Zuständen von Objekten *über die Zeit* hinweg
🔗 [[SAE - VL01 - Einführung und Grundlagen.pdf#page=27&selection=2,0,2,25|SAE - VL01 - Einführung und Grundlagen, p.27]] #KLAUSURRELEVANT 

## Diagrammarten

> [!quote] Diagrammarten #KLAUSURRELEVANT 
> 🔗 [[SAE - VL01 - Einführung und Grundlagen.pdf#page=33&selection=2,0,2,25|SAE - VL01 - Einführung und Grundlagen, p.33]]
> → Diagrammarten beschreiben und verstehen können


---
---
# Gruppenarbeit Modellierungsprojekt
==Gruppe 1: Agile Bügeleisen== mit Willi & Luis S. 
→ Interview mit Studiengangsmanagment zum Thema "Alles rund um Vorlesungensplanung"



