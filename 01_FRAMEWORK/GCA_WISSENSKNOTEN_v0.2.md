# GCA Wissensknoten v0.2

## Zweck

Dieses Dokument definiert den allgemeinen `Wissensknoten` als Oberobjekt vor allen spezialisierten Knotentypen.

Bisher ist der `Loesungsknoten` am besten beschrieben. Das reicht aber nicht, weil nicht jede Eingabe sofort eine Loesung ist.

---

## 1. Leitregel

> Jeder Loesungsknoten ist ein Wissensknoten, aber nicht jeder Wissensknoten ist ein Loesungsknoten.

---

## 2. Rolle des Wissensknotens

Der Wissensknoten ist das allgemeine Behaeltnis fuer verdichtete Erkenntnis.

Er dient dazu:

- neue Erkenntnis speicherbar zu machen
- Hypothesen, Sackgassen und Loesungen strukturell zusammenzufassen
- spaetere Wiederverwendung zu erlauben
- Aktualisierung statt bloesser Neuschreibung zu ermoeglichen

---

## 3. Knotentypen

Der Wissensknoten ist der Oberbegriff fuer mindestens diese Typen:

| Typ | Rolle |
|---|---|
| `beobachtung` | verdichtete Eingangsfeststellung |
| `hypothese` | gepruefter, aber noch nicht finaler Denkweg |
| `dead_end` | verworfener oder blockierter Weg |
| `loesung` | tragfaehiger Weg mit Nachweis und Folgeartefakten |
| `protokoll` | dokumentierte reale Durchfuehrung |
| `praevention` | abgeleitete Regel, Wartung oder Schutzmassnahme |

---

## 4. Pflichtfelder eines allgemeinen Wissensknotens

| Feld | Zweck |
|---|---|
| `id` | eindeutige Kennung |
| `typ` | Knotentyp |
| `titel` | kurzer Titel |
| `quelle` | woher stammt die Erkenntnis |
| `ausgangslage` | worauf bezieht sich der Knoten |
| `inhalt` | verdichtete Kernaussage |
| `evidenz` | Nachweislage |
| `offene_luecken` | was noch fehlt oder unklar ist |
| `bezugsknoten` | welche anderen Knoten werden beruehrt |
| `status` | neu, bestaetigt, erweitert, korrigiert, verworfen, veraltet |
| `zeitstand` | wann dieser Zustand gilt |

---

## 5. Spezialisierung zum Loesungsknoten

Ein Wissensknoten wird zum `Loesungsknoten`, wenn zusaetzlich vorliegt:

- tragfaehige Loesungsrichtung
- gepruefte und verworfene Wege
- Risiko- und Klassenlage
- Checklistenfolge
- Rollback oder Grenze
- Praeventionshinweis

Das bedeutet:

Der allgemeine Wissensknoten steht logisch vor dem Loesungsknoten.

---

## 6. Spezialisierung zu HYPOTHESIS und DEAD_END

### HYPOTHESIS

Ein Hypothesen-Knoten entsteht, wenn:

- eine plausible Richtung gesehen wird
- aber noch nicht genug Evidenz fuer eine tragfaehige Loesung vorliegt

### DEAD_END

Ein Dead-End-Knoten entsteht, wenn:

- ein Weg geprueft und verworfen wurde
- oder wegen Regel-, Risiko- oder Datenlage gesperrt bleibt

Wichtige Regel:

> `DEAD_ENDS` sind keine Textreste, sondern Wissensknoten mit eigenem Wert.

---

## 7. Aktualisierung bestehender Wissensknoten

Ein neuer Eingang soll nicht automatisch immer einen neuen Knoten erzeugen.

Stattdessen gibt es vier moegliche Wirkungen:

| Wirkung | Bedeutung |
|---|---|
| `bestaetigt` | bestaetigt einen vorhandenen Knoten |
| `erweitert` | fuegt neue Erkenntnis hinzu |
| `korrigiert` | aendert einen Teil des bisherigen Knotens |
| `ersetzt` | macht einen alten Zustand fachlich ueberholt |

Das ist die Grundlage fuer spaetere Knotenpflege.

---

## 8. Warum das jetzt wichtig ist

Ohne allgemeinen Wissensknoten bleibt alles zu schnell auf `Loesung` fokussiert.

Dann fehlen:

- saubere Zwischenzustaende
- geordnete Hypothesen
- negative Erkenntnisse
- spaetere Korrekturfuehrung

Mit dem Wissensknoten wird der Knowledge Layer belastbarer.

---

## 9. Verbindung zum Verarbeitungskreis

Der Verarbeitungskreis erzeugt nicht sofort Loesungsknoten, sondern zunaechst Wissensknoten.

Das saubere Modell ist:

```text
Eingabe
-> Abgleich
-> Verdichtung
-> Wissensknoten
-> je nach Reife:
   -> Hypothese
   -> Dead-End
   -> Loesungsknoten
   -> Protokoll
   -> Praeventionsknoten
```

---

## 10. Meine Einordnung

Mit diesem Schritt ist der Knowledge Layer deutlich stabiler als vorher.

Vorher war `Loesungsknoten` das klarste Objekt, aber zu eng.
Jetzt gibt es den allgemeinen Behälter, in den spaetere Domaenen wie ARGUS oder AEGIS ueberhaupt erst sauber einspeisen koennen.
