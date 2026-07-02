# 00 Architektur Audit

## Projektuebersicht

Warum existiert dieses Kapitel?

Dieses Kapitel zeigt, wie das Projekt derzeit aufgebaut ist und welche Dokumenttypen tatsaechlich vorliegen.

| Bereich | Inhalt | Beobachtung |
|---|---|---|
| `README.md` | Einstieg und Dateiliste | liefert nur eine Orientierung, aber keinen belastbaren Dokumentstatus |
| `00_MASTER/` | Haupttexte und spaetere Konsolidierungen | enthaelt gleichzeitig Ursprung, Zwischenstand und neue Gutachterfassungen |
| `00_MASTER/GCA_DOSSIER/` | kapitelweise Dossierfassung | ist die staerkste aktuelle Arbeitsfassung, aber nicht voll konsistent |
| `02_REGISTRY_ERWEITERUNG/` | Registry-Vorschlag | klar abgegrenzt, aber noch auf altem Begriffsfeld |
| `03_SIMULATION_UND_VALIDIERUNG/` | Validierungsprinzip und Testfaelle | methodisch wichtig, aber noch ohne echte Durchlaeufe |

Kernaussagen

- Das Projekt besitzt einen klaren Kernbestand, aber keinen einzigen kanonischen Dokumentstand.
- `00_MASTER/` und `00_MASTER/GCA_DOSSIER/` ueberschneiden sich stark.
- Simulation und Registry sind sinnvoll getrennt, aber sprachlich noch nicht auf den neuen Gesamtstand migriert.

## Dokumentstruktur

Warum existiert dieses Kapitel?

Dieses Kapitel zeigt, welche Dokumente existieren, welche sich ueberschneiden und welche fuer einen klaren Zielstand fehlen.

| Datei | Rolle | Bewertung |
|---|---|---|
| `README.md` | Einstieg | leicht anpassen |
| `00_MASTER/GEDANKENSPIEL_FRAMEWORK_v0.1.md` | historischer Ursprungstext | behalten als Historie |
| `00_MASTER/GOVERNED_COGNITIVE_ARCHITECTURE_GCA_v1.0.md` | aktuelle Hauptfassung | stark ueberarbeiten oder durch kanonische Fassung ersetzen |
| `00_MASTER/GCA_WIDERSPRUECHE_UND_OFFENE_SPANNUNGEN_v1.0.md` | alte Spannungsdatei | archivieren |
| `00_MASTER/GCA_DOSSIER/*.md` | kapitelweises Dossier | teilweise behalten, aber nicht mehr als kanonischen Stand fuehren |
| `02_REGISTRY_ERWEITERUNG/REGISTRY_ERWEITERUNG_FRAMEWORKS_v0.1.md` | Registry-Erweiterung | leicht anpassen |
| `03_SIMULATION_UND_VALIDIERUNG/*.md` | Validierungsbasis | behalten |

Fehlende Dokumente im bisherigen Bestand:

- ein echter Architektur-Audit
- eine kanonische Hauptfassung mit festem Architekturrahmen 0 bis 6
- eine klare Reviewdatei im Gutachterstil

Kernaussagen

- Die bisherige Dokumentstruktur ist produktiv, aber ueberlappt zu stark.
- Es fehlt ein klar priorisierter Zielstand.
- Das Audit-, Migrations- und Review-Set war bislang nicht vorhanden.

## Terminologie

Warum existiert dieses Kapitel?

Dieses Kapitel zeigt, welche Begriffe parallel verwendet werden und wo Vereinheitlichung noetig ist.

