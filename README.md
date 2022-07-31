# ESPHome configurations

This is a repo containing my ESPHome device configurations.

## Operations

### Starting the ESPHome dashboard

The dashboard can be started in docker using the following command on MacOS

```sh
docker run --rm -p 6052:6052 -e ESPHOME_DASHBOARD_USE_PING=true -v "${PWD}":/config -it esphome/esphome
```

### Pushing new firmware to devices

Device passthrough is not enabled with this command so the initial upload to a new device requires a binary download followed by an upload to the device using [ESPHome web tool](https://web.esphome.io/).

Once the first upload is done, over-the-air uploads will be available.

## Configurations

### garage-door.yaml

This uses the following components:
- HC-SR04 ultrasonic range sensor to detect an opened garage door
- 3.3v relay module setup as a momentary switch to trigger the garage door open/close functionnality

## Notes

### Static IPs?

I use static IPs because my devices are in a restricted VLAN that does not allow mDNS packets which are required for accessing `<device-name>.local`