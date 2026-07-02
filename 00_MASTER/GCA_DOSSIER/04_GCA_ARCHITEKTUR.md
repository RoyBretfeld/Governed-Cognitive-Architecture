# 04 GCA Architektur

## Gesamtbild

GCA wird in dieser Fassung bewusst auf den heute belegten Kern begrenzt. Nicht belegte Zusatzebenen gehoeren nicht mehr zur aktiven Kernarchitektur.

```text
Cognitive Core
Knowledge Cascade
Governance-Grenzen
Simulation und Validierung
```

## Ebenen im Ueberblick

| Kernbereich | Rolle | Im Material belegt | Einstufung |
|---|---|---|---|
| Cognitive Core | Denken, Planen, Problemlosen | klar belegt [Q1] | Architekturentscheidung |
| Knowledge Cascade | Wissensverdichtung und Wissensspeicherlogik | klar belegt [Q1][Q2] | Architekturentscheidung |
| Governance-Grenzen | begrenzen autonome Handlung | klar belegt [Q1] | Architekturentscheidung |
| Simulation und Validierung | pruefen den Kern an bekannten Faellen | klar belegt [Q3] | Implementiertes Konzept |

## Historische Entwicklung

Dieses Kapitel zeigt den Reifeprozess der Architektur, nicht nur alte Namen.

| Phase | Neue Erkenntnis |
|---|---|
| Gedankenspiel | Wissen muss dauerhaft erhalten bleiben. |
| Wissensverdichtung | Wissen muss verdichtet werden. |
| Abend-Reasoner | Problembearbeitung braucht eine eigene Denk-Instanz. |
| DEAD_ENDS | Fehler sind ebenfalls Wissen. |
| Werterahmen und Freigabegrenzen | Lernen und Handeln brauchen Grenzen. |
| Governance-Gedanke | Wissen allein reicht nicht. |
| GCA | Alle Bausteine bilden gemeinsam eine Architektur. |

## Cognitive Core

Der Cognitive Layer ist im Material am klarsten beschrieben.

```text
Problem
-> Weg A
-> Weg B
-> Weg C
-> Wege pruefen
-> Loesung oder Eskalation
```

Wichtige Regeln:

- Das Problem darf nicht umgedeutet werden [Q1].
- Mehrere Wege sollen geprueft werden [Q1].
- Die Iteration ist begrenzt [Q1].
- Risiko fuehrt sofort zur Eskalation [Q1].

## Knowledge Cascade

Die Knowledge Cascade ist das staerkste und am besten belegte Architektursegment.

```text
Tagesdaten
-> Problem erkennen
-> Loesungswege bilden
-> Wege pruefen
-> Wissensknoten
-> Loesungsknoten
-> Checkliste oder Protokoll
-> Registry oder Wissensspeicher
```

### Vorhandene Bausteine

| Baustein | Im Material belegt | Einstufung |
|---|---|---|
| DAILY_DUMP | indirekt als Tagesdaten belegt [Q1] | Architekturentscheidung |
| Wissensknoten | direkt als Wissensknoten belegt [Q1] | Architekturentscheidung |
| HYPOTHESIS | indirekt ueber gepruefte Wege belegt [Q1] | Architekturentscheidung |
| DEAD_ENDS | indirekt ueber Nicht-Loesungen belegt [Q1] | Architekturentscheidung |
| Loesungsknoten | ja [Q1] | Architekturentscheidung |
| Checkliste | ja [Q1] | Implementiertes Konzept |
| Protokoll | ja [Q1] | Implementiertes Konzept |
| Wartungsplan | ja [Q1] | Implementiertes Konzept |
| Registry-Erweiterung | ja [Q2] | Architekturentscheidung |

### Interne Datenlogik

```text
Erkenntnis
-> Wissensknoten
-> Typ
-> Loesungsknoten / Fakt / HYPOTHESIS / DEAD_END / Checkliste / Protokoll
```

`Wissensknoten` bleibt der interne Oberbegriff. Nach aussen kann weiterhin vor allem mit `Loesungsknoten` gearbeitet werden.

Historie ist kein eigener Architekturbaustein. Sie entsteht aus DAILY_DUMP, HYPOTHESIS, DEAD_ENDS, Loesungsknoten, Checklisten und Protokollen.

### Nicht Teil des festen Kerns

| Begriff | Stand |
|---|---|
| Baseline | vorerst nicht Teil der Kernarchitektur |
| Pointer | vorerst nicht Teil der Kernarchitektur |
| Subprocess | vorerst nicht Teil der Kernarchitektur |
| atomare Commits | vorerst nicht Teil der Kernarchitektur |

## Governance-Grenzen

Ein eigenes Governance-Engine-Modell wird in dieser Fassung nicht als Kernbaustein gefuehrt. Belegt sind heute die Begrenzungen:

| Begrenzung | Beleg |
|---|---|
| Denken autonom, Handeln kontrolliert | [Q1] |
| Produktive Aenderungen nicht autonom | [Q1] |
| Sicherheitsregeln nicht autonom veraendern | [Q1] |
| Risiko fuehrt zur Eskalation | [Q1] |

## Simulation und Validierung

Das Material kennt bereits Validierung, Luecken und Statuswerte.

| Element | Beleg | Einstufung |
|---|---|---|
| Simulation | [Q3] | Implementiertes Konzept |
| Bewertungsfragen | [Q3] | Implementiertes Konzept |
| Statuswerte | [Q3] | Implementiertes Konzept |

## Beispielablauf anhand eines Testfalls

### Rack-Hitzestau

```text
Messwerte zeigen Temperaturgradient
-> Cognitive Core bildet Ursachenwege
-> HYPOTHESIS werden geprueft
-> unpassende Wege werden als DEAD_ENDS gespeichert
-> tragfaehiger Weg wird Loesungsknoten
-> Checkliste fuehrt zur realen Pruefung
-> Protokoll sichert das Ergebnis
```

Die drei vorhandenen Testfaelle decken bereits Temperatur, Kapazitaet und Backup-Last ab [Q4][Q5][Q6].

## Kurzfazit

Architektonisch ist GCA im aktuellen Material ueber Cognitive Core, Knowledge Cascade, Governance-Grenzen und Simulation greifbar. Wissensknoten bleibt der interne Oberbegriff, waehrend Loesungsknoten nach aussen der sichtbarste Typ bleibt. Nicht belegte Zusatzschichten gehoeren in dieser Fassung nicht zur aktiven Kernarchitektur.

## Interne Belege

- [Q1] [GEDANKENSPIEL_FRAMEWORK_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\00_MASTER\GEDANKENSPIEL_FRAMEWORK_v0.1.md)
- [Q2] [REGISTRY_ERWEITERUNG_FRAMEWORKS_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\02_REGISTRY_ERWEITERUNG\REGISTRY_ERWEITERUNG_FRAMEWORKS_v0.1.md)
- [Q3] [SIMULATIONSPRINZIP_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\SIMULATIONSPRINZIP_v0.1.md)
- [Q4] [TESTFALL_01_HITZESTAU.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_01_HITZESTAU.md)
- [Q5] [TESTFALL_02_RAM_KAPAZITAET.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_02_RAM_KAPAZITAET.md)
- [Q6] [TESTFALL_03_BACKUPFENSTER.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_03_BACKUPFENSTER.md)
