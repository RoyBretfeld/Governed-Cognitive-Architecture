# Testfall 06 - Netzwerk / Switch-Uplink und VLAN-Konflikt

## Ausgangslage

Mehrere Systeme in unterschiedlichen Segmenten zeigen sporadische Verbindungsprobleme.

Beobachtung:

```text
- zeitweise hohe Latenz
- einzelne Systeme verlieren kurz die Verbindung
- nicht alle VLANs sind gleich stark betroffen
- Monitoring zeigt auf einem Uplink Fehler oder hohe Auslastung
```

Beispiel:

```text
Core-Switch Uplink Port 1/48
CRC-Fehler ansteigend
VLAN 20 und VLAN 30 betroffen
VoIP stoert, Fileservices langsam
```

## Bekannte Loesung wird ausgeblendet

Das System kennt nicht, ob am Ende ein physischer Portfehler, ein Duplex-Problem, Uplink-Saettigung, Trunk-Mismatch oder eine Fehlkonfiguration die Hauptursache ist.

## Erwartete Denkwege

```text
- physischer Port oder Modul fehlerhaft?
- CRC-Fehler, Duplex oder Speed-Mismatch?
- ist der Uplink ueberlastet?
- Trunk oder Allowed-VLAN-Liste fehlerhaft?
- Spanning-Tree oder Loop-Effekt moeglich?
- betrifft es nur Clients, nur Storage oder mehrere Dienste?
- waere ein Port-Shutdown oder Uplink-Wechsel produktiv riskant?
```

## Erwarteter Loesungsknoten

Das Framework soll physische und logische Netzwerkursachen trennen und ohne vorschnellen Eingriff eine priorisierte Diagnose und Aenderungsreihenfolge erzeugen.

Moegliche tragfaehige Richtung:

```text
1. Fehlerzaehler, Uplink-Auslastung und VLAN-Betroffenheit bewerten
2. physische Ursachen gegen Trunk- oder Regelfehler abgrenzen
3. risikoarme Gegenprobe oder Wartungswechsel planen
4. produktive Netzwerkaenderungen nur mit Freigabe durchfuehren
```

## Erwartete Checkliste

```text
[ ] Interface-Fehlerzaehler und Verlauf geprueft
[ ] Speed-, Duplex- und Modulstatus geprueft
[ ] Uplink-Auslastung und Burst-Muster geprueft
[ ] betroffene VLANs und Dienste eingegrenzt
[ ] Trunk- und Allowed-VLAN-Konfiguration geprueft
[ ] STP- oder Loop-Hinweise geprueft
[ ] risikoarme Gegenprobe oder Wartungsplan erstellt
[ ] menschliche Freigabe fuer produktive Umschaltung eingeholt
[ ] Bestaetigung durch Monitoring und Gegenmessung abgelegt
[ ] Protokoll und Praeventionsmassnahme erstellt
```
