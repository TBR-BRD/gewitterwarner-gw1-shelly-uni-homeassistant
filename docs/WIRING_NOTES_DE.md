# Verdrahtungsnotizen

Diese Datei ist eine Projektnotiz, keine verbindliche Installationsanleitung.

## Komponenten

- Gewitterwarner GW1
- Shelly UNI
- Home Assistant unter `http://<HA-IP>:8123`

## Grundidee

Der GW1 stellt einen oder mehrere Schaltzustände bereit. Der Shelly UNI liest diese Zustände als digitale Eingänge ein. Home Assistant verarbeitet die Shelly-Entitäten dann als Gewitterwarnstatus.

## Vor dem Anschließen prüfen

- Welche Ausgangsart liefert der GW1: potentialfreier Kontakt, Relaiskontakt, Open Collector oder Spannungsausgang?
- Welche Spannung liegt am jeweiligen GW1-Ausgang an?
- Welche Eingänge des Shelly UNI werden verwendet?
- Muss die Eingangslogik in Home Assistant invertiert werden?
- Haben GW1 und Shelly UNI eine gemeinsame Masse, falls erforderlich?

## Empfohlene Dokumentation

Notiere nach dem Test:

| Signal | GW1-Klemme | Shelly-Klemme | Home-Assistant-Entity | Logik |
| --- | --- | --- | --- | --- |
| Warnung |  |  |  |  |
| zweiter Status |  |  |  |  |
