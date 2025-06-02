# Smarthome

Smarthome Setup with Docker. With internal services and external services, configured in Træfik. HTTPS Certs via Træfik and Cloudflare.

## Hardware

 - Rasberry Pi 4, 4GB
 - Sonoff ZigBee Gateway ZigBee 3.0 USB Dongle Plus-E

## Software

- Træfik
- Home Assistant
- AdGuard Home
- Node RED
- [zigbee2mqtt](https://www.zigbee2mqtt.io/)
- zwavejs2mqtt

## Setup

1. Create `.env` file
2. Move the volume folder to the path you want to use. Make sure to change all the configs you want.
3. ???

## Z-wave

Generate NETWORK KEY:
`cat /dev/urandom | tr -dc '0-9A-F' | fold -w 32 | head -n 1 | sed -e 's/\(..\)/0x\1, /g' -e 's/, $//'`

## hs config for proxy

You might need to add this to the configuration.yml

```
http:
  use_x_forwarded_for: true
  trusted_proxies:
    - 172.0.0.0/8
```

## Setup MQTT

- https://www.home-assistant.io/docs/mqtt/broker
