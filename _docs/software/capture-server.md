---
title: Canon Control Server
permalink: /docs/capture-server/
---
### PARSEC Canon Control Server Software
The [Canon Control Server](https://github.com/UWStout/nodejs-canon-control-server.git){:target="_blank"} program is a tool for controlling all aspects of supported Canon cameras.  It is free open-source software implemented in JavaScript utilizing the node.js ecosystem. It runs natively on a desktop computer and can control supported models of Canon cameras connected via USB.

#### Supported Platforms
The Canon Control Software is built on top of the Canon EDSDK (a free developer tool provided by Canon). Because of this, is is restricted to the same platforms supported by that SDK.

- Windows: fully supported
- MacOS: experimental (may be supported in the future)
- Linux: not supported by EDSDK (might be possible with a tool like Wine or Photon)

The server runs in the node.js JavaScript interpreter and utilizes the node package manager ecosystem to download and manage dependencies.

#### Getting Started
The Canon Control Server Software is hosted at github. You can download and run the software as follows:
- Clone [the repository hosted at github](https://github.com/UWStout/nodejs-canon-control-server.git){:target="_blank"}
- Execute `npm i` to download and install dependencies

##### Configuring Environment Variables
You must provide several environment configuration variables in a `.env` file before you may launch the server.  There are many options that can be defined here:

Basic server options:
- `HOST_NAME`: The host name you want to bind to
- `DEV_PORT`: The IP port you want to bind to in development mode
- `PROD_PORT`: The IP port you want to bind to when NOT in development mode (production mode)
- `SERVER_KEY`: Path to a file containing the private key to use for SSL encryption
- `SERVER_CERT`: Path to the file containing the certificate to use for SSL encryption
- `DOWNLOAD_DIR`: Local directory to save images to as they are downloaded (may be a mounted network drive, see below)

Network attached storage options:
- `NAS_ENABLED`: Set to 'true' to enable the automatic mounting of network attached storage under windows
- `NAS_DRIVE_LETTER`: The windows drive letter to map the NAS to when it is mounted
- `NAS_SERVER_ADDRESS`: The hostname/ip address of the NAS (including any needed protocol or ports)
- `NAS_USERNAME`: A username for accessing the NAS (if required)
- `NAS_PASSWORD`: A plaintext password for accessing the NAS (if required)

##### NPM Package Scripts
To run the server you can execute `npm run server` but there are also many other scripts available that can be executed with `npm run`:
- `server:dev`: Run the server in development mode (with automatically restart server when changes are detected)
- `monit`: Run the server under the pm2 process monitoring system which will attempt to keep the server running and report statistics to the PM2 web portal
- `monit:dev`: Run monitored under pm2 but with the development flag to log and report more information
- `unmonit`: Stop a prevous `monit` or `monit:dev` task (which runs in the background)
- `dashboard`: Run monitored under pm2 with a LOCAL dashboard displaying the log and statistics of the server
