# GCA Verarbeitungskreis v0.2

## Zweck

Dieses Dokument schliesst den bisher nur angedeuteten inneren Verarbeitungskreis von GCA.

Es beschreibt den Weg:

```text
Eingabe
-> Bestandsabgleich
-> Delta oder Widerspruch
-> Verdichtung
-> Wissensknoten oder Knoten-Update
-> Speicherung
-> spaetere Rueckholung
```

Damit wird aus der bisherigen Architektur nicht nur eine Sammlung guter Bausteine, sondern ein geschlossener Verarbeitungsweg.

---

## 1. Leitregel

> GCA ist erst dann wirklich arbeitsfaehig, wenn neue Eingaben nicht nur beantwortet, sondern gegen den bestehenden Wissensraum geprueft, als Knoten verdichtet, gespeichert und spaeter gezielt wiederverwendet werden.

---

## 2. Der geschlossene Kreis

### 2.1 Eingang

Moegliche Eingaben:

- neue Beobachtung
- neues Dokument
- neue Messwerte
- neue Nutzerinformation
- Sicherheitsereignis
- alter Fall, der erneut relevant wird

Ziel:

- den Eingang nicht direkt als Antwort behandeln
- sondern als neues Material fuer den Wissensraum

### 2.2 Bestandsabgleich

Der Eingang wird gegen vorhandenes Wissen geprueft:

- gibt es bereits aehnliche Wissensknoten?
- gibt es einen passenden Loesungsknoten?
- gibt es bereits bekannte `DEAD_ENDS`?
- gibt es bestehende Fallkarten oder Protokolle?

Ausgang:

- `kein Treffer`
- `teilweiser Treffer`
- `starker Treffer`
- `Widerspruch zum Bestand`

### 2.3 Delta- und Widerspruchspruefung

Hier wird entschieden:

- bestaetigt die neue Eingabe den Bestand?
- erweitert sie ihn?
- widerspricht sie einem vorhandenen Knoten?
- macht sie einen alten Knoten veraltet?

Wichtige Regel:

> Ein Widerspruch darf nicht still in Text untergehen. Er muss als eigener Verarbeitungszustand sichtbar werden.

### 2.4 Verdichtung

Die Eingabe wird verdichtet in:

- tragfaehige Aussage
- gepruefte Hypothese
- verworfenen Weg
- Knoten-Update
- neuen Wissensknoten

Ergebnis:

- nicht bloesser Rohtext
- sondern strukturierter Wissenszustand

### 2.5 Knotenbildung oder Knotenaktualisierung

Jetzt wird entschieden:

- neuer Wissensknoten
- bestehender Wissensknoten wird erweitert
- bestehender Wissensknoten wird korrigiert
- bestehender Wissensknoten wird ersetzt
- kein Knoten, sondern nur `DEAD_END` oder Zwischenzustand

### 2.6 Speicherung

Jeder relevante Knoten muss speicherbar sein mit:

- Kennung
- Zeitbezug
- Evidenzlage
- Status
- Verweis auf Vorzustand oder Folgezustand

Neue Regel:

> Speicherung ist nicht nur Ablage, sondern Zustandssicherung fuer spaetere Rueckholung und Korrektur.

### 2.7 Rueckholung und Wiederverwendung

Spaeter muss ein Domaenensystem oder der Chat gezielt fragen koennen:

- was wissen wir bereits zu diesem Fall?
- welcher Knoten ist aktuell?
- welche alten Wege wurden verworfen?
- welche Checklisten entstanden daraus?
- welche Widersprueche sind offen?

Erst damit schliesst sich der Kreis.

---

## 3. Verarbeitungszustaende

| Zustand | Bedeutung |
|---|---|
| `roh` | Eingang noch unverdichtet |
| `abgeglichen` | Bestand wurde geprueft |
| `erweitert` | Eingang erweitert vorhandenes Wissen |
| `widerspruechlich` | Eingang kollidiert mit bestehendem Knoten |
| `verdichtet` | strukturierte Aussage ist entstanden |
| `gespeichert` | Knoten wurde versioniert abgelegt |
| `wiederverwendbar` | Knoten ist spaeter gezielt abrufbar |

---

## 4. Der eigentliche Kernunterschied

Ohne diesen Kreis passiert nur:

```text
Eingabe
-> Antwort
```

Mit GCA soll passieren:

```text
Eingabe
-> Abgleich
-> Verdichtung
-> Knoten
-> Speicherung
-> Rueckholung
-> spaetere bessere Verarbeitung
```

Das ist der eigentliche Architekturgewinn.

---

## 5. Verbindung zu Loesungsknoten

Ein Loesungsknoten ist nur ein Spezialfall des Kreises.

Er entsteht dann, wenn:

- genug Evidenz vorliegt
- ein tragfaehiger Weg entstanden ist
- Regel- und Betriebslage geklaert sind
- Umsetzung oder Folgeartefakte ableitbar sind

Nicht jede Eingabe fuehrt also zu einem Loesungsknoten.

---

## 6. Verbindung zu RAG und Dokumentenwissen

Der Kreis ist auch fuer spaetere RAG- oder Vektor-Nutzung wichtig:

- Dokumente liefern Rohmaterial
- der Chat liefert Kontext und Rueckfragen
- GCA verdichtet daraus Knoten
- spaeter wird nicht nur das Rohdokument, sondern auch der Knoten wiederholt

Gerade fuer Systeme wie ARGUS ist das wichtig:

- neue Dokumente kommen rein
- bestehende Wissenslage wird abgeglichen
- neue oder aktualisierte Wissensknoten entstehen

---

## 7. Was noch nicht Teil dieses Dokuments ist

Noch nicht voll festgelegt sind:

- konkrete Speicherstruktur
- Versionsschema
- Prioritaetslogik bei mehreren konkurrierenden Knoten
- Anonymisierung fuer systemuebergreifende Einbaubarkeit

Dieses Dokument schliesst also den Kreis logisch, aber noch nicht technisch.

---

## 8. Meine Einordnung

Damit ist der wichtigste innere Schritt getan:

- der Kreis ist jetzt endlich als Arbeitslogik geschlossen beschrieben
- die naechste Entwicklungsarbeit kann darauf aufsetzen

Der sinnvollste naechste Schritt danach ist:

> den allgemeinen Wissensknoten formal vor den Loesungsknoten setzen
