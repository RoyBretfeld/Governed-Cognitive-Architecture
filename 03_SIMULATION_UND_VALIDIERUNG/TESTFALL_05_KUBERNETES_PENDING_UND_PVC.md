# Testfall 05 - Kubernetes / Pod Pending und PVC-Konflikt

## Ausgangslage

Ein produktiver Workload im Kubernetes-Cluster startet nach einem Deployment nicht mehr sauber.

Symptome:

```text
- mehrere Pods bleiben in Pending
- neue ReplicaSets werden erzeugt
- Service reagiert nur teilweise
- PVC ist gebunden oder wartet unklar
- mindestens ein Node ist ausgelastet oder tainted
```

Beispiel:

```text
Namespace: prod-app
Deployment: api-service
3 von 6 Pods Pending
PVC resize oder bind status unklar
Cluster unter Last
```

## Bekannte Loesung wird ausgeblendet

Das System kennt weder die konkrete spaetere Ursache noch ob Scheduling, Storage, Requests/Limits, Node-Affinity, Taints oder ein Freigabefehler den Ausschlag gegeben haben.

## Erwartete Denkwege

```text
- fehlen CPU oder RAM auf geeigneten Nodes?
- verhindern Taints, Affinity oder Topology-Regeln die Platzierung?
- blockiert der PVC oder das StorageClass-Verhalten?
- sind Requests/Limits falsch dimensioniert?
- wurde waehrend eines laufenden Change-Fensters etwas halb ausgerollt?
- muss horizontal skaliert, rollbackt oder nur das Scheduling korrigiert werden?
- ist die Stoerung clusterweit oder workload-lokal?
- welche Aenderungen waeren produktiv riskant und damit freigabepflichtig?
```

## Erwarteter Loesungsknoten

Das Framework soll nicht vorschnell "mehr Nodes" oder "mehr Ressourcen" empfehlen, sondern zunaechst Scheduling-, Storage- und Policy-Konflikte trennen.

Moegliche tragfaehige Richtung:

```text
1. Events, Requests/Limits, Taints, Affinity und PVC-Status auswerten
2. Konfigurationsfehler von echter Kapazitaetsgrenze trennen
3. nur freigegebene Massnahme empfehlen
4. Rollback, Resize oder Scheduling-Korrektur sauber protokollieren
```

## Erwartete Checkliste

```text
[ ] Pod-Events und Scheduler-Meldungen geprueft
[ ] Requests, Limits und HPA/VPA-Kontext geprueft
[ ] Node-Auslastung, Taints und Affinity-Regeln geprueft
[ ] PVC-, PV- und StorageClass-Status geprueft
[ ] Rollout-Historie und letzte Aenderungen geprueft
[ ] rollbackfaehige Option identifiziert
[ ] produktive Cluster-Aenderung als Policy-Klasse bewertet
[ ] Human Approval fuer P2 oder P3 eingeholt
[ ] Witness fuer Durchfuehrung und Stabilisierung abgelegt
[ ] Protokoll und Praeventionshinweis erstellt
```
