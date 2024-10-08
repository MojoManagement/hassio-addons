# ha-hotspot

### Configuration

The available configuration options are as bellow. Make sure to edit
according to your needs:

```
{
    "ssid": "HA Hotspot",
    "wpa_passphrase": "",
    "channel": "0",
    "address": "192.168.2.1",
    "netmask": "255.255.255.0",
    "broadcast": "192.168.2.254"
    "interface": ""
    "interface_internet": "eth0"
    "allow_internet": false
    "dhcp_server": true
    "dhcp_start": "192.168.2.10",
    "dhcp_end": "192.168.2.200",
    "dhcp_dns": "1.1.1.1",
    "dhcp_subnet": "255.255.255.0",
    "dhcp_router": "192.168.2.1",
    "hide_ssid": false,
    "driver": "nl80211"
}

```
When channel set to 0, it will automatically find the best channel. 

When the `interface` option is left blank, a list with the detected wlan
interfaces will be printed on the logs and the addon will terminate. Set
the correct `interface` value on the configuration then restart the addon.
