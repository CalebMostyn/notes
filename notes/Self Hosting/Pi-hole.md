Ad-blocking and local DNS server. Uses unbound to do actual DNS, replacing ISP DNS server.  Link to [homepage](http://pi.hole/admin)

Had to set in router as primary DNS server.

Installed very easily on an LXC with the [community-scripts](https://community-scripts.org/scripts/pihole) install script.

Enabled conditional forwarding so VPN clients can make use of local DNS:
```
true,192.168.4.0/24,192.168.4.1
``` 

## Local DNS Records
- http://pi.hole
- http://proxmox.home:8006
- http://ubuntu-server.home