| Begriff | Aktuelle Rolle | Problem | Empfehlung |
|---|---|---|---|
| `Governed Cognitive Architecture (GCA)` | neuer Hauptname | korrekt gesetzt, aber nicht durchgaengig dominant | als einziger offizieller Hauptname behalten |
| `Gedankenspiel Framework` | Ursprungstitel | steht noch in Quell- und Registrytexten | als historischer Begriff erhalten |
| `Unterbewusstseinsmodell` | fruehes Gesamtprinzip | ueberlappt mit Gesamtarchitektur | nur im Historienkapitel fuehren |
| `Abend-Reasoner` | fruehe Denk-Instanz | ueberlappt mit Cognitive Layer | als historische Unterkomponente fuehren |
| `Wissenskaskade` | Verdichtungsprozess | teils als Gesamtarchitektur missverstanden | nur fuer Verdichtungsprozess verwenden |
| `Knowledge Cascade` | spaetere englische Variante | Bedeutungsnaehe zu Wissenskaskade | als englischer Fachbegriff fuer denselben Prozess fuehren |
| `Wissensknoten` | interner Oberbegriff | noch nicht formal ausgeschrieben | definieren und behalten |
| `Loesungsknoten` | sichtbarer Ergebnistyp | robust und klar | behalten |
| `Nicht-Loesungen` | Ursprungsterm | spaeter durch `DEAD_ENDS` ersetzt | als historische Vorstufe von `DEAD_ENDS` dokumentieren |
| `Historie` | teils Datenbaustein, teils Verlaufseffekt | inkonsistent | nicht als eigener Architekturbaustein fuehren |

Kernaussagen

- Der Hauptbegriff ist entschieden, aber die Altbegriffe sind noch nicht sauber einsortiert.
- `Wissenskaskade` und `Knowledge Cascade` muessen als Prozess, nicht als Gesamtarchitektur, definiert werden.
- `Wissensknoten` braucht eine harte Definition, sonst bleibt der Wissenskern unscharf.

## Architektur

Warum existiert dieses Kapitel?

Dieses Kapitel bewertet, welche Architektur das Projekt derzeit tatsaechlich beschreibt und wo Zielbild und Bestand auseinanderlaufen.

### Ist-Architektur im Bestand

| Bereich | Im Material robust belegt | Status |
|---|---|---|
| Cognitive Core / Cognitive Layer | ja | stark |
| Wissensverdichtung / Knowledge Cascade | ja | stark |
| Loesungsknoten, Checklisten, Protokolle | ja | stark |
| Governance-Grenzen | ja | stark |
| Simulation und Testfaelle | ja | mittel bis stark |

### Zielarchitektur laut Migrationsprompt

| Ebene | Sollzustand | Im Bestand belegt | Bewertung |
|---|---|---|---|
| 0 Philosophie | ethische Bewertungsmodelle | nein | fehlt |
| 1 Werterahmen | fuenf Grundgesetze | nein | fehlt |
| 2 Governance Engine | Moral, Evidenz, Verantwortung, Unsicherheit, Folgen, Konflikte | teilweise | unvollstaendig |
| 3 Cognitive Layer | Denken, Planen, Problemlosen, Reasoning | ja | belegt |
| 4 Knowledge Layer | DAILY_DUMP, HYPOTHESIS, DEAD_ENDS, Loesungsknoten, Checklisten, Protokolle | teilweise | im Umbau |
| 5 Learning Layer | Feedback, Lernmetriken, Confidence, Verbesserung, Qualitaet, Komplexitaet | nein | fehlt |
| 6 Security Layer | AEGIS, Evidence, Canary, Hydra, Scope Guard, Emergency Stop, Dual Kernel | nein | fehlt |

Kernaussagen

- Die echte Staerke des Projekts liegt derzeit auf Ebene 3 und 4 sowie bei den Handlungsgrenzen.
- Die offizielle Zielarchitektur 0 bis 6 ist als Struktur sinnvoll, aber nur teilweise belegt.
- Jede externe Fassung muss diesen Reifeunterschied offen markieren.

## Konsistenz

Warum existiert dieses Kapitel?

Dieses Kapitel bewertet jedes Dokument nach Konsistenz und Migrationsbedarf.

