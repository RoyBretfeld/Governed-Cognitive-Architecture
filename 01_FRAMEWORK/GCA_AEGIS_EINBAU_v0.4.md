# GCA AEGIS-Einbau v0.4

## Zweck

Dieses Dokument prueft AEGIS nicht als fernes Zukunftsetikett, sondern als konkretes Einbau-Framework fuer GCA.

AGI bleibt in GCA nur der Ausblick. Der operative Einbaupfad betrifft hier Sicherheit, Begrenzung, Freigabe, Nachweis und kontrollierte Ausfuehrung.

---

## 1. Grundsatz

> GCA beschreibt, wie Probleme verstanden, verdichtet und in Loesungsknoten ueberfuehrt werden. AEGIS beschreibt, wie riskante oder produktive Wirkung begrenzt, geprueft, freigegeben, bestaetigt und notfalls gestoppt wird.

Damit ist AEGIS fuer GCA kein Ersatz, sondern ein Einbaurahmen fuer die Durchsetzungsseite.

---

## 2. Was AEGIS fuer GCA leisten sollte

Aus GCA-Sicht braucht der Einbau vor allem sechs Funktionen:

1. Vorpruefung vor jeder riskanten oder produktiven Aenderung
2. Regel- und Klassenpruefung gegen `Regelklasse`, `Betriebsklasse` und `Berechtigungsstufe`
3. Nachweissicherung fuer Evidenz, Bestaetigung und Protokoll
4. Begrenzung des Handlungsspielraums bei unsicherer Datenlage
5. Notstopp oder Abbruchmoeglichkeit bei Grenzverletzung
6. sichtbare Rueckmeldung an Mensch und Protokollschicht

---

## 3. GCA-zu-AEGIS-Mapping

| GCA-Bedarf | AEGIS-Einbaurolle |
|---|---|
| Loesungsknoten mit Freigabelogik | AEGIS prueft Klassenlage und blockiert unzulaessige Ausfuehrung |
| Fallkarten | AEGIS liest Falltyp, Klassen und Mindest-Evidenz als operative Steuerdaten |
| Checklisten-Ableitung | AEGIS erzwingt die Pflichtschritte vor und nach Produktiveingriffen |
| menschliche Freigabe | AEGIS setzt nur freigegebene Aktionen in den ausfuehrbaren Bereich |
| Bestaetigung | AEGIS sammelt Gegenpruefung, Monitoring oder Bediennachweis |
| Eskalation | AEGIS friert, stoppt oder verweist an hoehere Berechtigung |

---

## 4. Empfohlene AEGIS-Unterfunktionen fuer den Einbau

### 4.1 Ausfuehrungspruefung vor Mutation

Das ist der wichtigste Einbaupunkt.

Bevor aus einem GCA-Loesungsknoten eine reale Handlung wird, muss AEGIS mindestens pruefen:

- ist die Evidenz ausreichend?
- ist die Regelklasse korrekt?
- ist die Betriebsklasse korrekt?
- liegt die benoetigte Berechtigungsstufe vor?
- ist Rollback definiert?
- ist die Bestaetigungspflicht gesetzt?

### 4.2 Begrenzungswaechter

AEGIS sollte produktive oder sicherheitsrelevante Grenzverletzungen aktiv blockieren.

Beispiele:

- keine Cluster-Aenderung ohne G3
- keine zentrale Storage-Aenderung ohne starke Bestaetigung
- keine Netzpfad-Umschaltung ohne Rueckweg und Gegenmessung

### 4.3 Nachweis- und Protokollschicht

AEGIS sollte die Beweiskette sichern:

- Eingabedaten
- Klasseneinstufung
- Freigabeentscheidung
- reale Durchfuehrung
- Stabilisierung oder Abbruch

### 4.4 Notstopp und Abbruchpfad

Wenn eine Regelgrenze verletzt wird oder Evidenz fehlt, braucht GCA keinen kreativen Weiterlauf, sondern einen klaren AEGIS-Abbruchpfad.

---

## 5. Empfohlener technischer Einbau in GCA

Ich wuerde AEGIS nicht als neue diffuse Oberschicht beschreiben, sondern als fuenf klar benannte Einbaumodule:

