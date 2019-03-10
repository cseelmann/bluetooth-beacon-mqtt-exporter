bluetooth-beacon-mqtt-exporter
==============================

This is a service running on node v8 publishing Bluetooth BLE beacons advertisements on a mqtt topic.

The original intent is to make available to node-RED temperature readings from Estimote beacons ; but this will work with any beacon advertisement supported by the [node-beacon-scanner](https://github.com/futomi/node-beacon-scanner) module.


Dependencies
------------


```sh
sudo apt-get install bluetooth
```

and the bluetooth-beacon-mqtt-exporter command must be run as `root`.


Install
-------


```sh
npm install bluetooth-beacon-mqtt-exporter
```


Run
---

```sh
sudo bluetooth-beacon-mqtt-exporter
```


Configuration
-------------

Configuration is provided throught environment variables:

```sh
MQTT_BROKER=mqtt://127.0.0.1   # url of a mqtt broker. For accepted protocols, refer to https://github.com/mqttjs/MQTT.js#connect
MQTT_TOPIC=beacon              # mqtt topic beacon' advertisements will be published to
MQTT_RECONNECT_DELAY=5000      # in case of a mqtt disconnection, will wait this amount of milliseconds before retrying to connect
LOG_PACKETS=no                 # yes/on/true/1 to log every advertisement package to the console
```

Hack
----


### Install dependencies

```
sudo apt-get install bluetooth bluez libbluetooth-dev libudev-dev
```


### Run the services


```
sudo service bluetooth start
sudo export MQTT_BROKER=mqtt://127.0.0.1 
sudoo export MQTT_TOPIC=beacon 
sudo npm run bluetooth-beacon-mqtt-exporter start
```

