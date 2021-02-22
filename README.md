# compose-transmission-wireguard
Run Transmission through a WireGuard tunnel using this docker-compose.yml. The Transmission WebUI theme is combustion which is normally a light theme but I've applied my dark variant of this theme. This is optional.

[![GitHub](https://img.shields.io/badge/github-blue?style=flat&color=grey&logo=GitHub)](https://github.com/SebDanielsson/compose-transmission-wireguard)
[![GitHub stars](https://img.shields.io/github/stars/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/issues)
[![GitHub forks](https://img.shields.io/github/forks/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/network)
[![GitHub license](https://img.shields.io/github/license/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/blob/main/LICENSE)

## Changelog
**2021-02-22:** First release!

## Usage
1. `git clone https://github.com/SebDanielsson/compose-transmission-wireguard.git`

2. Edit `wg0.conf` (WireGuard) and `settings.json` (Transmission) to your liking.

3. `docker-compose up -d` and you should be up and running.

4. The Transmission WebUI is accessible at 127.0.0.1:9091 but I would highly recommend to use a reverse proxy like [Traefik](https://hub.docker.com/_/traefik) or [Nginx](https://hub.docker.com/r/linuxserver/swag) to access the WebUI wherever you are.

**Killswitch:** Update `bind-address-ipv4` and `bind-address-ipv6` in Transmission's `settings.json` to the external IP of the VPN server for a built in kill switch.

**Themes:** By default this compose file enables my own dark variant of the combustion theme.
To run the light combustion theme, just delete the bind mount `- ./dark-combustion/main.77f9cffc.css:/combustion-release/main.77f9cffc.css`
To run the default Transmission WebUI, delete both the previous bind mount and the environment variable `- TRANSMISSION_WEB_HOME=/combustion-release/`

## Donate
<a href="https://buymeacoffee.com/danielsson" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/white_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

## Contribute
All contributions are appreciated

## License
MIT
