# Governed Cognitive Architecture (GCA) v1.0

## 1. Executive Summary

Warum existiert dieses Kapitel?

Dieses Kapitel erklaert in kurzer Form, welches Problem GCA adressiert, was die Architektur leistet und wo ihre aktuellen Grenzen liegen.

`Kategorie: Konzept`

GCA ist eine Governance- und Architekturgrundlage fuer langfristig lernende und kontrollierbare KI-Systeme. Sie beschreibt kein AGI-Versprechen und kein fertiges Produkt. Sie beschreibt ein mehrschichtiges Architekturmodell, das Denken, Wissen, Lernen, Sicherheit und Begrenzung systematisch trennt.

`Kategorie: Architektur`

Der heute am besten belegte Kern des Projekts liegt in drei Bereichen:

- geordnete Problemverarbeitung ueber mehrere Loesungswege
- Wissensverdichtung in strukturierte Wissensobjekte
- klare Grenzen zwischen autonomem Denken und kontrolliertem Handeln

`Kategorie: Implementiert`

Im Bestand bereits klar beschrieben sind Wissenskaskade, Loesungsknoten, Checklisten, Protokolle, Eskalationslogik und das Simulationsprinzip mit drei Startfaellen.

`Kategorie: Hypothese`

Noch nicht ausreichend belegt sind die philosophische Operationalisierung, die fuenf Grundgesetze, eine formale Governance Engine, ein ausgearbeiteter Learning Layer und ein technisch beschriebener Security Layer.

Kernaussagen

- GCA ist eine Architekturgrundlage, keine fertige AGI.
- Der Kern ist tragfaehig, aber die Gesamtarchitektur ist ungleich reif.
- Jede externe Darstellung muss belegte Architektur und offene Theorie sauber trennen.

## 2. Historische Entwicklung

Warum existiert dieses Kapitel?

Dieses Kapitel zeigt den Reifeprozess der Architektur und ordnet historische Begriffe ein, statt sie still zu loeschen.

`Kategorie: Konzept`

Die Architektur entstand nicht als fertiges Zielbild. Sie entwickelte sich schrittweise aus frueheren Modellen und Arbeitsbegriffen.

| Phase | Historischer Begriff | Neue Erkenntnis | Kategorie |
|---|---|---|---|
| 1 | Gedankenspiel Framework | Wissen muss dauerhaft erhalten bleiben. | Konzept |
| 2 | Unterbewusstseinsmodell | Das System soll Probleme ausserhalb der aktiven Arbeitszeit weiterverarbeiten. | Konzept |
| 3 | Abend-Reasoner | Problembearbeitung braucht eine eigene Denk-Instanz. | Konzept |
| 4 | Wissensverdichtung | Rohmaterial muss verdichtet werden. | Architektur |
| 5 | Knowledge Cascade | Wissensverdichtung ist ein eigener Prozess, nicht die Gesamtarchitektur. | Architektur |
| 6 | Governance | Wissen allein reicht nicht, Handlungsgrenzen sind notwendig. | Architektur |
| 7 | GCA | Die Bausteine werden zu einer mehrschichtigen Gesamtarchitektur zusammengefuehrt. | Architektur |

`Kategorie: Architektur`

Historische Begriffe bleiben erhalten, aber nur noch in dieser Rolle:

- `Gedankenspiel Framework` als Ursprungstitel
- `Unterbewusstseinsmodell` als fruehes Gesamtprinzip
- `Abend-Reasoner` als Vorform des spaeteren Cognitive Layer

Kernaussagen

- Historische Begriffe werden nicht geloescht.
- `GCA` ist der einzige offizielle Hauptname der Gegenwartsarchitektur.
- Historische Begriffe gehoeren in die Entwicklung, nicht in die aktuelle Terminologie.

## 3. Problemstellung

Warum existiert dieses Kapitel?

Dieses Kapitel beschreibt, welche Defizite heutige KI-Systeme aus Sicht des Projekts adressiert werden sollen.

| Problem | Beschreibung | Kategorie |
|---|---|---|
| Wissensverlust | Erkenntnisse bleiben nicht dauerhaft in einer klaren Struktur erhalten. | Architektur |
| Fehlende Nutzung negativer Erfahrung | Verworfenes Wissen verschwindet statt spaeteren Entscheidungen zu helfen. | Architektur |
| Geringe Nachvollziehbarkeit | Begruendung, Evidenz und Umsetzung sind oft nicht sauber gekoppelt. | Architektur |
| Ueberdehnte Autonomie | Vorschlag und produktive Aktion werden zu leicht vermischt. | Architektur |
| Fehlende Validierung | Gute Architekturideen bleiben unbelegt, wenn sie nicht gegen Faelle geprueft werden. | Implementiert |

`Kategorie: Hypothese`

