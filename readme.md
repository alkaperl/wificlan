# WiFicLAN Wireless Sniffer and Interface

MFA Media Design thesis project:

Web app and user interface for live wifi sniffing and network management built on beaglebone black with nodejs and aircrack-ng. Beaglebone pushes data to firebase, decoded into mongodb, visualized in browser with an interactive d3js duodendrogram.

View live at [tag.impracticalapplications.com](http://tag.impracticalapplications.com/live)

### Requirements

* NodeJS 0.10+
* Airodump 1.1+
* Wifi interface in monitor mode
* (Optional) 2nd wifi interface connected to the internet

### Server
Deploy on an embedded device -- beaglebone, rpi, router -- and gather data through airodump and POST it to an endpoint. This is a total work in progress.

##### Usage

Copy the `server` directory to your device, via `scp` or `sftp` or whatever is easiest. Set your wifi interface in monitor mode. Replace `wlan0` with your interface name:

Run `setup.sh`:
```
sh setup.sh
```

This will execute:
```
sudo ifconfig wlan0 down;sudo iwconfig wlan0 set mode monitor
```

Install npm modules
```
npm install
```

Start app
```
sh start.sh
```


### Client
Front end interface to display airodump data sent to the API by the `server`. Deploy somewhere publically accessible, like a digital ocean or AWS VPS, or heroku. Where ever, it just needs to support node applications. Some web hosting providers don't do that.

##### Usage

Install npm packages
```
npm install
```

Deploy and run the app on your server:
```
sh start-dev.sh
```


### TODO
* Send RSSI signal strength through API
* Execute bash scripts on beaglebone from web button

### Thanks
Thank you to Derek Rushforth.
