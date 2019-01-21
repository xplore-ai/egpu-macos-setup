# egpu-macos-setup
MacOS setup to use our eGPUs

## Requirements
- macOS 10.13.X ≤ 10.13.6 (17G65)
- ThunderBolt supported Mac
- External display
- disabled SIP
- macOS terminal (iTerm not supported)


## Basic setup

**Disable SIP**

1. Reboot you mac into recovery mode (Command<R> during boot)
2. Open terminal (Utilites -> Terminal) and execute `csrutil disable; reboot`

**eGPU setup**

3. Boot normally and log-in with all unnecessary peripherals disconnected. Especially eGPUs!
4. Open Terminal App (iTerm not supported) and execute:
```
 bash <(curl -s https://raw.githubusercontent.com/learex/macOS-eGPU/master/macOS-eGPU.sh)
```
Follow the installation process of the script (attention to the connection and disconnection of the egpu step)

Next times the script can be called by `macos-egpu`


## Use
**Plug:** Reboot and plug the eGPU before login

**Unplug:** Reboot and unplug the eGPU when Mac is off.


## Known troubles and common solutions

**Black display**
- Step set 1
	1. boot without eGPU
	2. hot plug eGPU with monitor
	3. log out
- Step set 2
	1. boot without eGPU
	2. hot plug eGPU only (no external monitor)
	3. wait 15 sec
	4. log out
	5. hot plug monitor
	6. wait 15 sec
	7. log in
- Step set 3
	1. boot without eGPU
	2. log out
	3. hot plug eGPU
- Step set 4 (no FileVault)
	1. boot without eGPU
	2. hot plug before first login

**UI Lagging**
1. Boot with eGPU
2. Install [DisableMonitor](https://github.com/Eun/DisableMonitor/releases/download/G1.92/DisableMonitor-G1.92.zip)
3. Disable the built-in display

## Important links and further information
- [learex/maOS-eGPU](https://github.com/learex/macOS-eGPU)
- [eun/DisableMonitor](https://github.com/Eun/DisableMonitor)
- eGPU.io [Setup Guide](https://egpu.io/setup-guide-external-graphics-card-mac)
