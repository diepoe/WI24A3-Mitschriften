# Use Case "Dozentenpool verwalten"

|                          |                                                                                                                                                                                                                 |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                 | "Dozentenpool" verwalten                                                                                                                                                                                        |
| **Kurzbeschreibung**     | Verwaltung einer internen Liste potenzieller externer Dozenten für unterschiedliche Lehrveranstaltungen.                                                                                                        |
| **Akteure**              | Studiengangsmanager (SGM)                                                                                                                                                                                       |
| **Vorbedienungen**       | - gepflegtes Dozentennetzwerk der DHBW<br>- Kontaktaufnahme mit neuem Dozenten (z.B. Bewerbung)                                                                                                                 |
| **Auslösendes Ereignis** | SGM möchte einen neuen Dozenten einpflegen<br>ODER potenzielle Dozenten für konkrete Lehrveranstaltungen identifizieren<br>ODER die Liste anderweitig bearbeiten (Kontaktdaten aktualisieren, Dozenten löschen) |
| **Hauptszenario**        | 1. SGM öffnet Word-Dokument<br>2. SGM filtert die Dozentenliste nach dem mit einem Dozenten zu besetzenden Fach<br>3. SGM extrahiert gewünschte Kontaktdaten von Dozent(en) und konaktiert diese(n)             |
| **Alternativszenario**   | 1. *Wie im Hauptszenario*<br>2. SGM bearbeitet Dozenteneintrag oder fügt einen neuen Dozenten hinzu                                                                                                             |
| **Nachbedingungen**      | -                                                                                                                                                                                                               |

# Use Case "Vorlesungsrahmenplan erstellen"

|                          |                                                                                                                                                                                                |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                 | Vorlesungsrahmenplan erstellen                                                                                                                                                                 |
| **Kurzbeschreibung**     | Auf Basis des Modulplans für das Semester im spezifischen Studiengang sowie der Raumbelegung wird ein Rahmenplan für die Lehrveranstaltungen eines Kurses für die kommenden Semester erstellt. |
| **Akteure**              | SGM<br>*Raumplanungssystem, Google Sheets*                                                                                                                                                     |
| **Vorbedienungen**       | Einsehen des Modulplans und Transfer der Moduldaten (Anzahl der Vorlesungsstunden, besondere Raumanforderungen etc.) in Google Sheets                                                          |
| **Auslösendes Ereignis** | SGM startet Planung für das kommende Semester.                                                                                                                                                 |
| **Hauptszenario**        | 1. SGM erstellt auf Basis des Modulverlaufsplans die Rahmenvorlage für das Semester                                                                                                            |
| **Alternativszenario**   | -                                                                                                                                                                                              |
| **Nachbedingungen**      | Vorlesungsrahmenplan für das Semester eines spezifischen Kurses wurde erstellt.                                                                                                                |
# Use Case "Terminvorschlag von Dozent bearbeiten"

|                          |                                                                                                                                                                                             |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                 | Terminvorschlag von Dozent bearbeiten                                                                                                                                                       |
| **Kurzbeschreibung**     | Ein externer Dozent hat einen Terminvorschlag für Lehrveranstaltung(en) auf den Vorlesungsrahmenplan abgegeben, welcher nun durch das SGM bearbeitet (eingepflegt oder konsolidiert) wird.  |
| **Akteure**              | SGM<br>*Google Sheets*                                                                                                                                                                      |
| **Vorbedienungen**       | - Vorlesungsrahmenplan vorhanden<br>- Dozent wurde um Terminvorschläge für das Semester gebeten                                                                                             |
| **Auslösendes Ereignis** | Dozent übermittelt Terminvorschlag an Sekretariat (Erfolgreiche Ausführung des Use Case "Vorlesungstermin vorschlagen")                                                                     |
| **Hauptszenario**        | 1. SGM sichtet Vorschlag<br>2. SGM prüft Vorschlag auf auf Terminkonflikt<br>3. Bei erfolgreicher Prüfung nimmt SGM Terminvorschlag an und [aktualisiert den öffentlichen Vorlesungsplan]() |
| **Alternativszenario**   | 3. Bei Terminkonflikt nimmt SGM Kontakt mit dem Dozenten auf, um den Konflikt zu beheben (Wiederholung des Prozesses)                                                                       |
| **Nachbedingungen**      | Terminvorschlag angenommen & eingepflegt                                                                                                                                                    |

# Use Case "Öffentliche Version des Vorlesungsplans verwalten"

|                          |                                                                                                       |
| ------------------------ | ----------------------------------------------------------------------------------------------------- |
| **Name**                 | Öffentliche Version des Vorlesungsplans verwalten                                                     |
| **Kurzbeschreibung**     | Bearbeitung des Vorlesungsplans auf der Plattform Google Sheets                                       |
| **Akteure**              | {abstract} VerwaltungsMA<br>*Google Sheets, Kalenderservice*                                          |
| **Vorbedienungen**       | Vorlesungsplanänderung liegt vor (z.B. Ausfall durch Krankheit)                                       |
| **Auslösendes Ereignis** | Ein Eintrag im Vorlesungsplan soll aktualisiert werden                                                |
| **Hauptszenario**        | 1. VerwaltungsMA klärt Änderungsanfrage ab<br>2. VerwaltungsMA bearbeitet Daten des Vorlesungseintrag |
| **Alternativszenario**   | 2. VerwaltungsMA *löscht* Vorlesungseintrag<br>---  <br>1. VerwaltungsMA sieht Vorlesungsplan ein     |
| **Nachbedingungen**      | Update Kalenderabonnement                                                                             |
# Use Case "Vorlesungstermin vorschlagen"

|                          |                                                                                                                                                                                                                                                                   |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                 | Vorlesungstermin vorschlagen                                                                                                                                                                                                                                      |
| **Kurzbeschreibung**     | Der Dozent schlägt auf konkrete Anfrage des SGM's per E-Mail Terminwünsche für seine Lehrveranstaltungen vor                                                                                                                                                      |
| **Akteure**              | Dozent,<br>*Externes E-Mail-System*                                                                                                                                                                                                                               |
| **Vorbedienungen**       | - Vorlesungsrahmenplan vorhanden<br>- SGM verständigt sich mit Dozenten auf Ausrichtung der Lehrveranstaltung                                                                                                                                                     |
| **Auslösendes Ereignis** | Dozent hat Terminrahmen durch das SGM mit Bitte um Rückmeldung erhalten                                                                                                                                                                                           |
| **Hauptszenario**        | 1. Dozent sieht seinen Terminrahmen (Mischung aus Vorlesungsrahmenplan und teilweise erstelltem Vorlesungsplan) ein<br>2. Dozent konsolidiert seinen persönlichen Kalendar<br>3. Dozent sendet Terminvorschlag für Vorlesungen über sein E-Mail-System an das SGM |
| **Alternativszenario**   | *Wenn Konsolidierung zwischen verfügbaren Vorlesungsslots und Privat-/Arbeitsterminen des Dozenten nicht möglich ist, erfolgt ebenfalls eine Nachricht an das SGM mit Problemstellung*                                                                            |
| **Nachbedingungen**      | Terminvorschlag von Dozenten wurde zugestellt                                                                                                                                                                                                                     |

