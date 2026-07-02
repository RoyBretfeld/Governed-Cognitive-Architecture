# Registry-Erweiterung: GCA Frameworks v0.1

**Status:** Vorschlag  
**Wichtig:** Die bestehende Registry bleibt unverändert eigenständig.

---

## Grundsatz

Die vorhandene Registry mit Modulen, Tools, Skills und Plugins bleibt bestehen.

Die Governed Cognitive Architecture (GCA) wird nur als zusaetzliche Ordnung ergaenzt.

Nicht ersetzen:

```text
modules.index.md
skills.index.md
tools_index.md
specs/
mobile/
```

Ergänzen:

```text
frameworks.index.md
patterns.index.md
solutions.index.md
```

---

## Neue Datei: frameworks.index.md

Zweck:

```text
Alle übergeordneten Frameworks und Denkmodelle erfassen.
```

Beispiel-Eintrag:

```markdown
| Framework | Status | Projekte | Kurzbeschreibung |
|---|---|---|---|
| Governed Cognitive Architecture (GCA) | v1.0 | Systemuebergreifend | Mehrschichtige Architektur mit Cognitive Layer, Knowledge Layer, Governance-Grenzen und simulativer Validierung. |
```

---

## Neue Datei: patterns.index.md

Zweck:

```text
Wiederverwendbare Entscheidungs-, Wartungs-, Diagnose- und Governance-Muster erfassen.
```

Beispiele:

```text
- 20-Iterationen-Regel
- Bedeutungstreue-Regel
- Denken autonom, Handeln kontrolliert
- Lösungsknoten-Prinzip
- Checkliste-wird-Protokoll-Prinzip
- Preventive-Maintenance-Kreislauf
```

---

## Neue Datei: solutions.index.md

Zweck:

```text
Gelöste Problemfälle als abrufbare Lösungsknoten erfassen.
```

Beispiel:

```markdown
| Lösungsknoten | Bereich | Status | Kurzbeschreibung |
|---|---|---|---|
| Rack-Hitzestau-Kabel-Luftstrom | Serverbetrieb | Gelöst | Temperaturanstieg von unten nach oben deutet auf blockierten Luftstrom / Kabelstau hin. |
```

---

## Harte Abgrenzung

Historisch ging diese Erweiterung aus dem Gedankenspiel Framework hervor. Im aktuellen Zielstand ist GCA kein Ersatz fuer die Registry.

GCA nutzt die Registry als Gedaechtnis und erweitert sie nur dort, wo Frameworks, Patterns und Loesungsknoten noch keinen sauberen Platz haben.
