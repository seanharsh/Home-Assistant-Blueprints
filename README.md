# Blueprints for Home Assistant

## Sunrise Light Simulator

A blueprint that gradually brightens your lights and changes their color temperature to simulate a natural sunrise over a customizable duration.

### Features

- 🌅 **Natural sunrise simulation** - Gradually transitions from deep red/orange to bright daylight
- 🎯 **Flexible targeting** - Select individual lights, multiple entities, entire areas, devices, or labels
- ⏱️ **Customizable duration** - Set sunrise length from 10 to 120 minutes
- 💡 **Adjustable brightness** - Set maximum brightness as a percentage (1-100%)
- 🎨 **Color temperature progression** - Smoothly transitions through 2000K → 2200K → 2700K → 3500K → 4500K → 5500K

### Configuration

When creating an automation from this blueprint, you'll configure:

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| **Lights** | Yes | - | Select lights by entity, area, device, or label |
| **Start Time** | Yes | - | Time to start the sunrise (e.g., 06:45:00) |
| **Duration** | No | 45 minutes | How long the sunrise should last (10-120 minutes) |
| **Maximum Brightness** | No | 100% | Maximum brightness level at the end (1-100%) |

### Usage Example

1. Go to **Settings** → **Automations & Scenes** → **Automations**
2. Click **Create Automation** → **Sunrise Light Simulator**
3. Configure:
   - **Lights**: Select your bedroom lights or bedroom area
   - **Start Time**: 06:45:00
   - **Duration**: 45 minutes
   - **Maximum Brightness**: 80%
4. Save the automation

Your lights will now gradually wake you up with a natural sunrise simulation every morning!

### How It Works

The blueprint creates a 5-stage sunrise progression:

1. **Stage 1** (0-11%): Deep red/orange (2000K) - Very dim
2. **Stage 2** (11-33%): Warm orange (2200K) - Gentle glow
3. **Stage 3** (33-55%): Warm yellow (2700K) - Soft light
4. **Stage 4** (55-77%): Neutral white (3500K) - Increasing brightness
5. **Stage 5** (77-100%): Cool daylight (4500K → 5500K) - Full brightness

Each stage uses smooth transitions to create a natural, gradual effect.

### Requirements

- Home Assistant 2021.3 or newer
- Lights that support:
  - Brightness control
  - Color temperature (Kelvin) control

## Troubleshooting

**Lights don't support color temperature:**
- The automation will still work for brightness, but color changes may be ignored
- Consider using RGB lights or lights with tunable white capability

**Automation doesn't trigger:**
- Check that the start time is set correctly
- Verify the automation is enabled
- Check Home Assistant logs for errors

**Transitions aren't smooth:**
- Some lights have limitations on transition duration
- Try adjusting the duration to be longer

### Installation

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fseanharsh%2FHome-Assistant-Blueprints%2Fmain%2Fautomation%2Fsunrise_light_simulator.yaml)

### Option 2: Manual Installation
1. Copy the blueprint YAML code
2. In Home Assistant, go to **Settings** → **Automations & Scenes** → **Blueprints**
3. Click the **Import Blueprint** button
4. Paste the URL or YAML content
5. Click **Preview** and then **Import**

## Zigbee2MQTT Dual Setpoint Fix

Helps fix issues where a high and low setpoint are required for some thermostats in Zigbee2MQTT.

### How It Works

Sets a target temp for high and low values.

### Requirements

- Home Assistant 2021.3 or newer
- Zigbee Thermostat with dual setpoint requirement such as the SAGE (Pearl)

### Installation

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fseanharsh%2FHome-Assistant-Blueprints%2Fmain%2Fautomation%2Fz2m_thermostat_dual_setpoint_fix.yaml)

### Option 2: Manual Installation
1. Copy the blueprint YAML code
2. In Home Assistant, go to **Settings** → **Automations & Scenes** → **Blueprints**
3. Click the **Import Blueprint** button
4. Paste the URL or YAML content
5. Click **Preview** and then **Import**


## License

These blueprints are free to use and modify for personal and commercial purposes.

## Contributing

Found a bug or have a suggestion? Please open an issue or submit a pull request!

## Credits

Created for the Home Assistant community.
