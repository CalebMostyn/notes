Home media streaming. Link to [dashboard](http://192.168.4.84:8096)

Set up mount point on root proxmox node for shared access between utilities, added this to each `/etc/pve/lxc/<container id>.conf` file:
```
mp0: /mnt/media,mp=/mnt/media
```

## Todo
- Buy GPU to enable hardware acceleration for faster transcoding and lighter CPU load