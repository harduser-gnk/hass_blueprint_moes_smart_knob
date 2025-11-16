## Adaptation for Moes ZG-101ZD Button

This blueprint project for Home Assistant using **Zigbee2MQTT** is an adaptation of the original  
[@TriggrHappy/hass_blueprint_tuya_smart_knob](https://github.com/TriggrHappy/hass_blueprint_tuya_smart_knob)  
to ensure correct operation with the [**Moes ZG-101ZD** button](https://www.zigbee2mqtt.io/devices/ZG-101ZD.html).

For some unknown reason, **Moes ZG-101ZD** always sends **two events** for each action:
- one from **command mode**
- and one from **event mode**

---

## Changes

### v1.1.1
- Disabled(commented) out the command mode switch [(Operation mode: "command")](https://www.zigbee2mqtt.io/devices/ZG-101ZD.html#operation-mode-enum)
- Added a filter for event mode packets (*single, hold, rotate_left, rotate_right*)


> ## The original description
>
> Blueprint to easily configure the **Tuya ERS-10TZBVK-AA Smart Knob** to control a light entity when integrated into Home Assistant using **Zigbee2MQTT**.
>
> It is based directly on the MQTT topic, as this turned out to be the most responsive way to automate this dimmer device.  
> Also see the [device page](https://www.zigbee2mqtt.io/devices/ERS-10TZBVK-AA.html) on the Zigbee2MQTT website for more information.
>
> ---
>
> **Important Note:**  
> The device needs to be in **COMMAND mode** – the other one being **EVENT mode** – for the automation to work.  
> However, the blueprint will automatically check for the correct mode and should keep the device in COMMAND.
>
> A triple-press changes the mode manually.  
> You can also see the current mode in the Home Assistant device page or in Zigbee2MQTT.
>
> ---
>
> <details>
> <summary><b>Actions</b></summary>
>
> - Press button: Toggle light  
> - Long press: Choose any Action  
> - Turn left/right: Change brightness / dim light  
> - Press, hold **and then** turn left/right: Change color temperature
>
> </details>
>
> <details>
> <summary><b>Features</b></summary>
>
> - The automation checks for the correct mode of the smart knob and will keep it in **COMMAND** mode.  
> - The maximum and especially minimum brightness is adjustable, preventing unwanted switch-off due to dimming too low (set minimum brightness > 0).  
> - Minimum and maximum color temperature can be configured. See [Color temperature](https://en.wikipedia.org/wiki/Color_temperature) to match Kelvin values with your desired effect.  
> - Fine-tune the resolution of color-temperature adjustments through a step multiplier (1–10).
>
> </details>
