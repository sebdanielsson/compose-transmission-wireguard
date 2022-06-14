# compose-transmission-wireguard

Run Transmission through a WireGuard tunnel with Docker Compose.

[![GitHub](https://img.shields.io/badge/github-blue?style=flat&color=grey&logo=GitHub)](https://github.com/SebDanielsson/compose-transmission-wireguard)
[![GitHub stars](https://img.shields.io/github/stars/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/issues)
[![GitHub forks](https://img.shields.io/github/forks/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/network)
[![GitHub license](https://img.shields.io/github/license/SebDanielsson/compose-transmission-wireguard?style=flat&color=blue&logo=github)](https://github.com/SebDanielsson/compose-transmission-wireguard/blob/main/LICENSE)

[![buymeacoffee_img]][buymeacoffee_url]

[buymeacoffee_img]: https://img.shields.io/badge/donate-BuyMeACoffee-ffdd00?logo=buymeacoffee&style=flat
[buymeacoffee_url]: https://buymeacoffee.com/danielsson

## Changelog

**2022-06-14:**

* Remove default config directory.
* Add transmission.env to separate secrets from the compose file.
* Switch to [Transmissionic](https://github.com/6c65726f79/Transmissionic) theme bundled with [linuxserver/docker-transmission](https://github.com/linuxserver/docker-transmission).

**2021-08-17:**

* Enable IPV6 [#3](https://github.com/SebDanielsson/compose-transmission-wireguard/pull/3)
* Removed `version` and renamed `docker-compose.yml` to `compose.yaml` according to [The Compose Specification](https://github.com/compose-spec/compose-spec/blob/master/spec.md#compose-file).

**2021-02-22:**

* First release!

## WireGuard VPN providers

Here is a list of WireGuard VPN providers. I've chosen to only list providrs what have a maximum of 2 major concerns over at [safetydetectives.com](http://safetydetectives.com/best-vpns/#simple), these concerns can not be security related. I receive no commission for linking to these providers. Personally I have only tested Mullvad, which are a great provider, so I can't speak for the others. Read about them and make up your own decision.

| Provider                            | No. of major concerns | WireGuard Port Forwarding |
| ----------------------------------- | --------------------- | ------------------------- |
| [Mullvad](https://mullvad.net)       | 0                     | ✅ [Source](https://mullvad.net/sv/help/port-forwarding-and-mullvad/#addingaport) |
| [Private Internet Access](https://www.privateinternetaccess.com) | 0 | ✅ [Source](https://www.privateinternetaccess.com/helpdesk/kb/articles/manual-connection-and-port-forwarding-scripts) |
| [OVPN](https://ovpn.com)             | 1                     | ✅ [Source](https://www.ovpn.com/en/blog/vidarebefordra-portar-i-ovpn) |
| [IVPN](https://ivpn.net)             | 0                     | ✅ Not available in the US. [Source](https://www.ivpn.net/knowledgebase/general/how-do-i-activate-port-forwarding/) |
| [AirVPN]([https://azirevpn.com](https://airvpn.org))     | 1                     | ✅ [Source](https://www.reddit.com/r/VPNTorrents/comments/s9f36q/list_of_vpns_that_allow_portforwarding_2022/) |
| [AzireVPN](https://azirevpn.com)     | 1                     | ✅ [Source](https://www.reddit.com/r/VPNTorrents/comments/s9f36q/list_of_vpns_that_allow_portforwarding_2022/) |

## Usage

1. `git clone https://github.com/SebDanielsson/compose-transmission-wireguard.git`
2. Edit `wg0.conf` (WireGuard) with credentials from your VPN provider.
3. Edit `transmission.env` and add your preferred username and password to access the WebUI. Also change  peerport to a port that is open at your VPN provider.
4. `docker compose up -d` and you should be up and running.
5. The Transmission WebUI is accessible at 127.0.0.1:9091. I highly recommend to use a VPN to access your WebUI remotely.

### Killswitch

Update `bind-address-ipv4` and `bind-address-ipv6` in Transmission's `settings.json` to the external IP of the VPN server for a built in kill switch.

### Themes

Default WebUI theme is [Transmissionic](https://github.com/6c65726f79/Transmissionic) bundled with [linuxserver/docker-transmission](https://github.com/linuxserver/docker-transmission). See their repo for alternatives.

## Donate

<a href="https://buymeacoffee.com/danielsson" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/white_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

## Contribute

All contributions are appreciated

## License

MIT
