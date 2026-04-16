Running single node made of old hardware with proxmox installed. Local IP address is `192.168.4.50`.

Had to give server a reserved IP in the router so that it will be static.

## VMs
### Ubuntu Server
Running several services that benefit in ease of use (or installation) from running on fully featured OS, including:
- [ctodo](https://github.com/CalebMostyn/ctodo)
	- Just installed the binary and barebones systemd service config and enabled it
- [OpenVPN](<Ubuntu Server/OpenVPN>)
- [Apache](<Ubuntu Server/Apache>)

Local IP address is `192.168.4.51`.

### [Pi-Hole](<Self Hosting/Pi-hole>)
Ad-blocking and DNS, based on debian.

### [[Homer]]
Simple static dashboard for links.

### [[Jellyfin]]
Self-hosted media streaming.

### [[qBittorrent]]
For fetching things for [[Jellyfin]].

### [[Radarr]]
Automatic downloader for movies.

### [[Sonarr]]
Automatic downloader for TV.

### [[Prowlarr]]
Automatic torrent indexer.

### [[Byparr]]
Cloudflare bot-detection avoider.

### [[Seerr]]
Automatic request manager for Jellyfin/Radarr/Sonarr.

## Todo
- Purchase quieter case fans
- Purchase better router, managed switch
- Purchase spool of Cat6, passthrough RJ45s, passthrough crimping tool, cable tester