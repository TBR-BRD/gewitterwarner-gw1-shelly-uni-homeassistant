# Shelly UNI Notizen

## Home Assistant

Der Shelly UNI kann ueber die Home-Assistant-Shelly-Integration eingebunden werden. Danach erscheinen die Eingänge und Diagnosewerte als Entitäten.

## Benoetigte Entitaeten

Platzhalter in den oeffentlichen Vorlagen:

- `binary_sensor.gw1_shelly_uni_input_0`
- `binary_sensor.gw1_shelly_uni_input_1`
- `sensor.gw1_shelly_uni_pulse_counter`
- `sensor.gw1_shelly_uni_pulse_frequency`
- `switch.gw1_shelly_uni_output_0`
- `switch.gw1_shelly_uni_output_1`
- `device_tracker.gw1_shelly_uni`
- `update.gw1_shelly_uni_firmware`
- `switch.gw1_shelly_uni_internet_access`

## Entity-IDs finden

In Home Assistant:

1. Einstellungen
2. Geraete & Dienste
3. Shelly UNI auswaehlen
4. Entitaeten oeffnen
5. passende Entity-IDs lokal in `local/ENTITY_MAPPING.private.md` eintragen

## Logik pruefen

Beim Testen die GW1-Ausloesung beobachten:

- Eingang `on` bei Warnung: Template kann unveraendert bleiben.
- Eingang `off` bei Warnung: Template-Logik in `home-assistant/packages/gewitterwarner_gw1_shelly_uni.yaml` invertieren.
