# compose-transmission-wireguard
Run Transmission through a WireGuard tunnel using this docker-compose.yml. The Transmission WebUI theme is combustion which is normally a light theme but I've applied my dark variant of this theme. This is optional.

[![GitHub](https://img.shields.io/badge/github-blue?style=flat&color=grey&logo=GitHub)](https://github.com/SebDanielsson/compose-transmission-wireguard)
[![GitHub stars](https://img.shields.io/github/stars/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/issues)
[![GitHub forks](https://img.shields.io/github/forks/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/network)
[![GitHub license](https://img.shields.io/github/license/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/blob/main/LICENSE)

## Changelog
**2021-02-22:** First release!

## WireGuard VPN providers
Here is a list of WireGuard VPN providers. I've chosen to only list providrs what have a maximum of 2 major concerns over at [safetydetectives.com](http://safetydetectives.com/best-vpns/#simple), these concerns can not be security related. I receive no commission for linking to these providers. Personally I have only tested Mullvad, which are a great provider, so I can't speak for the others. Read about them and make up your own decision.

| Provider                            | No. of major concerns | WireGuard Port Forwarding |
| ----------------------------------- | --------------------- | ------------------------- |
| [Mullvad](http://mullvad.net)       | 0                     | ✅ [Source](https://mullvad.net/sv/help/port-forwarding-and-mullvad/#addingaport) |
| [Private Internet Access](https://www.privateinternetaccess.com) | 0 | ✅ [Source](https://www.privateinternetaccess.com/helpdesk/kb/articles/manual-connection-and-port-forwarding-scripts) |
| [OVPN](http://ovpn.com)             | 1                     | ✅ [Source](https://www.ovpn.com/en/blog/vidarebefordra-portar-i-ovpn) |
| [WindScribe](http://windscribe.com) | 1                     | ✅ [Only partial](https://windscribe.com/features/port-forwarding) |
| [IVPN](http://ivpn.net)             | 0                     | ❌ [Source](https://www.ivpn.net/knowledgebase/general/how-do-i-activate-port-forwarding/) |
| [AzireVPN](http://azirevpn.com)     | 1                     | ❌ |

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
