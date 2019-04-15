# Assetto Corsa Competizione Server Container (that's a pretty long title right there)

[![](https://images.microbadger.com/badges/image/grimsi/accservermanager.svg)](https://microbadger.com/images/grimsi/accservermanager "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/grimsi/accservermanager.svg)](https://microbadger.com/images/grimsi/accservermanager "Get your own version badge on microbadger.com")

Docker container ready to run a Assetto Corsa competizione server instance.
It is based on Ubuntu (unfortunatly I could not get it to work with Alpine) and has Wine-Development installed to run the accServer.exe.

This container is used for every instance managed by my [ACC Server Manager](https://github.com/grimsi/accservermanager-backend).

## Usage

To run the ACC Server in a container you need to have the server downloaded on the same machine (I cant put it directly in the container since the server is copyrighted by Kunos).

Start the container with the following command:
```
docker run --name accServer -v <path to ACC server folder>:/opt/server -p <server port>:<server port>/tcp -p <server port>:<server port>/udp grimsi/accserver:latest
```
That's it! Your server should be now up and running. You can even create more instances and run them at the same time by copying the folder with the accServer.exe and changing the config options (you have to change the ports and remember to pass the new ports to the container when youre starting it).
