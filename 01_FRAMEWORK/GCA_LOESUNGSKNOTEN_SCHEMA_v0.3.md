# GCA Loesungsknoten Schema v0.3

## Zweck

Dieses Schema definiert den formalen Aufbau eines Loesungsknotens, sodass Diagnose, Evidence, Policy, Checkliste, Witness und Protokoll spaeter einheitlich gespeichert und wiederverwendet werden koennen.

---

## 1. Leitregel

> Ein Loesungsknoten ist keine Antwort, sondern ein strukturierter, pruefbarer und spaeter wiederverwendbarer Entscheidungsgegenstand.

---

## 2. Pflichtfelder

| Feld | Zweck |
|---|---|
| `id` | eindeutige Kennung |
| `titel` | kurzer, klarer Name des Falls |
| `problemtyp` | z. B. luftstrom, ram, backup, cluster, netzwerk, storage |
| `ausgangslage` | kompakte Beschreibung des Ausgangszustands |
| `symptome` | beobachtete Effekte oder Messhinweise |
| `annahmen` | vorlaeufige Interpretationen |
| `gepruefte_wege` | moegliche Loesungswege |
| `verworfene_wege` | bewusst abgelehnte Wege mit Grund |
| `tragfaehige_loesung` | priorisierte Loesungsrichtung |
| `evidence` | belastbare Nachweise |
| `offene_luecken` | fehlende Daten oder Unsicherheiten |
| `risiko` | Betriebs-, Daten- oder Sicherheitsrisiko |
| `policy_klasse` | P0 bis P3 |
| `approval_stufe` | A0 bis A3 |
| `witness_stufe` | W0 bis W3 |
| `checklisten_typen` | welche Checklisten entstehen sollen |
| `rollback` | Rueckfallstrategie oder Abbruchpunkt |
| `protokollpflicht` | ja oder erweitert |
| `status` | vorgeschlagen, freigegeben, umgesetzt, verworfen, eskaliert |
| `praeventionshinweis` | was spaeter als Regel oder Wartung bleibt |

---

## 3. Feldlogik

### 3.1 Symptome

Symptome bleiben beobachtbar und sollten keine versteckte Ursache enthalten.

Beispiel:

```text
gut: obere Server waermer als untere
schlecht: Rack-Luftstrom ist kaputt
```

### 3.2 Gepruefte und verworfene Wege

Diese Felder bilden die Mehrwege-Logik und das negative Erfahrungswissen ab.

### 3.3 Evidence

Evidence soll nach Moeglichkeit in Typen gegliedert sein:

- Messwerte
- Logs
- Topologie oder Konfiguration
- Zeitfenster
- Vorher-Nachher-Vergleich
- externer Nachweis

### 3.4 Offene Luecken

Offene Luecken bleiben explizit bestehen. Sie duerfen nicht im freien Fliesstext untergehen.

### 3.5 Checklisten-Typen

Ein Loesungsknoten erzeugt nicht automatisch nur eine Checkliste. Er kann mehrere Folgeartefakte erzeugen:

- Diagnose-Checkliste
- Umsetzungs-Checkliste
- Freigabe-Checkliste
- Witness-Checkliste
- Protokoll-Checkliste
- Praeventions-Checkliste

---

## 4. Minimales Pseudo-Schema

```text
id: GCA-LK-0001
titel: Rack-Hitzestau durch Luftstromblockade
problemtyp: luftstrom
ausgangslage: Mehrere Server in einem Rack zeigen oben hoehere Temperaturen.
symptome:
  - oben waermer als unten
  - Temperaturanstieg unter Last
annahmen:
  - Luftstromproblem wahrscheinlicher als Einzelluefterdefekt
gepruefte_wege:
  - Luefterdefekt pruefen
  - Raumtemperatur pruefen
  - Kabel oder Hindernisse im Luftstrom pruefen
verworfene_wege:
  - Hardwaretausch sofort
tragfaehige_loesung:
  - Luftstrom pruefen und Hindernisse entfernen
evidence:
  - Temperaturreihe vorher
  - Sichtpruefung Rack
offene_luecken:
  - keine Foto-Dokumentation vorhanden
risiko:
  - mittel
policy_klasse: P2
approval_stufe: A2
witness_stufe: W2
checklisten_typen:
  - diagnose
  - umsetzung
  - protokoll
rollback:
  - keine Veraenderung an Verkabelung ohne Rueckdokumentation
protokollpflicht: ja
status: vorgeschlagen
praeventionshinweis:
  - Luftstrompruefung in Wartungsplan aufnehmen
```

---

## 5. Ableitungsregeln

Aus dem Schema folgen spaeter automatische oder halbautomatische Artefakte:

- `policy_klasse` bestimmt Approval und Witness
- `problemtyp` bestimmt die Grundbausteine der Checkliste
- `risiko` bestimmt Eskalationstiefe
- `offene_luecken` erzeugt Datennachforderungen
- `praeventionshinweis` erzeugt spaetere Wartungs- oder Regelknoten

---

## 6. Verbindung zu DEAD_ENDS

Wenn kein tragfaehiger Weg entsteht, soll aus demselben Feldmodell ein `DEAD_END` ableitbar bleiben:

- gleiche Ausgangslage
- gleiche Symptome
- gleiche gepruefte Wege
- aber Status `verworfen` oder `eskaliert`
- plus Begruendung, warum keine Freigabe oder keine Loesung moeglich war

Das ist wichtig, damit negatives Erfahrungswissen dieselbe strukturelle Qualitaet bekommt wie erfolgreiche Loesungen.

---

## 7. Verbindung zu Checklisten

Ein Loesungsknoten gilt erst als praxisnah, wenn aus ihm mindestens eine explizite Checkliste ableitbar ist.

Regel:

> Kein P2- oder P3-Loesungsknoten ohne Umsetzungs-, Witness- und Protokoll-Checkliste.

---

## 8. Nutzen

Das Schema ist die Bruecke zwischen Architekturtext und spaeterem Systemverhalten:

- es macht Entscheidungen vergleichbar
- es macht Simulationen reproduzierbar
- es haelt Wissen, Freigabe und Umsetzung zusammen
- es verhindert, dass Checklisten spaeter frei improvisiert werden
