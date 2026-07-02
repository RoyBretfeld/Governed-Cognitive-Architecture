# GCA Checklisten Generator v0.3

## Zweck

Dieses Dokument beschreibt, welche Checklisten sich aus Loesungsknoten systematisch generieren lassen und welche Bausteine pro Falltyp nicht vergessen werden duerfen.

Das ist wichtig, damit Checklisten spaeter nicht zufaellig oder nur aus Erinnerung entstehen.

---

## 1. Grundregel

> Checklisten sind keine freien Notizen. Sie sind abgeleitete Folgeartefakte aus Problemtyp, Policy-Klasse, Risiko, Evidence und Witness.

---

## 2. Checklisten-Typen

| Typ | Zweck |
|---|---|
| Diagnose-Checkliste | notwendige Datenerhebung und Abgrenzung |
| Umsetzungs-Checkliste | konkrete produktive oder physische Handlung |
| Freigabe-Checkliste | Approval, Rollen, Zeitfenster, Rollback |
| Witness-Checkliste | Nachweise der Durchfuehrung oder Stabilisierung |
| Protokoll-Checkliste | dokumentierte Ist-Durchfuehrung |
| Praeventions-Checkliste | Wiederholungsschutz oder Wartungsueberfuehrung |

---

## 3. Generatorlogik

```text
Loesungsknoten lesen
-> Problemtyp erkennen
-> Policy-Klasse lesen
-> Risiko lesen
-> offene Luecken lesen
-> daraus Pflicht-Checklisten bestimmen
```

Pflichtregeln:

- P0 erzeugt meist nur Diagnose-Checkliste oder gar keine
- P1 erzeugt Diagnose- plus Vorschlags- oder Freigabevorlage
- P2 erzeugt Diagnose-, Umsetzungs-, Freigabe-, Witness- und Protokoll-Checkliste
- P3 erzeugt dieselben wie P2 plus erweiterte Rollback- und Praeventionspunkte

---

## 4. Pflichtbausteine je Checklisten-Typ

### Diagnose-Checkliste

- Symptom bestaetigt
- Mindest-Evidence gesammelt
- Alternativen geprueft
- offene Luecken sichtbar

### Umsetzungs-Checkliste

- vorbereitende Schritte
- Aenderungsschritt selbst
- Sicherheits- oder Betriebsgrenzen
- Rollback-Bereitschaft

### Freigabe-Checkliste

- Policy-Klasse bestaetigt
- Human Approval eingeholt
- Rollen benannt
- Zeitfenster festgelegt
- Rollback bestaetigt

### Witness-Checkliste

- Wer oder was bestaetigt?
- welcher Nachweis liegt vor?
- wann wird gegengeprueft?
- wann gilt der Fall als stabilisiert?

### Protokoll-Checkliste

- was wurde real getan?
- wann und durch wen?
- welches Ergebnis?
- welche Abweichungen zur Planung?

### Praeventions-Checkliste

- wiederkehrende Ursache erkannt?
- Wartung oder Policy noetig?
- Monitoring-Schwellen anpassen?
- neues Regelwissen uebernehmen?

---

## 5. Falltypische Generatorbausteine

### 5.1 Luftstrom oder physische Infrastruktur

Diagnose:

- Temperaturverteilung pruefen
- Raum- und Rack-Kontext pruefen
- Luefter, Staub, Kabel, Rueckansaugung pruefen

Umsetzung:

- Eingriff am Rack planen
- Kabel oder Hindernisse korrigieren
- Vorher-Nachher-Messung sichern

Praevention:

- Luftstrompruefung in Wartungsplan

### 5.2 RAM oder klassisches Provisioning

Diagnose:

- Lastspitze gegen Dauerproblem trennen
- Top-Consumer oder Leck pruefen
- Host-Grenzen und freie Slots pruefen

Umsetzung:

- nur freigegebene Erweiterung
- Wartungsfenster beachten
- Rollback oder Rueckbau definieren

Praevention:

- Kapazitaetswarnschwelle
- Trendbeobachtung

### 5.3 Storage, NAS oder NetApp

