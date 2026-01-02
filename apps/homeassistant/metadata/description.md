# Home Assistant

Open source home automation that puts local control and privacy first. Powered by a worldwide community of tinkerers and DIY enthusiasts. Perfect to run on a Raspberry Pi or a local server.

Check out [home-assistant.io](https://home-assistant.io) for a [demo](https://home-assistant.io/demo/), [tutorials](https://home-assistant.io/getting-started/automation/) and [documentation](https://home-assistant.io/docs/)

## App Features
- **Matter Server Included:** This app includes a Matter server, allowing you to add your Matter devices directly to Home Assistant.
- **Host mode by default:** The `host` network mode is enabled by default, allowing auto-discovery features to work out of the box.

## Required Configuration
### Accessing through the port
Since the host network mode is enabled by default, Runtipi’s port mapping will not work, so the service must be accessed directly via port `8123`.
### Accessing through a domain
Accessing through a domain is possible by exposing the app in the app settings, but it requires an additional Traefik configuration step:
- Create a custom Runtipi compose file ([guide](https://runtipi.io/docs/guides/customize-compose-and-traefik)).
- Modify your `tipi-compose.yml` to add the following: 
```yaml
services:
  runtipi-reverse-proxy:
    extra_hosts:
      - host.docker.internal:host-gateway
```
- Restart your Runtipi `sudo ./runtipi-cli restart`
- Now you can expose and assign a domain to the application.

