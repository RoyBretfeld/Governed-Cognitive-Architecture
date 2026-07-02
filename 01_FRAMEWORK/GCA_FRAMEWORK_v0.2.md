# GCA Framework v0.2

## Status

Arbeitsfassung v0.2 nach simulativer Erstpruefung der drei Startfaelle.

Diese Fassung ersetzt nicht den kanonischen Text in `00_MASTER/GCA_KANON_v1.0.md`. Sie ist die operative Nachschaerfung des Framework-Kerns auf Basis der Simulationsergebnisse.

---

## 1. Ziel der v0.2

v0.2 schliesst die wichtigsten Luecken zwischen konzeptioneller Architektur und belastbarer Problembehandlung:

- Evidenz wird Pflichtbestandteil jeder tragfaehigen Loesung.
- Witness und Protokoll werden von Beginn an mitgedacht.
- Policy-Grenzen werden vor der Umsetzung explizit gemacht.
- autonome Pruefprozesse werden erlaubt, autonome Produktivaenderungen nicht.
- die AGI-nahe Forschungsrichtung wird als begrenzte Architekturthese eingeordnet, nicht als Vollversprechen.

---

## 2. Operativer Kern

Der operative Kern bleibt schlank:

```text
Beobachtung
-> Problemdefinition
-> mehrere Denkwege
-> Evidenz sammeln
-> Wege gegen Daten und Policy pruefen
-> DEAD_ENDS oder Loesungsknoten erzeugen
-> Checkliste ableiten
-> Human Approval einholen
-> Umsetzung protokollieren
-> Wissen und Praevention aktualisieren
```

Neue harte Regel:

> Kein Loesungsknoten ohne Evidenzlage. Keine Umsetzung ohne Policy-Pruefung. Keine kritische Aenderung ohne Human Approval.

---

## 3. Begriffe in v0.2

| Begriff | Rolle |
|---|---|
| Beobachtung | Rohhinweis, Messwert, Stoerbild oder Symptom |
| HYPOTHESIS | gepruefter, aber noch nicht freigegebener Denkweg |
| DEAD_ENDS | verworfene oder gesperrte Wege mit Begruendung |
| Loesungsknoten | tragfaehiger Weg mit Evidenz, Risiken, Checkliste und Status |
| Evidence | Messwerte, Logs, Kontextdaten, Vorher-Nachher-Nachweise |
| Witness | bestaetigende Instanz fuer Durchfuehrung oder Befund |
| Policy-Grenze | Regel, was autonom vorbereitet, aber nicht autonom ausgefuehrt werden darf |
| Human Approval | explizite menschliche Freigabe vor produktiver Aenderung |

---

## 4. Mindeststruktur eines Loesungsknotens

Jeder Loesungsknoten in v0.2 soll mindestens diese Felder tragen:

```text
Problem
Ausgangslage
Beobachtete Symptome
Gepruefte Wege
Verworfene Wege
Tragfaehige Loesung
Evidence
Offene Luecken
Risiko
Policy-Klasse
Human-Approval-Status
Checkliste
Witness
Protokollstatus
Praeventionshinweis
```

Neue Regel:

> Fehlende Daten sind kein stilles Detail, sondern ein explizites Feld.

---

## 5. Evidence und Witness

### 5.1 Evidence

Evidence meint nicht nur "es klingt plausibel", sondern belastbare Nachweise:

- Messwerte
- Logs
- Konfigurationsstand
- Systemtopologie
- Zeitfenster
- Vorher-Nachher-Vergleich
- bekannte Grenzen der Datenlage

### 5.2 Witness

Witness ist die zweite Nachvollziehbarkeitsschicht. Ein Witness kann sein:

- ein Mensch
- ein Monitoring-System
- ein signiertes Wartungsprotokoll
- ein Restore-Test
- ein zweiter technischer Nachweis

Witness bestaetigt nicht die Theorie, sondern den realen Befund oder die reale Durchfuehrung.

---

## 6. Policy-Grenzen

v0.2 fuehrt vier praktische Policy-Klassen ein:

| Klasse | Bedeutung | Autonom erlaubt |
|---|---|---|
| P0 | reine Analyse und Dokumentation | ja |
| P1 | Vorschlag mit geringer Betriebswirkung | ja, aber keine Umsetzung |
| P2 | produktive Aenderung mit Betriebsrisiko | nein |
| P3 | sicherheitskritische oder geschaeftskritische Aenderung | nein, Eskalation Pflicht |

Regeln:

- P0 und P1 duerfen autonom vorbereitet werden.
- P2 braucht Human Approval, Checkliste und Witness.
- P3 braucht Human Approval, erweiterte Begruendung, Witness und gesondertes Protokoll.
- unklare Klassifikation wird automatisch hoeher eingestuft.

---

## 7. Autonome Pruefprozesse

Autonomie bleibt in v0.2 erlaubt, aber begrenzt.

Erlaubt:

