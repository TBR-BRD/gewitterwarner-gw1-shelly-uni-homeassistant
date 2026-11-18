# Thunderstorm Warner GW1 + Shelly UNI + Home Assistant

[🇩🇪 Deutsch](README.md) · 🇬🇧 English

This project documents how to integrate a **GW1 thunderstorm warner** (German "Gewitterwarner") into **Home Assistant** via a **Shelly UNI**.

Home Assistant dashboard:

```text
http://<HA-IP>:8123/dashboard-gewitter/gewitter
```

<br>
<a href="https://www.buymeacoffee.com/thoralf.brandt" target="_blank">
  <img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174">
</a>
<br>

## Goal

- Capture the GW1 switching outputs via the Shelly UNI
- Show the warning status in Home Assistant as clear sensors
- Provide a dashboard for GW1 status, lightning rate, daily counter and the Blitzortung (lightning detection network) surroundings
- Version notifications and automations as templates

## Project structure

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

> The files in `docs/` and `shelly/` are written in German.

## Quick start

1. Add the Shelly UNI to Home Assistant.
2. Check the Shelly entity IDs that were found against [docs/ENTITY_MAPPING.md](docs/ENTITY_MAPPING.md).
3. Check the GW1 output logic: input `on` on warning, or input `off` on warning.
4. Enable the package file in Home Assistant or copy it into your existing `packages` structure.
5. Adapt the dashboard template from [home-assistant/dashboards/dashboard-gewitter.yaml](home-assistant/dashboards/dashboard-gewitter.yaml).

## Entity placeholders

The public YAML files use anonymized placeholders:

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

Real local entities belong in ignored private files under `local/`.

## Dashboard layout

The dashboard template has two areas:

- **GW1 (own sensor)**: thunderstorm warning, all-clear, lightning strikes today, lightning rate, history.
- **Surroundings & official warning**: Blitzortung distance, azimuth, counter and map.

## Safety

Only wire with the power off and check against the manuals of the GW1 and the Shelly UNI. The templates here are no substitute for an electrical inspection; they only describe the Home Assistant integration.

## Next steps

- Check the GW1 output logic: contact closed = warning, or the other way round?
- Adapt the look of the dashboard to your existing `dashboard-gewitter`
- Test the notification channel