| Datei | Bewertung | Einstufung | Begruendung |
|---|---|---|---|
| `README.md` | 🟡 | leicht anpassen | verweist auf mehrere Fassungen, aber nicht auf einen klaren Zielstand |
| `00_MASTER/GEDANKENSPIEL_FRAMEWORK_v0.1.md` | 🟢 | behalten | als historische Quelle klar und koharent |
| `00_MASTER/GOVERNED_COGNITIVE_ARCHITECTURE_GCA_v1.0.md` | 🟠 | stark ueberarbeiten | vermischt Kernarchitektur, Historie und nicht belegte Erweiterungen |
| `00_MASTER/GCA_WIDERSPRUECHE_UND_OFFENE_SPANNUNGEN_v1.0.md` | 🟠 | archivieren | ist inhaltlich ueberholt durch spaetere Entscheidungen |
| `00_MASTER/GCA_DOSSIER/01_EXECUTIVE_SUMMARY.md` | 🟠 | stark ueberarbeiten | arbeitet teils noch mit nicht mehr kanonischem Architekturzuschnitt |
| `00_MASTER/GCA_DOSSIER/02_PROBLEMSTELLUNG.md` | 🟡 | leicht anpassen | inhaltlich tragfaehig, stilistisch nicht auf neuen Standard gezogen |
| `00_MASTER/GCA_DOSSIER/03_STAND_DER_TECHNIK.md` | 🟡 | leicht anpassen | inhaltlich brauchbar, aber Kategorien und Terminologie nicht final |
| `00_MASTER/GCA_DOSSIER/04_GCA_ARCHITEKTUR.md` | 🟠 | stark ueberarbeiten | naechste brauchbare Basis, aber noch nicht auf offizielle 0-6-Ebenen gezogen |
| `00_MASTER/GCA_DOSSIER/05_INNOVATIONEN.md` | 🟡 | leicht anpassen | brauchbar, aber noch nicht auf neuen Kapitelstil normiert |
| `00_MASTER/GCA_DOSSIER/06_VORTEILE.md` | 🟡 | leicht anpassen | inhaltlich brauchbar, aber stilistisch uneinheitlich |
| `00_MASTER/GCA_DOSSIER/07_GRENZEN.md` | 🟠 | stark ueberarbeiten | beschreibt alte Kernreduktion statt offiziellem 0-6-Modell |
| `00_MASTER/GCA_DOSSIER/08_FORSCHUNGSFRAGEN.md` | 🟡 | leicht anpassen | gute Grundlage, aber Kategorien nicht durchgaengig |
| `00_MASTER/GCA_DOSSIER/09_ROADMAP.md` | 🟠 | stark ueberarbeiten | enthaelt noch Entscheidungen aus der Kernverengung |
| `00_MASTER/GCA_DOSSIER/10_OFFENE_WIDERSPRUECHE.md` | 🟠 | stark ueberarbeiten | Teile sind durch neue Leitentscheidungen geloest |
| `00_MASTER/GCA_DOSSIER/11_ABSCHLUSSBERICHT.md` | 🟡 | leicht anpassen | gute Kritikbasis, aber noch vor neuem Audit-Stand |
| `02_REGISTRY_ERWEITERUNG/REGISTRY_ERWEITERUNG_FRAMEWORKS_v0.1.md` | 🟡 | leicht anpassen | sprachlich noch auf Gedankenspiel Framework bezogen |
| `03_SIMULATION_UND_VALIDIERUNG/SIMULATIONSPRINZIP_v0.1.md` | 🟢 | behalten | klar, knapp, methodisch brauchbar |
| `03_SIMULATION_UND_VALIDIERUNG/TESTFALL_01_HITZESTAU.md` | 🟢 | behalten | klar und spezifisch |
| `03_SIMULATION_UND_VALIDIERUNG/TESTFALL_02_RAM_KAPAZITAET.md` | 🟢 | behalten | klar und spezifisch |
| `03_SIMULATION_UND_VALIDIERUNG/TESTFALL_03_BACKUPFENSTER.md` | 🟢 | behalten | klar und spezifisch |

Kernaussagen

- Der historische Ursprungstext und die Simulationsdateien sind die konsistentesten Quellen.
- Die spaeteren Konsolidierungen sind brauchbar, aber noch nicht kanonisch.
- Die groesste Schwaeche liegt nicht im Materialmangel, sondern im Nebeneinander mehrerer halbfertiger Zielstaende.

## Redundanzen

Warum existiert dieses Kapitel?

Dieses Kapitel zeigt, welche Inhalte mehrfach erklaert werden und zusammengezogen werden sollten.

| Redundanz | Betroffene Dateien | Empfehlung |
|---|---|---|
| Gesamtueberblick GCA | `GOVERNED_COGNITIVE_ARCHITECTURE_GCA_v1.0.md`, `01_EXECUTIVE_SUMMARY.md`, `04_GCA_ARCHITEKTUR.md` | in eine kanonische Hauptfassung ueberfuehren |
| Spannungen und Widersprueche | `GCA_WIDERSPRUECHE_UND_OFFENE_SPANNUNGEN_v1.0.md`, `10_OFFENE_WIDERSPRUECHE.md` | alte Fassung archivieren, neue behalten |
| Kritik und Bewertung | `11_ABSCHLUSSBERICHT.md`, kuenftige Reviewdatei | Abschlussbericht als intern, Review als offizielles Gutachterdokument fuehren |
| Roadmap und naechste Schritte | `GEDANKENSPIEL_FRAMEWORK_v0.1.md`, `09_ROADMAP.md`, Hauptfassung | in eine offizielle Roadmap ueberfuehren |

