# ESP3D-WEBUI 
 ![Build Status](https://travis-ci.org/luc-github/ESP3D-WEBUI.svg?branch=master)   
 
## What is that ?
A web configuration tool for ESP3D
Originaly based on great UI from Jarek Szczepanski (imrahil): [smoothieware-webui](http://imrahil.github.io/smoothieware-webui/) to get a multi firmware support for [Repetier](https://github.com/repetier/Repetier-Firmware), [Repetier for Davinci printer](https://github.com/luc-github/Repetier-Firmware-0.92), [Marlin](https://github.com/MarlinFirmware), [Marlin Kimbra](https://github.com/MagoKimbra/MarlinKimbra) and of course [Smoothieware](https://github.com/Smoothieware/Smoothieware)

## Why doing it ?
Original I ported [smoothieware-webui](http://imrahil.github.io/smoothieware-webui/) to support [ESP3D firmware](https://github.com/luc-github/ESP3D) and it was working pretty well and gave :[smoothieware-webui-for-ESP3D](https://github.com/luc-github/smoothieware-webui-for-ESP3D)   
But this UI has a 2 big limitations:    
1 - you need internet access to get all libraries available to download, which may not happen when ESP is in AP mode for configuration if you do not have all js/css in your browser cache, or if you want to use in local environement, in that case not only ESP AP mode is not displaying UI properly but also STA mode - so it make the ESP useless

2 - it rely on server availability and certificat check, I got several certificat failure for unknown reason that made the UI not working

So the solution was to make all resources available - easy no ?

Yes but...  
ESP webserver is a convenient but it is also a very light webserver, allowing no more than 5 active connections at once and with a pretty limited filesystem space, so even concatenated all resources like bootstrap icon, angular and others libraries do not work as expected and do not fit the available space.

So I came with a full rewrite using pure javascript and resized resources:
1 - a compressed css based on [bootstrap](http://getbootstrap.com/css/) 
2 - a local limited version of svg based of [Glyphicons Halflings](http://glyphicons.com/) to get a small footprint.
3 - a customized version of [smoothiecharts](http://smoothiecharts.org/) is used to display temperatures charts, it is simple and perfectly sized for the current purpose

and the result is a monolitic file with a size less than 70Kb allowing almost full control of ESP3D board and your 3D printer

## Features
- It supports several firmwares based on Repetier, Marlin and Smoothieware.
- It allows to fully configure ESP wifi
- It has a macro support to add custom commands in UI by adding buttons launching some GCODE files from SD or ESP 
- It supports currently English, French, German (thanks @leseaw) and Spanish languages
- It allows to display a web camera in UI or detached
- It allows to edit the Repetier EEPROM and Smoothieware config file
- It allows to update the ESP3D by uploading the FW
- it allows to control and monitor your 3D printer in every aspect (position, temperature, print, SD card content, custom command

Please look at screenshots:
Main tab and menu:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/Full1.PNG'/>   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/Full2.PNG'/>   
Control panel:  
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/controls.PNG'/>  
Macro dialog:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/Macro.PNG'/>   
Temperatures panel:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/temperatures.PNG'/>   
Extruder panel:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/esxtruders.PNG'/>  
SD card panel:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/SD1.PNG'/>  
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/SD1.5.PNG'/>   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/SD2.PNG'/>  
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/SD-Dir.PNG'/>  
Camera Tab:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/Camera.PNG'/>  
Repetier EEPROM Editor tab:  
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/Repetier.PNG'/>  
Smoothieware config Editor tab:  
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/smoothieware.PNG'/>  
ESP3D settings Editor:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/ESP3D1.PNG'/>  
ESP3D Status:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/status.PNG'/>   
ESP3D SPIFFS:   
<img src='https://raw.githubusercontent.com/luc-github/ESP3D-WEBUI/master/images/SPIFFS.PNG'/>   


## Installation
For [ESP3D 1.X](https://github.com/luc-github/ESP3D) Please use the latest [ESP3D-WEBUI 1.X](https://github.com/luc-github/ESP3D-WEBUI/tree/master) and copy the index.html.gz file on root of SPIFFS, in theory ESP3D have a version of web-ui but it may not be the latest one

For [For ESP3D 2.X](https://github.com/luc-github/ESP3D/tree/2.0) Please use the latest [ESP3D-WEBUI 2.X](https://github.com/luc-github/ESP3D-WEBUI/tree/2.0)

## Contribution / development
Check wiki section [Contribution/Development](https://github.com/luc-github/ESP3D-WEBUI/wiki/Compilation---Development)

## Issues / Questions
You can submit ticket [here](https://github.com/luc-github/ESP3D-WEBUI/issues)

## Donate
Every support is welcome: [<img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG_global.gif" border="0" alt="PayPal – The safer, easier way to pay online.">](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=Y8FFE7NA4LJWQ)    
Especially if need to buy new modules for testing.
