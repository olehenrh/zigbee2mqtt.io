---
title: "Custom devices (DiY) DNCKATSW004 control via MQTT"
description: "Integrate your Custom devices (DiY) DNCKATSW004 via Zigbee2MQTT with whatever smart home
 infrastructure you are using without the vendors bridge or gateway."
---

*To contribute to this page, edit the following
[file](https://github.com/Koenkk/zigbee2mqtt.io/blob/master/docs/devices/DNCKATSW004.md)*

# Custom devices (DiY) DNCKATSW004

| Model | DNCKATSW004  |
| Vendor  | Custom devices (DiY)  |
| Description | [DNCKAT quadruple key wired wall light switch](https://github.com/dzungpv/dnckatsw00x/) |
| Supports | hold/release, on/off |
| Picture | ![Custom devices (DiY) DNCKATSW004](../images/devices/DNCKATSW004.jpg) |

## Notes

None

## Manual Home Assistant configuration
Although Home Assistant integration through [MQTT discovery](../integration/home_assistant) is preferred,
manual integration is possible with the following configuration:


{% raw %}
```yaml
switch:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    payload_off: "OFF"
    payload_on: "ON"
    value_template: "{{ value_json.state_bottom_left }}"
    command_topic: "zigbee2mqtt/<FRIENDLY_NAME>/bottom_left/set"

switch:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    payload_off: "OFF"
    payload_on: "ON"
    value_template: "{{ value_json.state_bottom_right }}"
    command_topic: "zigbee2mqtt/<FRIENDLY_NAME>/bottom_right/set"

switch:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    payload_off: "OFF"
    payload_on: "ON"
    value_template: "{{ value_json.state_top_left }}"
    command_topic: "zigbee2mqtt/<FRIENDLY_NAME>/top_left/set"

switch:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    payload_off: "OFF"
    payload_on: "ON"
    value_template: "{{ value_json.state_top_right }}"
    command_topic: "zigbee2mqtt/<FRIENDLY_NAME>/top_right/set"

sensor:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    icon: "mdi:signal"
    unit_of_measurement: "lqi"
    value_template: "{{ value_json.linkquality }}"
```
{% endraw %}