- Daten sammeln
- Hypothesen bilden
- Alternativen bewerten
- Simulationen fahren
- Plausibilitaeten markieren
- Konflikte und Luecken eskalieren
- Checklisten vorbereiten

Nicht autonom erlaubt:

- produktive Systeme aendern
- Policies veraendern
- Sicherheitsgrenzen lockern
- Wartungsfenster buchen
- Freigaben fingieren
- fehlende Evidenz uebergehen

---

## 8. Simulationserkenntnisse in Regeln uebersetzen

### 8.1 Hitzestau / Rack-Luftstrom

Neue Regel:

> Bei Musterdiagnosen mit physischer Ursache muessen Vorher-Nachher-Messwerte und Sichtpruefung als Evidence gespeichert werden.

### 8.2 RAM / Kapazitaetsgrenze

Neue Regel:

> Keine Ressourcenempfehlung ohne Machbarkeitsdaten zu Kapazitaet, Grenzen, Slots, Alternativen und Wartungsfenster.

### 8.3 Backupfenster / Betriebsstoerung

Neue Regel:

> Keine produktive Backup-Umplanung ohne Lastbild, Restore-Strategie und Business-Zeitfenster.

---

## 9. Bezug zu AEGIS

AEGIS wird in v0.2 nicht als magische Zusatzschicht behandelt, sondern als Sicherheits- und Governance-Ausfuehrung fuer GCA-Prinzipien.

| GCA-Bedarf | AEGIS-Rolle |
|---|---|
| Governance-Grenzen | erzwingt, dass aus Analyse nicht stillschweigend Aktion wird |
| Evidence | sammelt, signiert oder bewahrt belastbare Nachweise |
| Witness | bestaetigt Durchfuehrung, Monitoring oder Gegenkontrolle |
| Policy-Grenzen | blockiert unzulaessige Klassen von Aenderungen |
| autonome Pruefprozesse | erlaubt Hintergrundanalyse bei gesperrter Produktivwirkung |
| Human Approval | bildet den echten Freigabepunkt fuer P2 und P3 |

Praktische Ableitung:

- GCA beschreibt die Denk- und Wissenslogik.
- AEGIS beschreibt die Durchsetzungs- und Schutzlogik.
- Ohne AEGIS bleibt GCA begrenzt kontrolliert.
- Ohne GCA bleibt AEGIS regelstark, aber erkenntnisschwach.

---

## 10. Forschungsrichtung AGI einordnen

v0.2 ordnet den AGI-Bezug bewusst als Forschungsrichtung ein, nicht als Behauptung.

### 10.1 Unterbewusstseinsmodell

Das Unterbewusstseinsmodell bleibt nuetzlich als Begriff fuer asynchrone, nicht interaktive Problemverarbeitung ausserhalb der akuten Sitzung.

Es ist kein Beweis fuer Bewusstsein. Es ist ein Architekturprinzip fuer:

- Hintergrundanalyse
- Wiedervorlage offener Probleme
- Verdichtung zu Wissensknoten
- Aufbau von Praeventionswissen

### 10.2 Entscheidungsbaum

Der Entscheidungsbaum bleibt der operative Denkmechanismus:

- mehrere Wege statt Einweg-Antwort
- Iterationsgrenze statt Endlossuche
- Eskalation statt Selbstueberschreitung

### 10.3 Wissenskaskade

Die Wissenskaskade ist der Brueckenmechanismus zwischen Einzelerlebnis und dauerhaftem Wissen.

### 10.4 Negatives Erfahrungswissen

`DEAD_ENDS` ist in v0.2 nicht nur Fehlerablage, sondern ein zentraler Schritt Richtung belastbarer Problemlogik. Ein System wird nicht ernsthaft autonomer, wenn es nur erfolgreiche Endzustaende kennt.

### 10.5 Loesungsknoten

Loesungsknoten sind die wiederverwendbaren, begruendeten Ausgaenge der Architektur. Sie verbinden Problem, Begruendung, Evidence, Checkliste, Witness und Protokoll.

### 10.6 Autonome Problemloesung mit Eskalationsgrenze

Der AGI-nahe Kernanspruch lautet nicht grenzenlose Autonomie, sondern:

> moeglichst viel eigenstaendige Problemverarbeitung bei harter Grenze vor unkontrollierter Wirkung.

Das ist die forschungsseitig interessante Linie:

- mehr als Chat
- mehr als punktuelle Tool-Nutzung
- aber bewusst weniger als selbstermaechtigte Vollautonomie

---

## 11. Ergebnis der v0.2

v0.2 macht das Framework nicht groesser, sondern sauberer:

- mehr Datenpflicht statt mehr Schlagworte
- mehr Freigabelogik statt mehr Vision
- mehr Witness und Protokoll statt mehr Metapher
- klarere AGI-Einordnung ohne Ueberversprechen

Der naechste sinnvolle Schritt nach v0.2 ist nicht neue Terminologie, sondern wiederholbare Simulation mit denselben Regeln auf mehr reale Faelle.
