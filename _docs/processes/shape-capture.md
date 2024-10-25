---
title: Shape Capture (Full Scale)
permalink: /docs/shape-capture/
---
PARSEC targets two primary tasks: capture of shape and simple texture, and capture of complex appearance. This page details how to capture shape with simple base texture using the camera rig for a person or something similar in size.

### Shape & Texture Capture with PARSEC, Human Scale
The main equipment of PARSEC is modeled after setups commonly used in the video games industry to capture a character model from an existing person. The person steps into the capture space and many cameras at different angles are fired nearly simultaneously while the area is flooded with bright light. The resulting photographs are processed with commercial software (we recommend Agisoft Metashape) to reconstruct the shape and basic appearance of the person as a polygon mesh with a detailed color texture.

Below are the recommended steps for this process on the PARSEC system which should result in a highly-detailed polygon mesh with a high-resolution texture for the person or object you are scanning.

#### Steps for Human Scale Capture
### Preliminary
Your account will need to be authorized and setup with access to the PARSEC computers. Contact prof better for details and to request access.

### Power Up
All the computers and cameras need to be powered up before proceeding:
1. Walk around to each main pillar in the structure and locate the single power strip.
2. To power up the cameras, switch the power strip on (the switch will light up when it is on).
3. On each side of the structure, in the central pillar, there is a round power switch for each satellite computer. Turn these on to power up the camera (they light up when they are on).

### Server Startup
The four satellite computers need to be running the canon capture server software:
1. On the remote satellite monitor, make sure the power is on then wakeup the computers by moving the mouse.
  - If you don't see anything, try holding the windows key and pressing P twice.
  - This will change the current monitor mode between 'extend' and 'duplicate' (and other modes).
  - Wait 10 seconds or so and try this again until the desktop appears. 
3. Log in with your Stout account.
4. Look for the PARSEC server folder on the desktop and open it.
5. Double click the `runServer.bat` file to start the server software.
6. (optional) Double click the `serverDashboard.bat` file to open the log dashboard.
7. Switch to the next satellite computer by pressing the KVM switch button near the monitor.
8. Repeat steps 2-6 for each of the four satellite computers.

### Client/Main Workstation Startup
The main workstation computer runs the Canon Control Client software that communicates with each of the satellite computers:
1. Power up and log in to the main workstation computer.
4. Look for the PARSEC client folder on the desktop and open it.
5. Double click the `runClient.bat` file to start the server software.
6. Open a web browser (preferably Chrome) and navigate to the client dashboard at `http://127.0.0.1:8000` (do not use 'localhost' as data is stored with the specific IP address).

### Accept the Self-Signed Certificates
The servers use a self-signed certificate for secure communication which must be provisionally accepted about once a day.
1. In the same web browser, open a new tab and navigate to `https://10.1.1.101:42424/camera`
2. When warned about the certificate, click 'Advanced' and then 'Proceed to this website (unsafe)'.
3. Repeat steps 1-2 for each IP addresses ending in 102, 103, and 104.

### Checking Camera Function
Now the client and server programs should be able to communicate and you can check if each camera is functioning properly:
1. On the client web page, refresh the page and look for status messages in the lower right.
2. If there are any red messages, these must be addressed before proceeding (you may need to accept the self-signed certificates or check that the servers are running properly).
3. Select the `list` tab at the top to see the camera list for each satellite computer.
4. For each computer (North, East, South, West), click it's name near the top.
5. Look for any malfunctioning cameras in the list and make note of their numbers
6. Go to these cameras and unplug their power then plug them back in to reset them.
7. Return to the client web page and refresh the list (not the web page, just the list).
8. Repeat this process until most of the cameras are functioning properly (there are always a few that refuse to work and the system has redundancies so you can proceed with a few cameras down).
