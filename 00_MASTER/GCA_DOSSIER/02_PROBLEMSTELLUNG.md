# 02 Problemstellung

## Ausgangslage

Das Projektmaterial beschreibt kein reines Antwortsystem. Es beschreibt ein System, das Probleme, Beobachtungen, Messwerte und offene Fragen sammelt, spaeter autonom verarbeitet und daraus dauerhaft nutzbares Wissen erzeugen soll [Q1].

Damit reagiert das Projekt auf typische Defizite heutiger KI-Systeme.

## Welche Probleme heutige KI-Systeme besitzen

| Problem | Warum es problematisch ist | Interner Bezug | Kategorie |
|---|---|---|---|
| Kein sauberes Langzeitwissen | Erkenntnisse verschwinden oder bleiben unstrukturiert. | Das Projekt fordert Wissenskaskade, Wissensknoten und Loesungsknoten [Q1]. | Architekturentscheidung |
| Fehlende Nutzung von Nicht-Loesungen | Verworfenes Wissen geht verloren. | Das Projekt speichert gepruefte Nicht-Loesungen ausdruecklich [Q1]. | Architekturentscheidung |
| Unklare Entscheidungswege | Spaeter ist nicht nachvollziehbar, warum etwas empfohlen wurde. | Das Projekt fordert Begruendung, Nachweis, Checklisten und Protokolle [Q1]. | Architekturentscheidung |
| Zu viel Autonomie in kritischen Kontexten | Ein System koennte Vorschlag und Eingriff vermischen. | Das Projekt trennt Denken und Handeln hart [Q1]. | Architekturentscheidung |
| Lernen ohne Sicherheitsgrenzen | Neue Muster koennten unkontrolliert uebernommen werden. | Sicherheitsregeln duerfen nicht autonom veraendert werden [Q1]. | Architekturentscheidung |
| Keine geregelte Validierung | Gute Ideen bleiben unbelegt. | Das Projekt fordert virtuelle Simulation mit bekannten Faellen [Q3]. | Implementiertes Konzept |

## Was das Projekt als Kernproblem versteht

Das Projekt geht von einer einfachen Grundannahme aus:

```text
Eine brauchbare KI braucht nicht nur Antworten.
Sie braucht:
- Bedeutungstreue
- mehrere gepruefte Wege
- dokumentierte Nicht-Loesungen
- klare Freigabegrenzen
- nachvollziehbare Nachweise
```

Diese Logik ist im Quellmaterial mehrfach angelegt:

- das Problem darf weiterentwickelt, aber nicht umgedeutet werden [Q1]
- es gibt eine feste Iterationsgrenze mit Eskalation [Q1]
- Ergebnisse muessen ueber Checklisten und Protokolle nachvollziehbar bleiben [Q1]
- bekannte Faelle sollen spaeter gegen das System getestet werden [Q3]

## Interne Evidenz im Projekt

### Wissensverlust als Problem

Das Projekt fuehrt Wissenskaskade, Wissensknoten und Loesungsknoten ein, weil rohes Tageswissen allein nicht ausreicht [Q1].

### Fehlende Nachvollziehbarkeit als Problem

Ein Loesungsknoten enthaelt nicht nur eine Loesung, sondern auch Begruendung, verworfene Wege, Nachweis und Status [Q1].

### Fehlende Governance als Problem

Produktive Aenderungen, Neustarts, Loeschungen und Sicherheitsumbauten sind nicht autonom erlaubt [Q1].

### Fehlende Validierung als Problem

Die Architektur soll nicht nur behauptet, sondern an realen, bereits geloesten Faellen geprueft werden [Q3][Q4][Q5][Q6].

## Was im Material noch nicht direkt belegt ist

Die folgenden Begriffe stehen im Master-Prompt, sind aber in den aktuellen Projektdateien nicht detailliert ausgearbeitet:

- Kontext-Kollaps
- Vektordatenbank-Wachstum
- Trennung zwischen Wissen und Werten als explizites Modell
- formale Governance-Mathematik
- Langzeitgedaechtnis als technische Implementierung

Diese Punkte sind fuer die Problemstellung plausibel, aber derzeit nur als erweiterbare Rahmung nutzbar, nicht als intern voll belegte Projektrealitaet.

## Kurzfazit

Die Problemstellung des Projekts ist klar: Heutige KI ist aus Sicht des Materials zu kurzatmig, zu wenig nachvollziehbar und zu wenig kontrolliert. Das Projekt antwortet darauf mit Wissensverdichtung, gespeicherten Nicht-Loesungen, harten Freigabegrenzen und simulativer Ueberpruefung.

## Interne Belege

- [Q1] [GEDANKENSPIEL_FRAMEWORK_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\00_MASTER\GEDANKENSPIEL_FRAMEWORK_v0.1.md)
- [Q3] [SIMULATIONSPRINZIP_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\SIMULATIONSPRINZIP_v0.1.md)
- [Q4] [TESTFALL_01_HITZESTAU.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_01_HITZESTAU.md)
- [Q5] [TESTFALL_02_RAM_KAPAZITAET.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_02_RAM_KAPAZITAET.md)
- [Q6] [TESTFALL_03_BACKUPFENSTER.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\TESTFALL_03_BACKUPFENSTER.md)
