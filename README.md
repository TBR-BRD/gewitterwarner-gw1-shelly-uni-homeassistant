# Gewitterwarner GW1 + Shelly UNI + Home Assistant

Dieses Projekt dokumentiert die Einbindung eines **Gewitterwarners GW1** über einen **Shelly UNI** in **Home Assistant**.

Home-Assistant-Dashboard:

```text
http://<HA-IP>:8123/dashboard-gewitter/gewitter
```

## Ziel

- GW1-Schaltausgänge über Shelly UNI erfassen
- Warnstatus in Home Assistant als klare Sensoren darstellen
- Dashboard für GW1-Status, Blitzrate, Tageszähler und Blitzortung-Umgebung bereitstellen
- Benachrichtigungen und Automationen als Vorlage versionieren

## Projektstruktur

```text
.
├── docs/
│   ├── ENTITY_MAPPING.md
│   └── WIRING_NOTES_DE.md
├── home-assistant/
│   ├── dashboards/
│   │   └── dashboard-gewitter.yaml
│   └── packages/
│       └── gewitterwarner_gw1_shelly_uni.yaml
├── shelly/
│   └── README_DE.md
└── README.md
```

## Schnellstart

1. Shelly UNI in Home Assistant einbinden.
2. Die gefundenen Shelly-Entity-IDs in [docs/ENTITY_MAPPING.md](docs/ENTITY_MAPPING.md) prüfen.
3. GW1-Ausgangslogik prüfen: Eingang `on` bei Warnung oder Eingang `off` bei Warnung.
4. Package-Datei in Home Assistant aktivieren oder in die bestehende `packages`-Struktur kopieren.
5. Dashboard-Vorlage aus [home-assistant/dashboards/dashboard-gewitter.yaml](home-assistant/dashboards/dashboard-gewitter.yaml) anpassen.

## Entity-Platzhalter

Die oeffentlichen YAML-Dateien verwenden anonymisierte Platzhalter:

- `binary_sensor.gw1_shelly_uni_input_0`
- `binary_sensor.gw1_shelly_uni_input_1`
- `sensor.gw1_shelly_uni_pulse_counter`
- `sensor.gw1_shelly_uni_pulse_frequency`
- `sensor.gw1_lightning_rate`
- `sensor.gw1_lightning_daily`
- `sensor.blitzortung_lightning_distance`
- `sensor.blitzortung_lightning_azimuth`
- `sensor.blitzortung_lightning_counter`
- `switch.gw1_shelly_uni_output_0`
- `switch.gw1_shelly_uni_output_1`
- `device_tracker.gw1_shelly_uni`
- `update.gw1_shelly_uni_firmware`
- `switch.gw1_shelly_uni_internet_access`
- `notify.mobile_app_your_phone`

Echte lokale Entitaeten gehoeren in ignorierte private Dateien unter `local/`.

## Dashboard-Aufbau

Die Dashboard-Vorlage bildet zwei Bereiche ab:

- **GW1 (eigener Sensor)**: Gewitterwarnung, Entwarnung, Blitze heute, Blitzrate, Verlauf.
- **Umgebung & amtliche Warnung**: Blitzortung-Distanz, Azimut, Zaehler und Karte.

## Sicherheit

Verdrahtung nur stromlos und nach den Handbüchern von GW1 und Shelly UNI prüfen. Die Vorlagen hier ersetzen keine elektrische Prüfung; sie beschreiben nur die Home-Assistant-Integration.

## Nächste Schritte

- GW1-Ausgangslogik prüfen: Kontakt geschlossen = Warnung oder umgekehrt?
- Dashboard optisch an dein bestehendes `dashboard-gewitter` anpassen
- Benachrichtigungskanal testen