| Einbaumodul | Rolle |
|---|---|
| AEGIS Vorpruefung | prueft Klassen, Evidenz und Freigabe vor Ausfuehrung |
| AEGIS Regelwaechter | blockiert unzulaessige oder zu hochklassige Schritte |
| AEGIS Nachweissicherung | sammelt Evidenz, Bestaetigung und Protokoll |
| AEGIS Notstopp | friert oder bricht riskante Wege ab |
| AEGIS Rueckmeldung | liefert Status an Mensch, Fallkarte und Loesungsknoten zurueck |

---

## 6. Einbau in die sieben Testfaelle

### 6.1 Hitzestau

AEGIS-Rolle:

- Freigabe fuer physischen Eingriff pruefen
- Vorher-Nachher-Nachweis sichern
- Rueckdokumentation erzwingen

### 6.2 RAM

AEGIS-Rolle:

- Host-Machbarkeit als Pflichtbeweis erzwingen
- Erweiterung ohne Wartungsfenster blockieren
- Freigabe und Umsetzungsprotokoll absichern

### 6.3 Backupfenster

AEGIS-Rolle:

- Restore-Nachweis als Pflichtgrenze setzen
- Lastfenster ohne Freigabe nicht produktiv aendern lassen
- bei fehlendem Rueckfallpfad blockieren

### 6.4 Provisioning RAM und Storage

AEGIS-Rolle:

- gekoppelte Aenderung als hoeheren Eingriffsfall behandeln
- Thin-Provisioning und Rollback explizit pruefen
- Freigabe und Bestaetigung zusammenhalten

### 6.5 Kubernetes

AEGIS-Rolle:

- Cluster-Aenderung als B3-Fall erzwingen
- Rollback-Pflicht vor Mutation setzen
- Ereignisse, Klassenlage und Freigabe sichtbar koppeln

### 6.6 Netzwerk

AEGIS-Rolle:

- produktive Umschaltungen nur nach G3
- Gegenmessung und Rueckweg absichern
- Seiteneffekte auf mehrere Dienste mitdenken

### 6.7 NAS oder NetApp

AEGIS-Rolle:

- zentrale Storage-Aenderung als R3/B3 bis B4 behandeln
- Schnellloeschung oder Retention-Aenderung blockieren, solange keine starke Freigabe vorliegt
- Restore- und Compliance-Risiko in die Grenze ziehen

---

## 7. Was aus AEGIS nicht gemacht werden sollte

AEGIS sollte in GCA nicht als:

- mystische Superaufsicht
- allgemeines Bewusstseinsmodul
- unklare Sammelschicht fuer alles Schwierige

beschrieben werden.

Das waere zu unscharf. Stark wird AEGIS genau dann, wenn es eng bleibt:

- Vorpruefung
- Begrenzung
- Nachweissicherung
- Freigabeabsicherung
- Notstopp

---

## 8. Meine Einordnung

Persoenlich wuerde ich AEGIS fuer GCA klar empfehlen, aber nicht als erstes grosses Visionsthema, sondern als operativen Sicherheits- und Durchsetzungsrahmen.

Kurz:

> GCA ohne AEGIS bleibt erkenntnisstark, aber ausfuehrungsschwach.  
> AEGIS ohne GCA bleibt kontrollstark, aber problemverstaendlich schwach.

Gerade zusammen wird daraus etwas Brauchbares.

---

## 9. Priorisierte Einbaureihenfolge

1. AEGIS Vorpruefung an Loesungsknoten und Fallkarten koppeln
2. Klassenpruefung vor Produktiveingriff erzwingen
3. Nachweissicherung fuer Evidenz, Bestaetigung und Protokoll standardisieren
4. Notstopp- und Abbruchpfad definieren
5. erst spaeter feinere Unterkomponenten wie Canary, Hydra oder Dual Kernel sauber ausarbeiten

---

## 10. Schluss

AEGIS ist fuer GCA kein AGI-Baustein, sondern ein Einbau-Framework fuer kontrollierte Wirksamkeit.

Genau so wuerde ich es im Projekt fuehren:

- `AGI` nur als Ausblick
- `AEGIS` als konkreten Einbaurahmen
