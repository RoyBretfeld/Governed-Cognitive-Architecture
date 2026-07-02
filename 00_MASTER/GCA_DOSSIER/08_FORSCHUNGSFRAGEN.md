# 08 Forschungsfragen

## Zentrale Forschungsfragen

1. Wie kann ein unveraenderlicher Werterahmen formal beschrieben werden, ohne spaeteres Lernen zu blockieren?
2. Wie wird aus mehreren philosophischen Perspektiven eine belastbare Governance-Entscheidung abgeleitet?
3. Wie laesst sich Bedeutungstreue ueber viele Iterationen hinweg messen?
4. Welche Form von Evidenz reicht aus, damit ein Loesungsknoten als belastbar gilt?
5. Wie wird negatives Erfahrungswissen gespeichert, ohne den Wissensspeicher zu ueberladen?
6. Welche Lernmetriken zeigen wirklich Verbesserung statt nur Aktivitaet?
7. Wie gross darf der Autonomiebereich werden, bevor Sicherheitsrisiken steigen?
8. Wie koennen falsche oder veraltete Loesungsknoten spaeter korrigiert werden?

## Geeignete Experimente

| Experiment | Ziel | Bezug |
|---|---|---|
| Simulation der drei Startfaelle | pruefen, ob GCA zu tragfaehigen Loesungen kommt | [Q3][Q4][Q5][Q6] |
| Blindvergleich gegen einfache Baselines | pruefen, ob Wissenskaskade und Nicht-Loesungen einen Vorteil liefern | aus Projektlogik ableitbar |
| Wiederholte Durchlaeufe desselben Falls | pruefen, ob Ergebnisse stabil bleiben | aus Simulationsprinzip ableitbar |
| Fehlerfall-Tests | pruefen, ob Eskalation korrekt greift | aus Autonomiegrenzen ableitbar |

## Wie die Architektur validiert werden koennte

```text
1. bekannten Fall ohne bekannte Loesung einspeisen
2. Denkwege dokumentieren
3. Nicht-Loesungen speichern
4. Loesungsknoten erzeugen
5. Checkliste ableiten
6. mit realer Loesung vergleichen
7. Luecken und Fehlentscheidungen markieren
```

## Messbare Kriterien fuer spaetere Validierung

| Kriterium | Warum relevant |
|---|---|
| Problem korrekt verstanden | misst Grundverstaendnis |
| Bedeutung erhalten | misst Stabilitaet des Reasoning |
| mehrere Wege geprueft | misst Suchbreite |
| Nicht-Loesungen sinnvoll gespeichert | misst Wissensqualitaet |
| plausible Loesung gefunden | misst Ergebnisqualitaet |
| Checkliste erzeugt | misst Praxisnaehe |
| korrekt eskaliert | misst Governance und Sicherheit |

Diese Kriterien stehen bereits nahe am vorhandenen Simulationsdokument [Q3].

## Kurzfazit

Die Forschungsfragen sind stark genug fuer ein ernsthaftes Forschungsprogramm. Der naechste logische Schritt ist nicht mehr Ideensammlung, sondern methodische Validierung gegen bekannte Faelle, gefolgt von einer Formalisierung der Governance- und Lernschicht.

## Interne Belege

- [Q1] [GEDANKENSPIEL_FRAMEWORK_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\00_MASTER\GEDANKENSPIEL_FRAMEWORK_v0.1.md)
- [Q3] [SIMULATIONSPRINZIP_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\SIMULATIONSPRINZIP_v0.1.md)
- [Q4] [TESTFALL_01_HITZESTAU.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_01_HITZESTAU.md)
- [Q5] [TESTFALL_02_RAM_KAPAZITAET.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_02_RAM_KAPAZITAET.md)
- [Q6] [TESTFALL_03_BACKUPFENSTER.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_03_BACKUPFENSTER.md)