Weitere Problembegriffe wie Kontext-Kollaps, unendliches Memory-Wachstum oder formale Wertentrennung sind plausibel, aber im Bestand noch nicht hart ausgearbeitet.

Kernaussagen

- Das Projekt reagiert auf reale Strukturdefizite, nicht nur auf Modellleistung.
- Der Kern des Problems ist fehlende kontrollierte Langzeitverarbeitung.
- Nicht jeder moderne Problembegriff ist im Bestand schon gleich stark belegt.

## 4. Architekturrahmen

Warum existiert dieses Kapitel?

Dieses Kapitel legt die offizielle Zielarchitektur fest und markiert fuer jede Ebene ihren aktuellen Reifegrad.

| Ebene | Bezeichnung | Rolle | Reifegrad | Kategorie |
|---|---|---|---|---|
| 0 | Philosophische Grundlage | ethische Bewertungsmodelle | schwach belegt | Philosophie |
| 1 | Unveraenderlicher Werterahmen | fuenf Grundgesetze | nicht ausformuliert | Konzept |
| 2 | Governance Engine | Moral, Evidenz, Verantwortung, Unsicherheit, Folgen, Konflikte | teilweise belegt | Konzept |
| 3 | Cognitive Layer | Denken, Planen, Problemlosen, Reasoning | stark belegt | Architektur |
| 4 | Knowledge Layer | DAILY_DUMP, HYPOTHESIS, DEAD_ENDS, Loesungsknoten, Checklisten, Protokolle | mittel belegt | Architektur |
| 5 | Learning Layer | Feedback, Lernmetriken, Confidence, Verbesserung, Qualitaet, Komplexitaet | schwach belegt | Hypothese |
| 6 | Security Layer | AEGIS, Evidence, Canary, Hydra, Scope Guard, Emergency Stop, Dual Kernel | schwach belegt | Konzept |

Kernaussagen

- Die offizielle Architektur besteht aus sieben Ebenen.
- Nicht alle Ebenen sind gleich gut belegt.
- Ebene 3 und 4 sind derzeit der tragende Kern.

## 5. Ebene 0 Philosophische Grundlage

Warum existiert dieses Kapitel?

Dieses Kapitel trennt ethische Bewertungsmodelle vom festen Werterahmen.

| Perspektive | Rolle in GCA | Kategorie |
|---|---|---|
| Kant | Pflicht, Regelbindung, Wuerde | Philosophie |
| Aristoteles | Tugend, Mass, praktische Klugheit | Philosophie |
| Rawls | Fairness und gerechte Abwaegung | Philosophie |
| Stoiker | Selbstkontrolle und Besonnenheit | Philosophie |
| Nietzsche | Perspektivkritik und Motivpruefung | Philosophie |
| Schopenhauer | Leidvermeidung und Mitgefuehl | Philosophie |

`Kategorie: Konzept`

Diese Modelle bilden keine Grundgesetze. Sie bilden unterschiedliche Perspektiven fuer schwierige Entscheidungen.

`Kategorie: Hypothese`

Wie diese Perspektiven spaeter in konkrete Bewertungslogik ueberfuehrt werden, ist im Bestand noch nicht beschrieben.

Kernaussagen

- Philosophie ist Bewertungsrahmen, nicht Werterahmen.
- Die philosophische Ebene ist aktuell nur konzeptionell vorhanden.
- Ihre spaetere Operationalisierung bleibt eine Forschungsaufgabe.

## 6. Ebene 1 Unveraenderlicher Werterahmen

Warum existiert dieses Kapitel?

Dieses Kapitel markiert die Stelle, an der die spaeteren fuenf Grundgesetze verankert werden sollen.

`Kategorie: Konzept`

Der Werterahmen soll nicht lernbar, nicht automatisch erweiterbar und nicht vom System selbst veraenderbar sein.

`Kategorie: Hypothese`

Die fuenf Grundgesetze sind im aktuellen Projektbestand noch nicht explizit formuliert. Der Platz im Architekturmodell ist definiert, der Inhalt noch nicht.

Kernaussagen

- Ebene 1 ist im Zielbild zentral.
- Der Platz ist klar, die Inhalte fehlen noch.
- Jede spaetere Fassung muss diese Luecke offen kennzeichnen.

## 7. Ebene 2 Governance Engine

Warum existiert dieses Kapitel?

Dieses Kapitel definiert, was die Governance Engine leisten soll und was im Bestand davon bereits angelegt ist.

| Aufgabe | Ziel | Status | Kategorie |
|---|---|---|---|
| Moral bewerten | pruefen, ob eine Handlung verantwortbar ist | offen | Konzept |
| Evidenz bewerten | pruefen, wie belastbar eine Aussage ist | teilweise angelegt | Architektur |
| Verantwortung trennen | Vorschlag und Freigabe auseinanderhalten | belegt | Architektur |
| Unsicherheit markieren | Risiko nicht verdecken | belegt | Architektur |
| Folgen pruefen | Kurz- und Langzeitfolgen bewerten | offen | Hypothese |
| Konflikte bearbeiten | konkurrierende Kriterien abwaegen | offen | Hypothese |

