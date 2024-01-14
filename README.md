# UniFi-Network-Server
Docker compose UniFi Network Server + MongoDB (via LinuxServer.IO)
Combines the LinuxServer.IO docker image of the Unifi Network Application with one of the UniFi supported versions of MongoDB (4.4)

## Getting Started
1. Clone the repo
```bash
git clone https://github.com/aussieklutz/UniFi-Network-Server
cd UniFi-Network-Server
```
2. Create the persistent data directories
```bash
sudo mkdir -p /opt/unifi/db /opt/unifi/config
```
3. Create the config files, and set your own strong password
```bash
sudo cp init-mongo.js.example /opt/unifi/init-mongo.js
sudo nano /opt/unifi/init-mongo.js
nano .env
```
4.  bring the server up once, and make sure there are no port conflicts.
```bash
docker compose up
```
5. Once you have successfully run the server once, ctrl+c to shutdown.
6. Start the server in daemon / background mode.
```bash
docker compose up -d
```
7. The server should automatically be started by docker on boot.
8. Once you are in the UniFi application, you will need to navigate into Settings > System > Advanced and set the Inform Host to a hostname or IP address accessible by your devices. [Source: LinuxServers.IO](https://docs.linuxserver.io/images/docker-unifi-network-application/#device-adoption)

