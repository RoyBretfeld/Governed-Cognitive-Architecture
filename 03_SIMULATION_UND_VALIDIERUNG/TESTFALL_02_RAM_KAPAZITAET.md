# Testfall 02 — RAM-Auslastung / VM-Kapazität

## Ausgangslage

Mehrere VMs laufen dauerhaft mit hoher RAM-Auslastung.

Beispiel:

```text
10 VMs: 8 GB RAM
Auslastung dauerhaft > 85 %
```

## Erwartete Denkwege

```text
- kurzfristige Lastspitze oder Dauerproblem?
- einzelne Anwendung verursacht Verbrauch?
- VM-RAM erhöhen?
- Host hat noch Kapazität?
- freie RAM-Slots vorhanden?
- maximale RAM-Grenze erreicht?
- VMs verschieben?
- neuer Server nötig?
```

## Erwarteter Lösungsknoten

Eine RAM-Erhöhung darf erst empfohlen werden, wenn Machbarkeit geprüft ist.

## Erwartete Checkliste

```text
[ ] Zeitraum der RAM-Auslastung geprüft
[ ] betroffene VMs aufgelistet
[ ] Host-RAM geprüft
[ ] freie Slots geprüft
[ ] maximale RAM-Grenze geprüft
[ ] VM-Verschiebung geprüft
[ ] Wartungsfenster definiert
[ ] Freigabe / Unterschrift eingeholt
[ ] Änderung protokolliert
```
