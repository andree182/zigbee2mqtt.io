---
title: "Custom devices (DiY) ZWallRemote0 control via MQTT"
description: "Integrate your Custom devices (DiY) ZWallRemote0 via Zigbee2mqtt with whatever smart home
 infrastructure you are using without the vendors bridge or gateway."
---

*To contribute to this page, edit the following
[file](https://github.com/Koenkk/zigbee2mqtt.io/blob/master/docs/devices/ZWallRemote0.md)*

# Custom devices (DiY) ZWallRemote0

| Model | ZWallRemote0  |
| Vendor  | Custom devices (DiY)  |
| Description | Matts Wall Switch Remote (https://github.com/mattlokes/ZWallRemote) |
| Supports | on/off |
| Picture | ![Custom devices (DiY) ZWallRemote0](../images/devices/ZWallRemote0.jpg) |

## Notes

None

## Manual Home Assistant configuration
Although Home Assistant integration through [MQTT discovery](../integration/home_assistant) is preferred,
manual integration is possbile with the following configuration:


{% raw %}
```yaml
sensor:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    icon: "mdi:toggle-switch"
    value_template: "{{ value_json.click }}"

sensor:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    unit_of_measurement: "-"
    value_template: "{{ value_json.linkquality }}"
```
{% endraw %}


