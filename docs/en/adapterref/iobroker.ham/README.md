![Logo](admin/ham.png)
# ioBroker Homebridge accessories manager

![Number of Installations](http://iobroker.live/badges/ham-installed.svg)
![Number of Installations](http://iobroker.live/badges/ham-stable.svg)
[![NPM version](http://img.shields.io/npm/v/iobroker.ham.svg)](https://www.npmjs.com/package/iobroker.ham)

![Test and Release](https://github.com/ioBroker/iobroker.ham/workflows/Test%20and%20Release/badge.svg)
[![Translation status](https://weblate.iobroker.net/widgets/adapters/-/ham/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)
[![Downloads](https://img.shields.io/npm/dm/iobroker.ham.svg)](https://www.npmjs.com/package/iobroker.ham)

Use Homebridge plugins in ioBroker or run a global installed Homebridge as ioBroker adapter.
All States from Homebridge will be available in ioBroker too and can also be controlled there.

## Description
This adapter provides three different modes:

### Default (Wrapper) Mode
In the default mode the adapter allows you to use homebridge Plugin Modules directly.
You can explore all available plugins at the NPM website by [searching for the keyword `homebridge-plugin`](https://www.npmjs.com/search?q=homebridge-plugin).

You simply add the list of modules to the Adapter configuration and provide the configuration
in the JSON-editor (see Plugin descriptions).
After this, all Homebridge objects will be created in ioBroker too and all writable objects can
be changed too.

**IMPORTANT: This mode allows to use the device integrations of the provided homebridge plugins. No "bridge" is provided that can be used by the Home App!**

A link of successfully tried plugins with examples can be found here: https://forum.iobroker.net/viewtopic.php?f=20&t=15021

### Local-Homebridge-Mode
If you want to have a published bridge to be used by the Home App and want to also interact with it from ioBroker and get the data, but do not already have homebridge installed then use this mode.

The Local mode installs the current compatible version of homebridge and runs it as ioBroker user. You provide the complete homebridge configuration using ioBroker. 
The installation of the homebridge modules is also done via ioBroker.

**IMPORTANT: When using child bridges (new homebridge feature since 1.3.x) the adapter CAN NOT access the data provided by these child bridges! Only the main bridge is accessible!**

### Global-Homebridge-Mode
If you already use Homebridge (Apple OpenSource SmartHome) as a global installation on the host where also ioBroker runs on,
then you can use this existing Homebridge installation and start this Homebridge
installation as ioBroker process. **In this case the Homebridge server is started by ioBroker.**

**IMPORTANT: You need to make sure the global service is NOT started by the system or such. ioBroker itself will do the start! See below for best practice setup details.**

**IMPORTANT: Because ioBroker starts the Homebridge also the logging is done by ioBroker. YOu can set the loglevel from the instance to silly to also see all Homebridge logs, else it will be filtered for the important stuff.**

Additionally, all states from Homebridge are available as states in ioBroker and allow to be controlled from ioBroker.

For this to work you need to provide the location of the systems global node-modules folder. For this call **npm root -g**. Additionally, you need to provide the path of the homebridge configuration directory (usually .homebridge in the "users" folder).

**IMPORTANT: ioBroker runs as user "iobroker", but homebridge normally as root or homebridge user (depending on how you installed it). You need to make sure that the homebride "persistance" folder can be accessed by the ioBroker user, else you will see errors that the file can not be saved (which can crash the adapter!)**

**IMPORTANT: When using child bridges (new homebridge feature since 1.3.x) the adapter CAN NOT access the data provided by these child bridges! Only the main bridge is accessible!**

#### Install as Global Bridge details
Thanks to @Anzic23 here some details on how to set up homebridge ideally for global mode:

1. `sudo npm install -g --unsafe-perm homebridge homebridge-config-ui-x`
2. install hb-service (sudo hb-service install --user homebridge) This step is needed to create the necessary files and directories
3. uninstall hb-service (sudo hb-service uninstall)
4. after installing homebridge
```
sudo chmod 777 -R /var/lib/homebridge/
sudo chmod 777 -R /usr/lib/node_modules/homebridge
```
in iobroker
Global Homebridge Path:
/usr/lib/node_modules/homebridge

Global Homebridge Config Directory Path:
/var/lib/homebridge


## Following plugins were tested in Default mode

* homebridge-chamberlain v1.0.1 - plugin for Chamberlain garage door openers with MyQ
* homebridge-doorbird v0.0.4 - Plugin for Doorbird
* homebridge-dyson-link v2.2.2 - Dyson Link devices
* homebridge-edomoticz v2.1.11 - A fully-fledged up-to-date Plugin for Domoticz
* homebridge-Fibaro-HC2 v2.1.5 - Fibaro HomeCenter integration
* homebridge-homee v0.2.4 - A fully-fledged up-to--date Plugin for Homee
* homebridge-ikea-tradfri-gateway v1.0.26 - Tradfri
* homebridge-noolite v0.0.29 - Noolite via USB MTRF-64 or МТRF-64 modules
* homebridge-platform-wemo v1.0.1 - Belkin WeMo Platform plugin
* homebridge-seasons v1.0.1  - A plugin to display the current season of the year.
* homebridge-vera v0.8.2 - VeraLink is an application for Z-Wave accessories from Vera (Node.js 8.11.3)
... and many more

## TODO
* Tests
* More documentation?!
* Test and find out if ESM modules will work in which mode (I expect none)

<!--
	Placeholder for the next version (at the beginning of the line):
	### **WORK IN PROGRESS**
-->

## Changelog

### __WORK IN PROGRESS__
* (Apollon77) Optimize value determination on accessory initialization

### 5.3.1 (2022-09-28)
* (bluefox) Updated GUI packages

### 5.3.0 (2022-09-15)
* (Apollon77) Add option to enable homebridge debug logging

### 5.2.4 (2022-09-15)
* (Apollon77) Prevent crash when accessing a state which is not controllable anymore

### 5.2.3 (2022-09-14)
* (Apollon77) Optimize Accessory processing

### 5.2.2 (2022-09-14)
* (Apollon77) make compatible to more plugins

### 5.2.1 (2022-09-12)
* (Apollon77) make compatible to more plugins

### 5.1.0 (2022-08-17)
* IMPORTANT update homebridge and wrapper to 1.5.0 (latest as of today). IMPORTANT: Requires also homebridge 1.5.x installed when using global mode and local mode will update to 1.5.x too! Check your plugins for updates!

### 5.0.2 (2022-07-20)
* (bluefox) Update tab GUI

### 5.0.1 (2022-06-28)
* (Apollon77) Make sure values are set after objects were created

### 5.0.0 (2022-06-27)
* IMPORTANT update homebridge and wrapper to 1.4.1 (latest as of today). IMPORTANT: Requires also homebridge 1.4.x installed when using global mode and local mode will update to 1.4.x too! Check your plugins for updates!
* (Apollon77) Sync forbidden characters with ioBroker standard - Object IDs might change with this version!
* (Apollon77) Basically allow to specify http URLS as plugins in the main configuration list (not the tab!)
* (Apollon77) Also try to register on external accessories like cameras (experimental)
* (Apollon77) Fix loading issues with the tab

### 4.0.4 (2022-06-07)
* (bluefox) Corrected configuration in dark theme

### 4.0.3 (2022-03-20)
* (bluefox) Update packages

### 4.0.2 (2021-05-08)
* (Apollon77) prevent warnings in js-controller 3.3

### 4.0.1 (2021-03-24)
* (Apollon77) update homebridge and wrapper to 1.3.4 (latest as of today). IMPORTANT: Requires also homebridge 1.3.x installed when using global mode and local mode will update to 1.3.x too! Check your plugins for updates!
* (UncleSamSwiss) Add an experimental version of new plugin selection and configuration tab - TRY IT OUT!
* (Apollon77) IMPORTANT: Configurations in local/global mode with child bridges will NOT work because ioBroker can not access the data on the child bridge processes!

### 3.0.2 (2020-11-29)
* (Apollon77) update homebridge in wrapper to 1.1.6 (latest as of today)

### 3.0.1 (2020-08-08)
* (Apollon77) set a very high limit (again) on allowed accessories and services because irrelevant

### 3.0.0 (2020-08-04)
* (Apollon77) BREAKING: ONLY WORKS WITH HOMEBRIDGE 1.1.x+ AND Node JS >=10.17.0!! Make sure plugins support it AND homebridge is updated to 1.1.x when you use the Global Mode!

### 1.1.2 (2019-07-08)
* (Apollon77) Allow more than 149 accessories in wrapper mode

### 1.1.1 (2019-07-05)
* (Apollon77) Add option to update NPM modules in Admin. Reinstall will happen after saving settings
* (Apollon77) Enhance NPM installation handling
* (Apollon77) Allow to specify special version of homebridge NPM packages using name@version
* (Apollon77) Allow to specify homebridge command line options. They will be added to the command line arguments (Some plugins need that or special features are only available with it)
* (Apollon77) Add "Local" mode that installs an own homebridge and run it as bridge

### 1.0.1 (2019-01-16)
* (SchumyHao) Add Chinese support

### 1.0.0 (WIP)
* (Apollon77) add polling interval to global mode
* (Apollon77) add option to use insecure flag in wrapper mode

### 0.4.5 (2018.08.21)
* (Apollon77) issues fixed

### 0.4.4 (2018.08.07)
* (Apollon77) corrected automatic role determination and bugs fixed

### 0.4.2 (2018.06.25)
* (Apollon77) Fix for global mode

### 0.4.1 (2018.06.21)
* (Apollon77) option to poll values from the plugins added and other optimizations

### 0.3.1 (2018.06.20)
* (kirovilya) Fixed a bug in global mode that values were not reported back to iOS devices

### 0.3.0 (2018.06.20)
* (bluefox) Support of ham plugins was added

### 0.2.6 (2018.06.19)
* (Apollon77) Updates for Homebridge-Wrapper

### 0.2.5 (2018.06.18)
* (Apollon77) Catch all console logs from Homebridge and make available as debug log

### 0.2.4 (2018.06.18)
* (Apollon77) Updates for Homebridge-Wrapper

### 0.2.3 (2018.06.17)
* (Apollon77) Updates for Homebridge-Wrapper

### 0.2.2 (2018.06.17)
* (Bluefox) Fixes for JSON editor in Firefox and Chrome

### 0.2.0/0.2.1 (2018.06.17)
* (Apollon77) Public test version with both modes
* (Bluefox) Admin3

### 0.1.0 (2018.06.09)
* (Apollon77) Update for working mode 1

### 0.0.1 (2018.03.24)
* (kirovilya) initial commit

## License
The MIT License (MIT)

Copyright (c) 2018-2022 Apollon77 <ingo@fischer-ka.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
