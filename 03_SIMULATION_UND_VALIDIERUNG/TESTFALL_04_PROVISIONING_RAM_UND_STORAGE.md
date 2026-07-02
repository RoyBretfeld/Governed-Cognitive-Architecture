# Testfall 04 - Provisioning / RAM-Erweiterung und Festplattenplatz

## Ausgangslage

Mehrere produktive VMs zeigen gleichzeitig zwei Engpaesse:

```text
- RAM-Auslastung dauerhaft hoch
- Datenvolume fast voll
- Nutzer melden Verlangsamung
- naechstes Wartungsfenster ist knapp
```

Beispiel:

```text
VM-01: RAM dauerhaft 88 bis 93 Prozent
VM-01: Datenvolume C: nur noch 8 Prozent frei
Host: freie RAM-Reserve unklar
Storage-Backend: Thin Provisioning aktiv
```

## Bekannte Loesung wird ausgeblendet

Das System kennt weder die spaetere reale Massnahme noch die Priorisierung zwischen RAM, Cleanup, Volume-Erweiterung oder Migration.

## Erwartete Denkwege

```text
- liegt ein echtes RAM-Problem oder ein Applikationsleck vor?
- ist der knappe Speicherplatz Ursache, Folge oder Parallelproblem?
- kann zunaechst bereinigt werden statt sofort zu erweitern?
- hat der Host physische RAM-Reserve?
- ist auf dem Datastore oder Backend genug Platz fuer Volume-Wachstum?
- kollidiert die Erweiterung mit Thin-Provisioning-Risiken?
- ist eine Verlagerung auf einen anderen Host oder Storage-Pool sinnvoll?
- muss wegen Betriebsrisiko eskaliert werden?
```

## Erwarteter Loesungsknoten

RAM-Erweiterung und Speichererweiterung duerfen nicht isoliert empfohlen werden. Das Framework soll zuerst die Machbarkeit und Wechselwirkung beider Engpaesse pruefen und erst danach eine abgestufte Handlung ableiten.

Moegliche tragfaehige Richtung:

```text
1. Evidenz sammeln
2. Cleanup- und Leckpruefung
3. Host- und Storage-Machbarkeit pruefen
4. nur freigegebene Erweiterung im Wartungsfenster
5. Ergebnis und Vorher-Nachher-Werte protokollieren
```

## Erwartete Checkliste

```text
[ ] Zeitraum und Muster der RAM-Last geprueft
[ ] Volume-Wachstum und Top-Verbraucher geprueft
[ ] Applikationsleck oder Fehlkonfiguration geprueft
[ ] Host-RAM, freie Slots und Maximalgrenzen geprueft
[ ] Datastore-, NAS- oder SAN-Reserve geprueft
[ ] Thin-Provisioning-Risiko bewertet
[ ] Cleanup oder Archivierung als Alternative geprueft
[ ] Wartungsfenster und Rollback definiert
[ ] menschliche Freigabe eingeholt
[ ] Bestaetigung und Protokoll abgelegt
```
