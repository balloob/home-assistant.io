---
title: myIO
description: Instructions on how to integrate myIO Server into Home Assistant.
ha_category:
  - Climate
  - Cover
  - Light
  - Sensor
ha_release: 0.108
ha_iot_class: Local Poll
ha_config_flow: true
ha_codeowners:
  - '@smarthomeninja'
ha_domain: myio
---

The myIO integration adds support for [myIO-server](https://myio.com) controlled peripherals into Home Assistant. Features currently include:

- Import all sensors (temperature, humidity, consumption) as individual entities.
- Import all used digital outputs (with a description) as a light entity (except the sensor-controlled outputs).
- Import all PWM output as a brightness controlled light entity (except the sensor-controlled outputs).
- Import all sensor-controlled output (digital and PWM) to climate entities.
- Import all the groups, what's description begins with 'RGB' to RGB light entities.
- Import all the relay protection pairs to a cover entity. 

## Configuration

Home Assistant offers myIO integration through **Configuration** -> **Integrations** -> **myIO**. Follow the instructions to get it set up.

Parameter settings:

- 'Name' - this is a name of the server (example: "my Home", "Weekend House", "Office"). You can integrate more servers.
- 'Host' - this is the IP address of the myIO server.
- 'HTTP Port' - in case of port forwarding, you can change this.
- 'App Port' - in case of port forwarding, you can change this.
- 'Username' - Set the username to log in to myIO server.
- 'Password' - Set the password to log in to myIO Server.

Click 'Submit'.

The integration finds all of your discoverable devices and imports them to a Home Assistant.

## Notes

The following settings need to be set in the myIO Server UI.

- The RGBW lights description needs to start with the 'R','G','B','W' characters to describe the colors.
- The RGB group descriptions need to start with the 'RGB' characters.
- Your covers up and down relays need to be set to the relay protection pair. The first needs to be the 'up' direction.

Recommendation:

- Add a new user to myIO server for Home Assistant, and set the permissions for it.