`Kategorie: Architektur`

Im Bestand bereits greifbar sind Eskalation bei Risiko, Freigabepflicht fuer kritische Aktionen und die Trennung von Denken und Handeln.

Kernaussagen

- Die Governance Engine ist im Zielbild eine Schluesselinnovation.
- Im Bestand sind erst Teilfunktionen vorhanden.
- Die Engine darf nicht staerker behauptet werden, als sie aktuell ausgearbeitet ist.

## 8. Ebene 3 Cognitive Layer

Warum existiert dieses Kapitel?

Dieses Kapitel beschreibt den derzeit staerksten funktionalen Kern des Projekts.

| Element | Rolle | Kategorie |
|---|---|---|
| Problemverstehen | Ausgangslage korrekt fassen | Architektur |
| Mehrwege-Denken | mehrere Loesungswege pruefen | Architektur |
| Bedeutungstreue | Problem nicht umdeuten | Architektur |
| Iterationsgrenze | Suche begrenzen und Eskalation ermoeglichen | Architektur |
| Reasoning | Hypothesen und Folgeschritte bilden | Architektur |

`Kategorie: Implementiert`

Der Bestand beschreibt diese Logik bereits ueber Entscheidungsbaum, Iterationsregel und Eskalation bei Risiko.

Kernaussagen

- Ebene 3 ist die am besten belegte Denkschicht.
- Die Trennung von Denken und Handeln bleibt auch hier zentral.
- Dieser Layer ist bereits gut genug beschrieben, um als Kernarchitektur zu gelten.

## 9. Ebene 4 Knowledge Layer

Warum existiert dieses Kapitel?

Dieses Kapitel definiert den aktuellen Wissenskern und trennt Objekte von Prozessen.

`Kategorie: Architektur`

Der Knowledge Layer enthaelt aktuell folgende Wissensobjekte:

| Objekt | Rolle | Kategorie |
|---|---|---|
| DAILY_DUMP | Rohmaterial des Tages | Architektur |
| HYPOTHESIS | gepruefter Denkweg | Architektur |
| DEAD_ENDS | verworfene Wege als negatives Wissen | Architektur |
| Loesungsknoten | tragfaehige Loesung mit Begruendung und Nachweis | Architektur |
| Checklisten | geplante Umsetzung | Implementiert |
| Protokolle | dokumentierte Umsetzung | Implementiert |

`Kategorie: Architektur`

`Wissensknoten` ist der interne Oberbegriff. Die einzelnen Typen sind konkrete Spezialisierungen davon.

`Kategorie: Architektur`

`Historie` ist kein eigener Architekturbaustein. Historie entsteht aus dem Verlauf von DAILY_DUMP, HYPOTHESIS, DEAD_ENDS, Loesungsknoten, Checklisten und Protokollen.

`Kategorie: Architektur`

`Knowledge Cascade` bezeichnet ausschliesslich den Verdichtungsprozess vom Rohmaterial zum strukturierten Wissensobjekt. Sie bezeichnet nicht die Gesamtarchitektur.

Kernaussagen

- Ebene 4 ist der zweite starke Kernbereich der Architektur.
- `Wissensknoten` ist Oberbegriff, `Loesungsknoten` ist ein zentraler Typ.
- `Knowledge Cascade` ist Prozessname, nicht Systemname.

## 10. Ebene 5 Learning Layer

Warum existiert dieses Kapitel?

Dieses Kapitel markiert den Ort, an dem Lernen spaeter messbar und kontrollierbar gemacht werden soll.

| Element | Rolle | Status | Kategorie |
|---|---|---|---|
| Feedback | Rueckfuehrung realer Ergebnisse | offen | Hypothese |
| Lernmetriken | Verbesserung messbar machen | offen | Hypothese |
| Confidence | Unsicherheit quantifizieren | offen | Hypothese |
| Verbesserung | spaetere Leistung steigern | offen | Hypothese |
| Qualitaet | Ergebnisguete absichern | offen | Hypothese |
| Komplexitaet | Schwierigkeit von Faellen bewerten | offen | Hypothese |

`Kategorie: Implementiert`

Der Bestand besitzt bereits einen Validierungsansatz ueber Simulation, Bewertungsfragen und Statuswerte. Das ist aber noch kein vollstaendiger Learning Layer.

Kernaussagen

- Ebene 5 ist im Zielbild wichtig, aber im Bestand noch schwach.
- Validierung ist vorhanden, Lernen im engeren Sinn noch nicht.
- Diese Ebene darf nicht als ausgereift dargestellt werden.

