# 03 Stand Der Technik

## Zweck dieses Kapitels

Dieses Kapitel trennt zwischen:

- allgemein bekanntem Stand der Technik
- projektspezifischen GCA-Konzepten

Es nutzt fuer den allgemeinen Teil bewusst nur knappe, allgemein bekannte Beschreibungen. Wo das Projektmaterial mehr sagt, wird dies gesondert markiert.

## Vergleichsrahmen

| Systemtyp | Was heute ueblich ist | Was im Projektmaterial fehlt oder kritisch gesehen wird | Kategorie |
|---|---|---|---|
| Heutige LLMs | starke Textgenerierung und Schlussfolgern in Einzelsitzungen | kein im Material belegter Mechanismus fuer dauerhafte Loesungsknoten, Nicht-Loesungen und Freigabeprotokolle | allgemein bekannter Stand der Technik |
| Klassische Agentensysteme | koennen Aufgabenketten planen und Werkzeuge ausfuehren | im Projektmaterial fehlt dort meist die harte Trennung zwischen Denken und Handeln als Leitregel | allgemein bekannter Stand der Technik |
| RAG | holt Wissen aus externen Quellen nach | im Projektmaterial fehlt dort die Verdichtung zu dauerhaften Loesungsknoten und DEAD_END-artigem Negativwissen | allgemein bekannter Stand der Technik |
| Memory-Systeme | speichern fruehere Inhalte oder Profile | im Projektmaterial fehlt dort die geregelte Ueberfuehrung in Checklisten, Protokolle und Wartungsplaene | allgemein bekannter Stand der Technik |

## Was GCA gegenueber dem Stand der Technik einfuehrt

| GCA-Baustein | Im Projekt belegt | Unterschied zum ueblichen Stand |
|---|---|---|
| Wissenskaskade | ja [Q1] | Wissen wird schrittweise verdichtet statt nur gespeichert. |
| Nicht-Loesungen als Orientierungswissen | ja [Q1] | Verworfenes wird systematisch behalten. |
| Loesungsknoten mit Nachweisstruktur | ja [Q1] | Ergebnis, Begruendung und Evidenz bleiben gekoppelt. |
| Checkliste wird Protokoll | ja [Q1] | Wissen wird in reale und pruefbare Handlung ueberfuehrt. |
| Harte Autonomiegrenzen | ja [Q1] | Analyse und Eingriff bleiben getrennt. |
| Simulation mit bekannten Faellen | ja [Q3] | Die Architektur soll gegen echte Vergleichsfaelle gehalten werden. |

## ASCII-Uebersicht

```text
Heutiger Standard
-> Antwort
-> eventuell Memory
-> eventuell RAG

GCA-Zielbild
-> Problem
-> mehrere Wege
-> Nicht-Loesungen
-> Loesungsknoten
-> Checkliste
-> Protokoll
-> Wartungsplan
-> spaeteres Erfahrungswissen
```

## Wo das Projektmaterial noch keine belastbare Abgrenzung liefert

Die folgenden Aussagen waeren fuer einen harten Stand-der-Technik-Vergleich wichtig, sind aber in den internen Dokumenten noch nicht belegt:

- ob GCA gegenueber bestehenden Memory-Systemen messbar bessere Langzeitstabilitaet liefert
- ob die Governance Engine Entscheidungen besser kalibriert als heutige Guardrail-Systeme
- ob die Wissenskaskade skalierbar bleibt
- ob philosophische Perspektiven praktisch bessere Entscheidungen liefern

Diese Punkte gehoeren spaeter in Forschung und Validierung, nicht in bereits gesicherte Abgrenzung.

## Was bereits Architektur ist und was noch Vision bleibt

| Aussage | Einstufung |
|---|---|
| Wissenskaskade, Entscheidungsbaum, Loesungsknoten, Freigabeprozess | Architekturentscheidung |
| Simulation mit Startfaellen | Implementiertes Konzept |
| Learning Layer mit Metriken und Tags | Hypothese |
| Security Layer mit AEGIS, Hydra, Hypervisor, Killswitch | Vision |
| Philosophische Mehrperspektivenbewertung | Philosophische Grundlage |

## Kurzfazit

Im Vergleich zum ueblichen Stand der Technik bringt das Projekt vor allem mehr Struktur fuer Wissensverdichtung, dokumentierte Nicht-Loesungen und kontrollierte Ueberfuehrung in reale Handlungsablaeufe. Die staerksten Abgrenzungen sind bereits architektonisch angelegt, aber noch nicht empirisch bewiesen.

## Interne Belege

- [Q1] [GEDANKENSPIEL_FRAMEWORK_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\00_MASTER\GEDANKENSPIEL_FRAMEWORK_v0.1.md)
- [Q3] [SIMULATIONSPRINZIP_v0.1.md](E:\Projekte\01_Aktiv\Gedankenspiel 2\03_SIMULATION_UND_VALIDIERUNG\SIMULATIONSPRINZIP_v0.1.md)