Diagnose:

- freier Platz auf mehreren Ebenen pruefen
- Snapshot-Anteil pruefen
- Wachstumsmuster pruefen
- Restore- und Compliance-Kontext pruefen

Umsetzung:

- Expansion, Tiering, Archivierung oder Retention-Anpassung vergleichen
- Schnellloeschung nur nach harter Freigabe

Praevention:

- Growth-Monitoring
- Snapshot-Policy pruefen

### 5.4 Backup oder Betriebsfenster

Diagnose:

- Nutzerlast je Zeitraum
- Datenmenge und Zielsystem
- Storage- und Netzwerklast
- Restore-Faehigkeit

Umsetzung:

- neues Fenster
- Drosselung oder Inkrementalitaet
- Freigabe fuer Produktivumstellung

Praevention:

- Backupfenster regelmaessig validieren

### 5.5 Kubernetes oder Cluster

Diagnose:

- Events und Scheduler-Meldungen
- Requests, Limits, Taints, Affinity
- PVC, PV, StorageClass
- letzte Rollout-Aenderung

Umsetzung:

- Rollback oder Resize
- Scheduling-Korrektur
- Cluster-Aenderung nur freigegeben

Praevention:

- Default-Policies oder Guardrails anpassen

### 5.6 Netzwerk, Switch oder VLAN

Diagnose:

- betroffene VLANs und Dienste
- Interface-Fehlerzaehler
- Speed, Duplex, Module
- Uplink-Auslastung
- Trunk- und STP-Lage

Umsetzung:

- Gegenprobe oder Wartungsumschaltung
- produktive Netzwerkaenderung nur nach Freigabe

Praevention:

- Link-Health-Monitoring
- Konfigurationsbaseline pflegen

---

## 6. Matrix aus Problemtyp und Policy

| Problemtyp | P0/P1 erzeugt | P2 erzeugt zusaetzlich | P3 erzeugt zusaetzlich |
|---|---|---|---|
| luftstrom | Diagnose | Umsetzung, Witness, Protokoll | erweiterte Freigabe |
| ram | Diagnose | Umsetzung, Freigabe, Protokoll | erweiterter Rollback |
| backup | Diagnose | Freigabe, Witness, Protokoll | Business- und Restore-Absicherung |
| provisioning_kombi | Diagnose | Umsetzung, Freigabe, Witness | erweiterte Risiko- und Rollback-Schicht |
| kubernetes | Diagnose | Rollback-/Resize-Checkliste, Protokoll | Clusterkritische Freigabe |
| netzwerk | Diagnose | Gegenprobe, Freigabe, Witness | starke Freigabe und Gegenmessung |
| storage | Diagnose | Freigabe, Witness, Protokoll | Compliance- und Restore-Schutz |

---

## 7. Direkte Ableitung fuer die sieben Testfaelle

| Testfall | Mindest-Checklisten |
|---|---|
| 01 Hitzestau | Diagnose, Umsetzung, Protokoll, Praevention |
| 02 RAM | Diagnose, Freigabe, Umsetzung, Protokoll |
| 03 Backupfenster | Diagnose, Freigabe, Witness, Protokoll, Praevention |
| 04 Provisioning RAM und Storage | Diagnose, Freigabe, Umsetzung, Witness, Protokoll |
| 05 Kubernetes Pending und PVC | Diagnose, Freigabe, Rollback, Witness, Protokoll |
| 06 Switch-Uplink und VLAN | Diagnose, Freigabe, Witness, Protokoll, Praevention |
| 07 NAS oder NetApp | Diagnose, Freigabe, Witness, Protokoll, Praevention |

---

## 8. Was wir spaeter nicht vergessen duerfen

Diese Generatorlogik sollte spaeter nicht nur als Text existieren, sondern als feste Ableitungsregel:

- aus `problemtyp`
- aus `policy_klasse`
- aus `witness_stufe`
- aus `risiko`
- aus `offene_luecken`

Nur dann wird aus "Loesung mit Checkliste" wirklich eine belastbare Systemfunktion.
