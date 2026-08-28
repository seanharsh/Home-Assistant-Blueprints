# Changelog

All notable changes to this project's blueprints.

## Sunrise Light Simulator

### [v1.6.0] - Unreleased

**Added:**
- Customizable start and end color temperature (Kelvin) with presets (1800-6500K)
- Reorganized blueprint inputs for better user workflow

**Changed:**
- Color temperature formula now uses user-selected values instead of hardcoded 2000K→5500K

---

### [v1.5.0] - 2026-04-10

**Added:**
- Day-of-week filtering (run only on selected days: Mon, Tue, Wed, etc.)

---

### [v1.4.0] - 2026-04-10

**Added:**
- Startup brightness configuration (avoids flickering on sensitive lights like Govee)
- Device-specific step interval guidance (LIFX 5-10s, Hue 10-15s, Govee 15-30s)

---

### [v1.3.0] - 2026-01-21

**Added:**
- Stop on manual off (stops automation if light turned off during simulation)
- Graceful error handling for multi-light setups
- 2-second startup delay for better device response

---

### [v1.2.0] - 2026-01-20

**Added:**
- Non-linear brightness curve (power of 1.3) for natural feel
- Configurable step interval (5-60 seconds)
- Hardware-level transitions for smoother updates

---

### [v1.1.0] - 2025-10-21

**Added:**
- Pre/post-sunrise action hooks

---

### [v1.0.0] - 2025-10-20

**Initial Release:**
- Gradual brightness increase from startup to maximum
- Color temperature transition (2000K to 5500K)
- Multi-light targeting (entity, area, device, label)

---

## Zigbee2MQTT Dual Setpoint Fix

### [v1.0.0]

**Initial Release:**
- Maps single temperature to separate high/low setpoints
- Mode-aware (heat/cool/off modes)
- Optional Fahrenheit conversion

---

## Links

- **Community Forum:** https://community.home-assistant.io/t/sunrise-light-simulator/943155
- **Feature Roadmap:** `automation/TODO.md`
