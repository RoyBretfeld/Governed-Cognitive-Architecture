# GCA Klassenmodell v0.4

## Zweck

Dieses Dokument trennt drei Dinge sauber voneinander:

- `Regelklasse`: wie stark Regeln, Schutzgrenzen oder Compliance den Fall binden
- `Betriebsklasse`: wie stark der Fall in laufende Systeme eingreift
- `Berechtigungsstufe`: wer freigeben oder ausfuehren darf

Diese Trennung soll die bisherigen `teilweise`-Faelle besser verarbeitbar machen.

---

## 1. Leitidee

> Ein Fall ist nicht nur riskant oder nicht riskant. Er hat Regelbindung, Betriebswirkung und Berechtigungsbedarf gleichzeitig.

---

## 2. Regelklassen

| Klasse | Bedeutung | Typische Ausloeser |
|---|---|---|
| R0 | keine besondere Regelbindung | reine Analyse, rein technische Sichtung |
| R1 | normale Betriebsregel | Wartungsregeln, Standardvorgehen, Routinefreigabe |
| R2 | erhoehte Regelbindung | Datenhaltung, Clusterregeln, Netzpfade, Wiederanlauf |
| R3 | starke Regelbindung | Security, Compliance, Restore-Sicherheit, Mandantentrennung |
| R4 | Notfall- oder Schadensbegrenzungsregel | akute Gefaehrdung, Datenverlust, erheblicher Ausfall |

Neue Regel:

> Unklare Regelbindung wird mindestens als R2 behandelt.

---

## 3. Betriebsklassen

| Klasse | Bedeutung | Typische Wirkung |
|---|---|---|
| B0 | keine Produktivwirkung | Analyse, Simulation, Dokumentation |
| B1 | vorbereitender Vorschlag | keine direkte Aenderung, aber konkrete Empfehlung |
| B2 | begrenzte Produktivaenderung | eine VM, ein Volume, ein geplanter Einzeleingriff |
| B3 | systemuebergreifende oder schwer reversible Aenderung | Cluster, Core-Netz, zentrales Storage |
| B4 | akuter produktiver Stoer- oder Notfalleingriff | Zeitdruck, Schadensbegrenzung, hoher Seiteneffekt |

Neue Regel:

> Wenn mehrere produktive Systeme gleichzeitig betroffen sein koennen, mindestens B3.

---

## 4. Berechtigungsstufen

| Stufe | Bedeutung | Typischer Bedarf |
|---|---|---|
| G0 | keine Freigabe notwendig | B0 |
| G1 | fachliche Plausibilisierung | B1 |
| G2 | normale Betriebsfreigabe | B2 |
| G3 | erweiterte Freigabe mit Gegenpruefung | B3 |
| G4 | Notfall- oder Sonderfreigabe | B4 oder R4 |

Die Stufe beantwortet zwei Fragen:

- Wer darf den Vorschlag freigeben?
- Wer darf die reale Aenderung ausfuehren oder bestaetigen?

---

## 5. Bestaetigungsstufen

| Stufe | Bedeutung | Beispiele |
|---|---|---|
| N0 | keine Bestaetigung erforderlich | Analyse ohne Eingriff |
| N1 | einfache technische Bestaetigung | Monitoring, Log, Vergleichsmessung |
| N2 | umsetzungsnahe Bestaetigung | Wartungsprotokoll, zweiter Operator, Funktionspruefung |
| N3 | starke Gegenpruefung | Vier-Augen-Prinzip, Restore-Test, Security-Gegencheck |
| N4 | Notfallbestaetigung mit Nachpruefung | Soforteingriff plus nachgelagerte Aufarbeitung |

---

## 6. Ableitungslogik

```text
Fall aufnehmen
-> Regelklasse bestimmen
-> Betriebsklasse bestimmen
-> daraus Berechtigungsstufe ableiten
-> daraus Bestaetigungsstufe ableiten
-> erst dann Checklisten und Loesungsknoten finalisieren
```

Grundregeln:

- hohe Regelklasse zieht niemals eine niedrigere Berechtigungsstufe nach sich
- hohe Betriebsklasse zieht mindestens gleiche oder hoehere Bestaetigungsstufe nach sich
- R4 oder B4 aktivieren immer Eskalation und Nachpruefpflicht

---

## 7. Standardableitung

| Regelklasse | Betriebsklasse | Mindest-Berechtigung | Mindest-Bestaetigung |
|---|---|---|---|
| R0 | B0 | G0 | N0 |
| R1 | B1 | G1 | N1 |
| R1 bis R2 | B2 | G2 | N2 |
| R2 bis R3 | B3 | G3 | N3 |
| R4 oder B4 | B3 bis B4 | G4 | N4 |

---

## 8. Einordnung der sieben Testfaelle

| Testfall | Regelklasse | Betriebsklasse | Berechtigung | Bestaetigung |
|---|---|---|---|---|
| 01 Hitzestau / Rack-Luftstrom | R1 | B2 | G2 | N2 |
| 02 RAM / Kapazitaetsgrenze | R1 | B2 | G2 | N2 |
| 03 Backupfenster / Betriebsstoerung | R2 | B2 bis B3 | G2 bis G3 | N2 bis N3 |
| 04 Provisioning / RAM und Storage | R2 | B2 bis B3 | G2 bis G3 | N2 bis N3 |
| 05 Kubernetes / Pending und PVC | R2 bis R3 | B3 | G3 | N3 |
| 06 Netzwerk / Switch-Uplink und VLAN | R2 bis R3 | B3 | G3 | N3 |
| 07 NAS oder NetApp / Snapshot-Wachstum | R3 | B3 bis B4 | G3 bis G4 | N3 bis N4 |

---

## 9. Warum das hilft

Das feinere Modell verhindert drei Fehler:

1. Ein Fall mit normaler Technik, aber hoher Regelbindung wird nicht zu niedrig bewertet.
2. Ein Fall mit hoher Betriebswirkung, aber moderater Technik, wird nicht als Routinefall behandelt.
3. Ein Fall mit unklarer Verantwortung bekommt automatisch eine sichtbare Berechtigungsfrage.

---

## 10. Kurzfazit

v0.4 fuehrt keinen neuen Visionstext ein, sondern eine bessere Steuerlogik. Gerade fuer Backup, Provisioning, Kubernetes, Netzwerk und Storage sollte diese Dreiteilung helfen, die virtuelle Bewertung vom diffusen `teilweise` in Richtung `funktioniert mit klarer Grenze` zu schieben.
