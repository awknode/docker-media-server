# docker-media-server-htpc
Docker Plex Server / Wireguard Client / Rtorrent-flood / Prowlarr / Radarr / Sonarr / Lidarr / Overseerr / Organizr / NVIDIA GPU Passthrough (optional, #commented out) in one .yml file

For GPU passthrough, requirements are as needed at minimum:
1. proper nvidia drivers installed
2. nvidia-docker installed
3. nvidia-container-toolkit (cuda)
4. nvidia-container-runtime (to correct runtime errors with OCI)
5. make sure docker is running and working
6. make sure your graphics card is gtx 960 or later
7. make sure you can run nvidia-smi inside your docker container, <code>docker exec -it plex nvidia-smi</code> to ensure you see the Drivers installed and CUDA version, as well as more information.

Follow the https://github.com/sebgl/htpc-download-box#readme instructions on getting the basics setup, he did a great job with documentation, why damage a good thing.

gpu.sh will brute force gpu passthrough even without hardware acceleration enabled with the plex server (cost you plex pass). you'll want to mount it and run 

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
7. Overseerr -- Load http://localhost:5055
8. Plex Media Server installation help -- Load https://support.plex.tv/articles/200288586-installation/

Also very relevant to GPU passthrough: https://github.com/keylase/nvidia-patch <br>
gl ; hf
