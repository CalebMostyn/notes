Setup and configuration was done automagically with a script from a [git repo](https://github.com/Nyr/openvpn-install):

```bash
wget https://git.io/vpn -O openvpn-install.sh && bash openvpn-install.sh
```

The script generates the client key files, so rerun it to add new clients. Generates a .ovpn file, which must be moved to the client.

Stored it off in `~/openvpn/openvpn-install.sh`.

Had to port forward to default OpenVPN port (1194) in router.