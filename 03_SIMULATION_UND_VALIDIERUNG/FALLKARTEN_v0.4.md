# GCA Fallkarten v0.4

## Zweck

Dieses Dokument uebersetzt die sieben aktuellen Testfaelle in ein einheitliches Fallkartenformat.

Jede Fallkarte verdichtet:

- Problemtyp
- Regelklasse
- Betriebsklasse
- Berechtigungsstufe
- Bestaetigungsstufe
- notwendige Evidenz
- Mindest-Checklisten
- Rollback oder Eskalationspunkt

Damit werden die Testfaelle nicht nur bewertet, sondern spaeter operativ wiederverwendbar.

---

## Fallkarte 01 - Hitzestau / Rack-Luftstrom

| Feld | Inhalt |
|---|---|
| Kennung | FK-01 |
| Problemtyp | luftstrom |
| Regelklasse | R1 |
| Betriebsklasse | B2 |
| Berechtigungsstufe | G2 |
| Bestaetigungsstufe | N2 |
| Kurzproblem | Temperaturanstieg im Rack mit Muster oben waermer als unten |
| Tragfaehige Richtung | Luftstromproblem vor Einzelschaden priorisieren |
| Mindest-Evidenz | Temperaturreihe, Sichtpruefung, Rack-Kontext, Luefterstatus |
| Mindest-Checklisten | Diagnose, Umsetzung, Protokoll, Praevention |
| Rollback oder Grenze | keine physische Veraenderung ohne Rueckdokumentation |
| Status im Modell | funktioniert |

---

## Fallkarte 02 - RAM / Kapazitaetsgrenze

| Feld | Inhalt |
|---|---|
| Kennung | FK-02 |
| Problemtyp | ram |
| Regelklasse | R1 |
| Betriebsklasse | B2 |
| Berechtigungsstufe | G2 |
| Bestaetigungsstufe | N2 |
| Kurzproblem | dauerhafte hohe RAM-Last bei produktiven VMs |
| Tragfaehige Richtung | Machbarkeit vor Erweiterung, Alternativen gegenpruefen |
| Mindest-Evidenz | Lastverlauf, Top-Consumer, Host-Grenzen, freie Slots, Wartungsfenster |
| Mindest-Checklisten | Diagnose, Freigabe, Umsetzung, Protokoll |
| Rollback oder Grenze | keine RAM-Erweiterung ohne Host-Beweis und Wartungsfenster |
| Status im Modell | funktioniert |

---

## Fallkarte 03 - Backupfenster / Betriebsstoerung

| Feld | Inhalt |
|---|---|
| Kennung | FK-03 |
| Problemtyp | backup |
| Regelklasse | R2 |
| Betriebsklasse | B2 bis B3 |
| Berechtigungsstufe | G2 bis G3 |
| Bestaetigungsstufe | N2 bis N3 |
| Kurzproblem | Backups stoeren laufenden Betrieb und Lastfenster |
| Tragfaehige Richtung | Lastbild, Restore-Schutz und Betriebsfenster gemeinsam bewerten |
| Mindest-Evidenz | Lastwerte je Zeitraum, Datenmenge, Zielsystem, Restore-Kontext |
| Mindest-Checklisten | Diagnose, Freigabe, Bestaetigung, Protokoll, Praevention |
| Rollback oder Grenze | keine produktive Umplanung ohne Restore-Betrachtung |
| Status im Modell | funktioniert |

---

## Fallkarte 04 - Provisioning / RAM und Storage

| Feld | Inhalt |
|---|---|
| Kennung | FK-04 |
| Problemtyp | provisioning_kombi |
| Regelklasse | R2 |
| Betriebsklasse | B2 bis B3 |
| Berechtigungsstufe | G2 bis G3 |
| Bestaetigungsstufe | N2 bis N3 |
| Kurzproblem | RAM-Engpass und Speichermangel treten gekoppelt auf |
| Tragfaehige Richtung | gekoppelte Machbarkeit vor isolierter Einzelmassnahme |
| Mindest-Evidenz | RAM-Verlauf, Top-Consumer, Volume-Auslastung, Storage-Reserve, Thin-Provisioning-Lage |
| Mindest-Checklisten | Diagnose, Freigabe, Umsetzung, Bestaetigung, Protokoll |
| Rollback oder Grenze | keine Doppelmassnahme ohne Rollback und Freigabe |
| Status im Modell | funktioniert |

