# Testfall 01 — Server-Hitzestau / Rack-Luftstrom

## Ausgangslage

Mehrere Server zeigen unterschiedliche Temperaturen.

Muster:

```text
unten: niedriger
mitte: höher
oben: am höchsten
```

## Bekannte Lösung wird ausgeblendet

Das System bekommt nur Messwerte und Beobachtung, nicht die vermutete Ursache.

## Erwartete Denkwege

```text
- einzelner Lüfter defekt?
- Raumtemperatur zu hoch?
- Luftstrom im Rack gestört?
- Kabel im Luftstrom?
- Staub / Filter?
- Warmluft wird wieder angesaugt?
```

## Erwarteter Lösungsknoten

Das Muster spricht eher für ein Luftstromproblem im Rack als für einen einzelnen Hardwaredefekt.

Wahrscheinliche Ursache:

```text
Kabel oder Hindernisse im Luftstrom erzeugen Wärmerückstau.
```

## Erwartete Checkliste

```text
[ ] Rack öffnen
[ ] Luftstrom prüfen
[ ] Kabelwege prüfen
[ ] Lüfter prüfen
[ ] Staub / Filter prüfen
[ ] Kabel aus Luftweg nehmen
[ ] Temperaturen vorher/nachher messen
[ ] Ergebnis protokollieren
```
