# docker-media-server-htpc
Docker Plex Server / Wireguard Client / Deluge) / Prowlarr / Radarr / Sonarr / Lidarr / Overseerr / Organizr / NVIDIA GPU Passthrough (optional, #commented out) in one .yml file

For GPU passthrough, requirements are as needed at minimum:
1. proper nvidia drivers installed
2. nvidia-docker installed
3. nvidia-container-toolkit (cuda)
4. nvidia-container-runtime (to correct runtime errors with OCI)
5. make sure docker is running and working
6. make sure your graphics card is gtx 960 or later
7. make sure you can run nvidia-smi inside your docker container, <code>docker exec -it plex nvidia-smi</code> to ensure you see the Drivers installed and CUDA version, as well as more information.

Follow the https://github.com/sebgl/htpc-download-box#readme instructions on getting the basics setup, he did a great job with documentation, why damage a good thing.

gpu.sh will brute force gpu passthrough with the plex server. you'll want to mount it and run 

<code>docker exec -it plex /config/gpu.sh</code>
(as i do) or you can modify it to your liking.

This is great for a LAN if you have unlimited data, as all your data is encrypted with wireguard and the wireguard gateway is only accessed by the gateway which only deluge is set to as you'll see in the .yml file (refer to networks: service:wireguard). 

You could even route yourself through this traffic, a simple change of configuration with your gateway and networking configurations. I'm willing to help if you need it, let me know. (with any part of this setup)

In short, once this is up and running, just do the following:
1. Open up your favorite browser
2. Jackett -- Load http://localhost:9117
3. Deluge -- Load http://localhost:8112
4. Sonarr -- Load http://localhost:8989
5. Radarr -- Load http://localhost:7878
6. Prowlarr -- Load http://localhost:9696 (replacing Jackett)
7. Overseerr -- Load http://localhost:5055
8. Plex Media Server installation help -- Load https://support.plex.tv/articles/200288586-installation/

gl ; hf
