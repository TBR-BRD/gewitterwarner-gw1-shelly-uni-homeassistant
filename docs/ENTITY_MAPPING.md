# Entity Mapping Vorlage

Trage echte Home-Assistant-Entity-IDs nur lokal in eine private, ignorierte Datei ein, z. B. `local/ENTITY_MAPPING.private.md`.

| Funktion | Platzhalter | Echte Entity-ID lokal eintragen | Notiz |
| --- | --- | --- | --- |
| GW1 Warnkontakt 1 | `binary_sensor.gw1_shelly_uni_input_0` |  | Hauptwarnung / Alarm, Logik pruefen |
| GW1 Warnkontakt 2 | `binary_sensor.gw1_shelly_uni_input_1` |  | optionaler zweiter Status |
| Impulszaehler | `sensor.gw1_shelly_uni_pulse_counter` |  | optional, Zaehlimpulse |
| Impulsfrequenz | `sensor.gw1_shelly_uni_pulse_frequency` |  | optional |
| Shelly Output 0 | `switch.gw1_shelly_uni_output_0` |  | nicht fuer Warnlogik verwendet |
| Shelly Output 1 | `switch.gw1_shelly_uni_output_1` |  | nicht fuer Warnlogik verwendet |
| Shelly Online | `device_tracker.gw1_shelly_uni` |  | Verfuegbarkeit im Netzwerk |
| Shelly Firmware | `update.gw1_shelly_uni_firmware` |  | Firmwarestatus |
| Internetzugang | `switch.gw1_shelly_uni_internet_access` |  | Shelly Netzwerkoption |
| Mobile Benachrichtigung | `notify.mobile_app_your_phone` |  | Smartphone-App |

## Pruefpunkte

- Welche Shelly-Entitaet wechselt, wenn der GW1 ausloest: Eingang 0, Eingang 1 oder Impulszaehler?
- Ist die Logik normal oder invertiert?
- Gibt es getrennte GW1-Ausgaenge fuer Vorwarnung und Alarm?
- Soll Home Assistant nach Boot einen unbekannten Zustand als "keine Warnung" oder als "unbekannt" behandeln?
