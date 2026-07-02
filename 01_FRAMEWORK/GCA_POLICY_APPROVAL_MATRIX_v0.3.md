# GCA Policy und Approval Matrix v0.3

## Zweck

Dieses Dokument formalisiert, wann GCA nur analysieren darf, wann ein Vorschlag entstehen darf und wann zwingend menschliche Freigabe, Witness und Protokoll notwendig sind.

Die Matrix ist bewusst praktisch gehalten. Sie soll nicht Theorie vermehren, sondern Fehlgrenzen im Betrieb sichtbar machen.

---

## 1. Leitregel

> Je hoeher Betriebswirkung, Sicherheitswirkung oder Unsicherheit, desto hoeher die Policy-Klasse und desto haerter die Freigabepflicht.

---

## 2. Policy-Klassen

| Klasse | Typischer Charakter | Autonom erlaubt | Human Approval | Witness | Protokoll |
|---|---|---|---|---|---|
| P0 | reine Analyse, Dokumentation, Simulation | ja | nein | optional | optional |
| P1 | vorbereitender Vorschlag ohne direkte Produktivwirkung | ja | nein fuer Vorschlag, ja fuer Umsetzung | optional | empfohlen |
| P2 | produktive Aenderung mit begrenztem Betriebsrisiko | nein | ja | ja | ja |
| P3 | sicherheitskritische, geschaeftskritische oder schwer reversible Aenderung | nein | ja, erweitert | ja, stark | ja, erweitert |

---

## 3. Einstufungslogik

Ein Fall wird mindestens um eine Stufe hoeher eingestuft, wenn einer dieser Punkte zutrifft:

- unvollstaendige oder widerspruechliche Evidence
- keine sichere Rollback-Moeglichkeit
- mehrere Systeme oder Mandanten betroffen
- Datenverlust oder Compliance-Risiko moeglich
- Produktivsystem, Core-Netzwerk, zentrales Storage oder Clustersteuerung betroffen
- Sicherheitsregel, Policy oder Schutzgrenze beruehrt

Neue Regel:

> Unklare Einstufung wird nicht nach unten, sondern nach oben aufgeloest.

---

## 4. Approval-Stufen

| Approval-Stufe | Bedeutung | Wann noetig |
|---|---|---|
| A0 | keine Freigabe notwendig | P0 |
| A1 | fachliche Kenntnisnahme oder Plausibilisierung | P1 bei spaeterer Uebergabe |
| A2 | normale produktive Freigabe | P2 |
| A3 | erweiterte Freigabe mit Risiko- und Rollback-Betrachtung | P3 |

---

## 5. Mindestanforderungen je Klasse

### P0

- Problemdefinition
- Eingabedaten dokumentiert
- Hypothesen und offene Luecken dokumentiert

### P1

- Problemdefinition
- Evidence-Grundlage
- Alternativenvergleich
- vorgeschlagene Checkliste
- Hinweis, dass noch keine Umsetzung freigegeben ist

### P2

- vollstaendige Evidence fuer den konkreten Eingriff
- Risikoabschaetzung
- Rollback-Plan
- Human Approval A2
- Witness fuer Durchfuehrung oder Stabilisierung
- Protokollpflicht

### P3

- vollstaendige Evidence plus Business-Kritikalitaet
- Risiko- und Nebenwirkungsanalyse
- Rollback oder Ersatzverfahren
- Human Approval A3
- starker Witness
- erweitertes Protokoll
- Eskalationsweg bei Abbruch oder Unsicherheit

---

## 6. Witness-Stufen

| Witness-Stufe | Bedeutung | Beispiele |
|---|---|---|
| W0 | nicht erforderlich | reine Denkarbeit |
| W1 | einfacher bestaetigender Nachweis | Monitoring-Screenshot, zweiter Log, Kontrollmessung |
| W2 | umsetzungsnaher oder personengebundener Nachweis | signiertes Wartungsprotokoll, zweiter Operator, Restore-Test |
| W3 | starker Nachweis bei kritischen Aenderungen | Vier-Augen-Prinzip, Security-Freigabe, dokumentierter Gegencheck nach Aenderung |

---

## 7. Entscheidungslogik als Ablauf

```text
Problem erkannt
-> Evidence ausreichend?
   -> nein: Eskalation oder Datennachforderung
   -> ja: Policy-Klasse bestimmen
-> P0 oder P1?
   -> Vorschlag und Checkliste erzeugen
-> P2 oder P3?
   -> Human Approval verlangen
   -> Witness-Anforderung setzen
   -> Rollback und Protokollpflicht aktivieren
-> Umsetzung nur nach Freigabe
```

---

## 8. Einordnung der sieben aktuellen Testfaelle

| Testfall | Primäre Klasse | Warum |
|---|---|---|
| 01 Hitzestau / Rack-Luftstrom | P2 | physischer Eingriff am produktiven Rack |
| 02 RAM / Kapazitaetsgrenze | P2 | produktive Ressourcenanpassung |
| 03 Backupfenster / Betriebsstoerung | P2 bis P3 | produktive Backup-Aenderung mit Daten- und Betriebsrisiko |
| 04 Provisioning / RAM und Storage | P2 bis P3 | gekoppelte produktive Ressourcen- und Storage-Aenderung |
| 05 Kubernetes / Pending und PVC | P2 bis P3 | Cluster- oder Storage-Aenderung im Produktivbetrieb |
| 06 Netzwerk / Switch-Uplink und VLAN | P2 bis P3 | Core-Netzwerk kann mehrere Dienste betreffen |
| 07 NAS oder NetApp / Snapshot-Wachstum | P3 | zentrales Storage, Daten- und Restore-Risiko |

---

## 9. Approval-Matrix nach Aktionstyp

| Aktionstyp | Standardklasse | Approval | Witness | Hinweis |
|---|---|---|---|---|
| Analyse, Vergleich, Simulation | P0 | A0 | W0 | kein Produktiveingriff |
| Handlungsvorschlag oder Wartungsplan | P1 | A1 | W0 bis W1 | noch keine Umsetzung |
| VM-RAM erweitern | P2 | A2 | W2 | Host- und Wartungsfenster pruefen |
| produktives Volume erweitern | P2 | A2 | W2 | Storage-Reserve pruefen |
| Backupfenster aendern | P2 bis P3 | A2 oder A3 | W2 | Restore und Lastwirkung pruefen |
| PVC, Cluster oder Scheduling anpassen | P2 bis P3 | A2 oder A3 | W2 | Rollbackfaehigkeit wichtig |
| Uplink umschalten oder VLAN-Produktivpfad aendern | P3 | A3 | W3 | Netzwerkbreite Wirkung |
| Snapshot-Retention oder Storage-Policy aendern | P3 | A3 | W3 | Restore- und Compliance-Risiko |

---

## 10. Operative Konsequenz fuer GCA

Die Matrix bedeutet fuer spaetere GCA-Logik:

- kein Loesungsknoten ohne Policy-Klasse
- keine Checkliste ohne benoetigte Approval-Stufe
- kein Protokoll ohne Witness-Anforderung
- kein "teilweise" bestandener Simulationsfall ohne sichtbare Freigabelogik

---

## 11. Kurzfazit

Diese Matrix macht aus der vagen Idee "Denken autonom, Handeln kontrolliert" einen praktischen Steuermechanismus. Genau das wird gebraucht, damit die heutigen `teilweise`-Faelle spaeter systematisch Richtung `funktioniert` wandern koennen.
