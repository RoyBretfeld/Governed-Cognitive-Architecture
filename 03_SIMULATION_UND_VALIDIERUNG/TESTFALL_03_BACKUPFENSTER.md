# Testfall 03 — Backupfenster / Betriebsbelastung

## Ausgangslage

Backups laufen zu Zeiten, in denen viele Nutzer oder Anwendungen aktiv sind.

Folge:

```text
- Netzwerk wird belastet
- Storage-I/O steigt
- Anwendungen reagieren langsamer
- Wartungsfenster wird unklar
```

## Erwartete Denkwege

```text
- Backupzeit falsch?
- Datenmenge zu groß?
- Netzwerk-Bottleneck?
- Storage-Bottleneck?
- inkrementelles Backup möglich?
- getrenntes Backupziel nötig?
- Restore-Test vorhanden?
```

## Erwarteter Lösungsknoten

Backups müssen in freie Systemzeiten verschoben und nach Lastgrenzen geplant werden.

## Erwartete Checkliste

```text
[ ] Nutzerlast je Zeitraum geprüft
[ ] CPU/RAM/Storage/Netzwerk während Backup geprüft
[ ] Datenmenge geprüft
[ ] Backupziel geprüft
[ ] neues Backupfenster vorgeschlagen
[ ] Restore-Test geplant
[ ] Backup-Protokoll abgelegt
```
