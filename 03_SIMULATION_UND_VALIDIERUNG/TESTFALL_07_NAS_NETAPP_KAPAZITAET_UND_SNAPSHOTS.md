# Testfall 07 - NAS oder NetApp / Kapazitaetsgrenze und Snapshot-Wachstum

## Ausgangslage

Ein zentrales NAS- oder NetApp-System meldet sinkende freie Kapazitaet, waehrend Fachbereiche bereits Performance- oder Speicherrisiken melden.

Symptome:

```text
- Volume oder Aggregate laufen gegen die Kapazitaetsgrenze
- Snapshots wachsen ungewoehnlich stark
- neue Schreibvorgaenge werden langsamer oder schlagen fehl
- mehrere Systeme teilen sich dieselbe Storage-Basis
```

Beispiel:

```text
NetApp Volume DATA_PROD nur noch 9 Prozent frei
Snapshot-Reserve nahezu ausgeschoepft
gleichzeitig starkes Datenwachstum im Fileshare
```

## Bekannte Loesung wird ausgeblendet

Das System kennt nicht, ob spaeter aufgeraeumt, expandiert, Snapshot-Retention geaendert, tiered oder auf ein anderes Ziel migriert wurde.

## Erwartete Denkwege

```text
- ist das Wachstum einmalig oder strukturell?
- verursacht Snapshot-Politik den Engpass?
- ist die Reserve auf Volume-, Aggregate- oder Backend-Ebene kritisch?
- ist Expansion technisch moeglich und betrieblich zulaessig?
- wuerde Aufraeumen Compliance oder Restore-Sicherheit gefaehrden?
- ist Tiering, Archivierung oder Migration sinnvoller?
- muss wegen Datenrisiko oder geschaeftskritischer Freigaben eskaliert werden?
```

## Erwarteter Loesungsknoten

Das Framework soll Kapazitaetsproblem, Aufbewahrung, Datensicherheit und Restore-Faehigkeit gemeinsam betrachten und keine vorschnelle Loesch- oder Expansionsentscheidung treffen.

Moegliche tragfaehige Richtung:

```text
1. Wachstum und Snapshot-Anteil belegen
2. technische und regulatorische Grenzen trennen
3. sichere Optionen gegen riskante Schnellmassnahmen abwaegen
4. nur freigegebene Storage-Aenderung empfehlen
```

## Erwartete Checkliste

```text
[ ] Volume-, Aggregate- und Reservewerte geprueft
[ ] Snapshot-Wachstum und Retention geprueft
[ ] Top-Consumer oder Freigaben mit hohem Wachstum geprueft
[ ] Restore- und Compliance-Auswirkungen geprueft
[ ] Expansion, Tiering, Archivierung oder Migration verglichen
[ ] Risiko einer Schnellloeschung bewertet
[ ] Policy-Klasse und Business-Kritikalitaet festgehalten
[ ] Human Approval eingeholt
[ ] Witness durch Monitoring oder Storage-Bericht abgelegt
[ ] Protokoll und Praeventionsplan erstellt
```
