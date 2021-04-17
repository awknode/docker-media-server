# docker-media-server
Docker Plex Server / Wireguard Client / Deluge / Jackett / Radarr / Sonarr / NVIDIA GPU Passthrough (optional, #commented out) in one .yml file

Follow the https://github.com/sebgl/htpc-download-box#readme instructions on getting the basics setup, he did a great job with documentation, why damage a good thing.

gpu.sh will brute force gpu passthrough with the plex server. you'll want to mount it and docker exec -it plex /config/gpu.sh (as i do) or you can modify it to your liking.