---

## Fallkarte 05 - Kubernetes / Pod Pending und PVC

| Feld | Inhalt |
|---|---|
| Kennung | FK-05 |
| Problemtyp | kubernetes |
| Regelklasse | R2 bis R3 |
| Betriebsklasse | B3 |
| Berechtigungsstufe | G3 |
| Bestaetigungsstufe | N3 |
| Kurzproblem | Pods bleiben Pending, Scheduling und Storage kollidieren |
| Tragfaehige Richtung | Ereignisse, Ressourcen, PVC und Rollout-Kontext getrennt analysieren |
| Mindest-Evidenz | Scheduler-Events, Requests/Limits, Taints, Affinity, PVC/PV/StorageClass, Rollout-Historie |
| Mindest-Checklisten | Diagnose, Freigabe, Rollback, Bestaetigung, Protokoll |
| Rollback oder Grenze | keine Cluster-Aenderung ohne klare Rueckfalloption |
| Status im Modell | teilweise |

---

## Fallkarte 06 - Netzwerk / Switch-Uplink und VLAN

| Feld | Inhalt |
|---|---|
| Kennung | FK-06 |
| Problemtyp | netzwerk |
| Regelklasse | R2 bis R3 |
| Betriebsklasse | B3 |
| Berechtigungsstufe | G3 |
| Bestaetigungsstufe | N3 |
| Kurzproblem | Netzwerkstoerung mit moeglicher physischer oder logischer Uplink-Ursache |
| Tragfaehige Richtung | Fehlerzaehler, Trunk, Auslastung und betroffene Segmente gemeinsam bewerten |
| Mindest-Evidenz | Interface-Werte, CRC oder Duplex-Lage, Uplink-Last, VLAN-Betroffenheit, STP-Hinweise |
| Mindest-Checklisten | Diagnose, Freigabe, Bestaetigung, Protokoll, Praevention |
| Rollback oder Grenze | keine produktive Umschaltung ohne Gegenmessung und Rueckweg |
| Status im Modell | funktioniert |

---

## Fallkarte 07 - NAS oder NetApp / Snapshot-Wachstum

| Feld | Inhalt |
|---|---|
| Kennung | FK-07 |
| Problemtyp | storage |
| Regelklasse | R3 |
| Betriebsklasse | B3 bis B4 |
| Berechtigungsstufe | G3 bis G4 |
| Bestaetigungsstufe | N3 bis N4 |
| Kurzproblem | zentrale Storage-Kapazitaet wird durch Wachstum und Snapshots kritisch |
| Tragfaehige Richtung | Expansion, Retention, Restore-Sicherheit und Geschaeftsrisiko zusammen betrachten |
| Mindest-Evidenz | Volume- und Aggregate-Werte, Snapshot-Anteil, Wachstumsmuster, Restore- und Compliance-Kontext |
| Mindest-Checklisten | Diagnose, Freigabe, Bestaetigung, Protokoll, Praevention |
| Rollback oder Grenze | keine Schnellloeschung oder Regelanpassung ohne starke Freigabe |
| Status im Modell | teilweise |

---

## Gesamtbild

Die Fallkarten zeigen, dass GCA bei den sieben Faellen inzwischen nicht nur Gedankenbaeume, sondern fast operative Steckbriefe liefern kann.

Aus meiner Sicht sind diese Fallkarten der naechste wichtige Zwischenschritt zwischen:

- Architekturtext
- virtueller Simulation
- spaeterer Systemlogik

Sie machen das Modell deutlich belastbarer.