Kernaussagen

- Die Dokumentation ist nicht zu duenn, sondern zu mehrfach.
- Die staerkste Verbesserung entsteht durch Konsolidierung, nicht durch neue Kapitelmenge.
- Audit, Hauptfassung und Review muessen die neue Dreierstruktur bilden.

## Historische Entwicklung

Warum existiert dieses Kapitel?

Dieses Kapitel trennt zwischen historischen Begriffen, die erhalten bleiben sollen, und alten Begriffen, die nicht mehr als Gegenwartsarchitektur auftreten duerfen.

| Begriff | Rolle | Empfehlung |
|---|---|---|
| `Gedankenspiel Framework` | Ursprungstitel | behalten im Historienkapitel |
| `Unterbewusstseinsmodell` | fruehes Gesamtprinzip | nur historisch fuehren |
| `Abend-Reasoner` | fruehe Denkkomponente | als historische Vorform des Cognitive Layer fuehren |
| `Wissensverdichtung` | bleibende Grundidee | behalten, aber dem Knowledge Layer zuordnen |
| `Knowledge Cascade` | Verdichtungsprozess | behalten, aber nur als Prozess in Ebene 4 |
| `Governance` | bleibende Kernidee | behalten, aber als Ebene 2 definieren |
| `GCA` | offizieller Hauptname | exklusiv als aktueller Systemname fuehren |

Kernaussagen

- Historische Begriffe muessen nicht geloescht, sondern eingeordnet werden.
- Nur `GCA` darf als aktueller Hauptname auftreten.
- `Knowledge Cascade` darf nicht mehr die Gesamtarchitektur bezeichnen.

## Bewertung

Warum existiert dieses Kapitel?

Dieses Kapitel legt fuer jede Datei die Migrationsentscheidung fest.

| Datei | Entscheidung | Begruendung |
|---|---|---|
| `README.md` | leicht anpassen | muss den kanonischen Zielstand zeigen |
| `GEDANKENSPIEL_FRAMEWORK_v0.1.md` | behalten | wichtigste historische Quelle |
| `GOVERNED_COGNITIVE_ARCHITECTURE_GCA_v1.0.md` | stark ueberarbeiten oder ersetzen | aktueller Haupttext, aber noch inkonsistent |
| `GCA_WIDERSPRUECHE_UND_OFFENE_SPANNUNGEN_v1.0.md` | archivieren | durch neues Audit und neue Widerspruchslogik ueberholt |
| `GCA_DOSSIER/` | stark ueberarbeiten | gute Rohbasis, aber nicht final |
| `REGISTRY_ERWEITERUNG_FRAMEWORKS_v0.1.md` | leicht anpassen | terminologisch migrieren |
| `SIMULATIONSPRINZIP_v0.1.md` | behalten | methodisch klar |
| `TESTFALL_*.md` | behalten | als Validierungsbasis klar |

Kernaussagen

- Nicht alles muss geloescht werden.
- Historische Quellen bleiben, kanonische Zieldokumente werden neu geordnet.
- Archivierung betrifft nur ueberholte Zwischenfassungen.

## Migrationsplan

Warum existiert dieses Kapitel?

Dieses Kapitel legt die beste Reihenfolge fest, damit Konsistenz nicht spaeter wieder zerfaellt.

1. Audit festschreiben.
2. Kanonische Hauptfassung auf offiziellen Architekturrahmen 0 bis 6 migrieren.
3. Terminologie in Executive Summary, Problemstellung, Architektur, Grenzen und Roadmap angleichen.
4. Widerspruchsdatei auf den neuen Zielstand reduzieren.
5. Registry-Dokument sprachlich auf GCA umstellen.
6. README auf kanonische Dokumente fokussieren.
7. Reviewdatei im Gutachterstil schreiben.

Kernaussagen

- Zuerst braucht das Projekt einen Audit.
- Danach braucht es einen kanonischen Zieltext.
- Erst am Ende ist eine belastbare Reviewdatei sinnvoll.
