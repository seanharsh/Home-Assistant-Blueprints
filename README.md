# Blueprints for Home Assistant

## Sunrise Light Simulator

A blueprint that gradually brightens your lights and changes their color temperature to simulate a natural sunrise over a customizable duration.

### Features

- 🌅 **Natural sunrise simulation** - Gradually transitions from deep red/orange to bright daylight
- 🎯 **Flexible targeting** - Select individual lights, multiple entities, entire areas, devices, or labels
- ⏱️ **Customizable duration** - Set sunrise length from 5 to 120 minutes
- 💡 **Adjustable brightness** - Set maximum brightness as a percentage (1-100%)
- 🎨 **Color temperature progression** - Smoothly transitions from 2000K (warm) to 5500K (cool daylight)
- 📅 **Day-of-week filtering** - Run only on specific days (e.g., weekdays only, skip weekends)
- ⚙️ **Device-specific tuning** - Configure step interval for smooth transitions based on your light type
- 🔧 **Custom actions** - Add pre-sunrise setup actions or post-sunrise cleanup actions

### Configuration

When creating an automation from this blueprint, you'll configure:

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| **Lights** | Yes | - | Select lights by entity, area, device, or label |
| **Start Time** | Yes | - | Time to start the sunrise (e.g., 06:45:00) |
| **Duration** | No | 45 minutes | How long the sunrise should last (5-120 minutes) |
| **Maximum Brightness** | No | 100% | Maximum brightness level at the end (1-100%) |
| **Startup Brightness** | No | 1% | Initial brightness when simulation starts (1-100%). Increase to 5-10% if lights flicker at startup |
| **Step Interval** | No | 30 seconds | Time between brightness updates (5-60 seconds). Adjust for your light type: LIFX 5-10s, Hue 10-15s, Govee 15-30s |
| **Days of Week** | No | Every day | Select which days to run (leave empty for daily) |
| **Pre-Sunrise Actions** | No | - | Actions to run before the sunrise simulation starts |
| **Post-Sunrise Actions** | No | - | Actions to run after the sunrise simulation completes |

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

The blueprint uses a smooth, non-linear curve to simulate a natural sunrise:

- **Color temperature**: Progresses from warm (2000K) to cool daylight (5500K)
- **Brightness curve**: Uses a non-linear progression (power of 1.3) for natural-feeling transitions
- **Smooth transitions**: Updates brightness at configurable intervals (default 30 seconds)
- **Hardware aware**: Adjustable step interval and startup brightness for different light types
- **Smart light monitoring**: Stops if the light is turned off during the simulation
- **Flexible scheduling**: Run daily or only on specific days of the week

The algorithm starts at your configured startup brightness and smoothly increases to maximum brightness over the duration, while simultaneously shifting color temperature from warm to cool.

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
- Adjust **Step Interval** based on your light type (see configuration table)

**Lights flicker or don't respond at startup:**
- Increase **Startup Brightness** to 5-10% instead of the default 1%
- This helps with lights like Govee that have issues with very low commands

**Automation doesn't run on certain days:**
- Check that **Days of Week** is configured correctly
- Leave it empty to run every day
- Make sure you've selected the correct days (Monday-Sunday)

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