## 11. Ebene 6 Security Layer

Warum existiert dieses Kapitel?

Dieses Kapitel beschreibt die offizielle Sicherheitslage des Modells, ohne technische Reife vorzutaeuschen.

| Element | Rolle | Status | Kategorie |
|---|---|---|---|
| AEGIS | Schutz- und Kontrollinstanz | offen | Konzept |
| Evidence | Evidenzsicherung | offen | Konzept |
| Canary | Fruehwarnung | offen | Konzept |
| Hydra | Abwehr oder Mehrfachschutz | offen | Konzept |
| Scope Guard | Begrenzung des Handlungsspielraums | offen | Konzept |
| Emergency Stop | Not-Aus fuer riskante Prozesse | offen | Konzept |
| Dual Kernel | Trennung kritischer Funktionen | offen | Konzept |

`Kategorie: Architektur`

Im aktuellen Bestand sind nur die allgemeinen Schutzprinzipien klar belegt:

- produktive Systeme nicht autonom veraendern
- Sicherheitsregeln nicht autonom veraendern
- bei Risiko eskalieren

Kernaussagen

- Die Sicherheitsidee ist vorhanden.
- Die technischen Unterkomponenten sind noch nicht beschrieben.
- Ebene 6 ist derzeit konzeptionell, nicht implementiert.

## 12. Validierung

Warum existiert dieses Kapitel?

Dieses Kapitel beschreibt, wie GCA gegen bekannte Faelle geprueft werden soll.

`Kategorie: Implementiert`

Das Projekt besitzt bereits ein Simulationsprinzip:

1. echten Fall auswaehlen
2. Ausgangslage wiederherstellen
3. bekannte Loesung ausblenden
4. System virtuell laufen lassen
5. Ergebnis mit realer Loesung vergleichen
6. Luecken dokumentieren

| Testfall | Fokus | Kategorie |
|---|---|---|
| Hitzestau im Rack | Temperatur und Luftstrom | Implementiert |
| RAM-Kapazitaet | Ressourcen und Machbarkeit | Implementiert |
| Backupfenster | Lastgrenzen und Betriebszeit | Implementiert |

`Kategorie: Forschungsfrage`

Noch offen ist, ob drei Startfaelle fuer eine belastbare Gesamtvalidierung ausreichen.

Kernaussagen

- Validierung ist einer der glaubwuerdigsten Teile des Projekts.
- Es gibt bereits konkrete Testfaelle.
- Es fehlen dokumentierte Durchlaeufe und Vergleichsergebnisse.

## 13. Forschungsfragen

Warum existiert dieses Kapitel?

Dieses Kapitel sammelt die Fragen, die aus dem aktuellen Reifegrad des Projekts folgen.

| Frage | Kategorie |
|---|---|
| Wie werden die fuenf Grundgesetze formal beschrieben? | Forschungsfrage |
| Wie wird Philosophie in Governance ueberfuehrt, ohne beliebig zu werden? | Forschungsfrage |
| Wie wird Wissensknoten-Datenlogik formalisiert? | Forschungsfrage |
| Wie wird Lernen messbar? | Forschungsfrage |
| Wie wird Ebene 6 technisch konkret? | Forschungsfrage |
| Wie viele und welche Testfaelle reichen fuer ernsthafte Validierung? | Forschungsfrage |

Kernaussagen

- Die offenen Fragen sind substanziell und nicht nur kosmetisch.
- Vor allem Ebene 0, 1, 5 und 6 brauchen Forschung statt Formulierungskosmetik.
- Die Forschungsfragen ergeben sich direkt aus dem Architekturgefuege.

## 14. Roadmap

Warum existiert dieses Kapitel?

Dieses Kapitel ordnet die naechsten Schritte nach Risiko und Nutzen.

| Zeithorizont | Schritt | Kategorie |
|---|---|---|
| kurzfristig | Terminologie vereinheitlichen | Architektur |
| kurzfristig | Wissensknoten-Datenlogik definieren | Architektur |
| kurzfristig | Simulationsdurchlaeufe dokumentieren | Implementiert |
| mittelfristig | Governance Engine formal beschreiben | Konzept |
| mittelfristig | Learning Layer mit Metriken ausbauen | Hypothese |
| mittelfristig | Registry-Anbindung terminologisch migrieren | Architektur |
| langfristig | Security Layer technisch ausarbeiten | Konzept |
| langfristig | Vergleichsstudien und groessere Validierung | Forschungsfrage |

Kernaussagen

- Zuerst braucht das Projekt Konsistenz und Validierung.
- Danach braucht es Governance- und Lernformalismus.
- Sicherheits- und Vergleichsstudien gehoeren spaeter, nicht vorher.
