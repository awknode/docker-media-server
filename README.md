# docker-media-server-htpc
Wireguard Client / Rtorrent-flood / Deluge / Prowlarr / Radarr / Sonarr / Lidarr / Organizr / Portainer / Docker Proxy

I installed plex directly onto the VM in this instance

Follow the https://github.com/sebgl/htpc-download-box#readme instructions on getting the basics setup, he did a great job with documentation, why damage a good thing

gpu.sh will brute force gpu passthrough even without hardware acceleration enabled with the plex server (cost you plex pass). you'll want to mount it and run 

Docker proxy is only used / needed for my locally run home assistant, you can comment it out if you'd like

<code>docker exec -it plex /config/gpu.sh</code>
(as i do) or you can modify it to your liking.

This is great for a LAN, as all your data is encrypted with wireguard and the wireguard gateway is only accessed by the gateway which only deluge is set to as you'll see in the .yml file (refer to networks: service:wireguard). 

In short, once this is up and running, just do the following:
1. Open up your favorite browser
2. Rtorrent-Flood -- Load http://localhost:3001
3. Sonarr -- Load http://localhost:8989
4. Radarr -- Load http://localhost:7878
5. Lidarr -- load http://localhost:8686
6. Prowlarr -- Load http://localhost:9696 (replacing Jackett)
8. Plex Media Server installation help -- Load https://support.plex.tv/articles/200288586-installation/

Also very relevant to GPU passthrough: https://github.com/keylase/nvidia-patch <br>
