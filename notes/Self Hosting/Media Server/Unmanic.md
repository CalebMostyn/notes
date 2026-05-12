Automatic file management for media server. Scans library files and transcodes where necessary. Link to [dashboard](http://192.168.4.98:8888).

~~Right now only will run from 00:00-08:00~~. Currently set up to convert everything to H.265 and .mkv, as well as do other nice things like make English the default audio/subtitles. Any transcodings that will increase the size of the file are rejected. Should allow for everything to be downloaded/ripped at full quality (remux), as after its transcoded it should result in a very significant compression.

Default /tmp directory for the LXC was in RAM, so it was causing massive bottlenecks where there wasn't enough physical memory + swap to hold everything being worked on at once and memory was constantly almost maxed out (probably some leaks going on) and jobs would "succeed" but then attempt to be converted again because the file never actually was modified.

Symlinked `/tmp/unmanic` to `/mnt/media/.unmanic-tmp` so its on the shared filesytem.