Open source torrent client, setup to route through VPN. Link to [dashboard](http://192.168.4.91:8090)

## VPN
Tried gluetun and WireGuard for auto setup, but kept getting stuck. Went for a simpler solution of running [[OpenVPN]] with systemd to connect to [ProtonVPN](https://account.proton.me/u/0/vpn/dashboardV2) with a free subscription.

Had to edit `/etc/pve/lxc/<qBittorrent-container-id>.conf` on the [[Proxmox]] node to allow the tunnel:
```
lxc.cgroup2.devices.allow = c 10:200 rwm
lxc.mount.entry = /dev/net/tun dev/net/tun none bind,create=file
```

Added a barebones `protonvpn` systemd service:
```
[Unit]
Description=ProtonVPN OpenVPN Service
After=network.target

[Service]
ExecStart=/usr/sbin/openvpn --config /etc/openvpn/protonvpn/us-free-33.protonvpn.udp.ovpn
Restart=always

[Install]
WantedBy=multi-user.target
``` 

And had to edit the `.ovpn` file downloaded from Proton to use my credentials automatically.

`curl ipinfo.io/json` is useful for a quick check if the VPN is working.

Set `Settings -> Advanced -> Network interface:` to the tunnel interface.

Had a problem where IP was leaked. Seems to be due to DNS, which was still going through the pihole. Installing openresolv allowed the ProtonVPN systemd job to correctly set to the VPN's DNS automatically. Also setup a killswitch to ensure all traffic goes through the tunnel using iptables, saved to be persistent with iptables-persistent:
```bash
netfilter-persistent save # saves to /etc/iptables/rules.v4 
```