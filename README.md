# docker-media-server
Docker Plex Server / Wireguard Client / Deluge (seedbox hosted by wireguard container [whatever VPN provider you want, just make sure there's a wireguard configuration file], I use my own dedi) / Jackett / Radarr / Sonarr / NVIDIA GPU Passthrough (optional, #commented out) in one .yml file

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

gl ; hf
