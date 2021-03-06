# TorBox
TorBox is an easy to use, anonymizing router based on a Raspberry Pi. TorBox creates a separate WiFi that routes the encrypted network data over the Tor network. The type of client (desktop, laptop, tablet, mobile, etc.), and operating system on the client do not matter.

For more information visit the [TorBox website](https://www.torbox.ch)<br />
TorBox Image (about 1.2 GB) : [v.0.3.2 (24.08.2020)](https://www.torbox.ch/data/torbox-20200824-v032.gz) – [SHA-256 values](https://www.torbox.ch/?page_id=1128)<br />
TorBox Menu only : [v.0.3.2 (24.08.2020)](https://www.torbox.ch/data/torbox032-20200824.zip) – [SHA-256 values](https://www.torbox.ch/?page_id=1128)<br />

![What’s it all about?](https://www.torbox.ch/wp-content/uploads/2019/01/TorBox400-e1548096878388.jpg)

### Disclaimer
**Use it at your own risk!**

TorBox is ideal for providing additional protection for the entire data stream up to the Tor network, and for overcoming censorship. However, **anonymity is hard to get – solely using Tor doesn’t guarantee it**. Malware, Cookies, Java, Flash, Javascript and more will most certainly compromise your anonymity. Even the people from the [Tor Project themselves state](https://2019.www.torproject.org/about/overview.html.en#stayinganonymous) that “Tor can’t solve all anonymity problems. It focuses only on protecting the transport of data.” Therefore, **it is strongly advised not to use TorBox, if your well-being depends on your anonymity**. In such a situation it is advisable to use [Tails](https://tails.boum.org/) (read [here](https://browserleaks.com/), [here](https://en.wikipedia.org/wiki/Device_fingerprint) and [here](https://panopticlick.eff.org/about#defend-against) why). [Here](https://www.torbox.ch/?page_id=112#fingerprinting) are additional browser add-ons to improve anonymity, security and/or usability.

### Quick Installation Guide
1. Download the latest TorBox image file and [verify the integrity of the downloaded file](https://www.torbox.ch/?page_id=1128).
2. Transfer the downloaded image file on an [SD Card](https://en.wikipedia.org/wiki/Secure_Digital); for example, with [Etcher](https://www.balena.io/etcher/). TorBox needs at least a 4 GB SD Card, but 8 GB is recommended.
3. Put the SD Card into your Raspberry Pi, link it with an Internet router using an Ethernet cable, or place an USB WiFi adapter in one of the USB ports to use an already existing WiFi. Afterward, start the Raspberry Pi. During the start, the system on the SD card automatically expands over the entire free partition – user interaction, screen, and peripherals are not required.
4. After 2-3 minutes, when the green LED stops to flicker, connect your client to the new WiFi “TorBox032” (password: **CHANGE-IT**). Then use an [SSH-client](https://en.wikipedia.org/wiki/Comparison_of_SSH_clients) to access 192.168.42.1 (username: **torbox** / password: **CHANGE-IT**). Now, you should see the [TorBox main menu](https://www.torbox.ch/?page_id=775). Choose the preferred connection setup, and **change the default passwords as soon as possible** (the associated entries are placed in the [configuration sub-menu](https://www.torbox.ch/?page_id=875)).

A Raspberry Pi 3 ([Model B](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/) / [Model B+](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/)) or a [Raspberry Pi 4 Model B](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/) is recommended.

Do you have additional questions? Check out our [Documentation](https://www.torbox.ch/?page_id=775), our [FAQ on the TorBox website](https://www.torbox.ch/?page_id=112) or [contact us](mailto:anonym@torbox.ch).

![Start-up instructions](https://www.torbox.ch/wp-content/uploads/2020/08/TorBox-A5-RPI4-032.png)

### Features
* TorBox routes all your network data through the Tor network. At the same time, TorBox acts as an external firewall and prevents IP leakage.
* With the SSH-accessible menu, TorBox provides you with a user-friendly interface.
* TorBox supports Internet access via cable (Ethernet), WiFi, tethering devices, [cellular links](https://www.torbox.ch/?page_id=1030), USB dongles (wlan1/eth1/ppp0/usb0), and VPN connections (tun0).
* Clients can connect TorBox via WiFi (in most cases, **an additional USB WiFi adapter is necessary**) and cable (simultaneously; see [here](https://www.torbox.ch/?page_id=775)).
* It easily overcomes captive portals and offers, if necessary, measures against “disconnect when idle features” (sometimes seen with WiFis in airports, hotels, coffee houses).
* TorBox supports [OBFS4](https://2019.www.torproject.org/docs/pluggable-transports.html) bridges, which help to overcome censorship ([with an easy to use interface](https://www.torbox.ch/?page_id=797)).
* If you have a public IP address, 24/7 Internet connectivity over a long time, and a bandwidth of at least 1 Mbps, TorBox can provide a bridge relay, easily configurable via a user-friendly interface [to allow censored users access to the open Internet](https://blog.torproject.org/run-tor-bridges-defend-open-internet).
* It provides [SOCKS v5 proxy functionality](https://en.wikipedia.org/wiki/SOCKS) on the ports 9050 (standard) and 9051 (with [destination address stream isolation](https://tails.boum.org/contribute/design/stream_isolation/)).
* It allows easy access to .onion websites without client configuration (Chrome) or [via SOCKS v5 proxy (Firefox)](https://www.torbox.ch/?page_id=112#SOCKS).

### Alternative installation method with the TorBox installation script
Alternatively, you can download the latest version of [Raspberry Pi OS Lite](https://www.raspberrypi.org/software/operating-systems/), ensure stable Internet connectivity, localize your installation with raspi-config (optional), download and execute our installation script:
```console
cd
wget https://raw.githubusercontent.com/radio24/TorBox/master/install/run_install.sh
chmod a+x run_install.sh
./run_install.sh
```
\
We recommend running TorBox on a Raspberry Pi 3 ([Model B](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/) / [Model B+](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/)) or a [Raspberry Pi 4 Model B](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/) under [Raspberry Pi OS Lite](https://www.raspberrypi.org/software/operating-systems/). However, [there is another installation script](https://www.torbox.ch/?page_id=1168#ubuntu) that installs TorBox on [Ubuntu Server 20.04 LTS (32/64 bit)](https://en.wikipedia.org/wiki/Ubuntu#Official_distributions) and therefore, might run on other hardware platforms (this script is currently in an experimental state).

### Building from scratch
All you need to run TorBox on your Raspberry Pi is the image file. However, if you want to build it from scratch, whether you like to implement it to an existing system, to another hardware, respectively another operating system or you don’t trust an image file, which you didn’t bundle of your own, then check out our detailed manual [for a Raspberry Pi with Raspberry Pi OS Lite](https://www.torbox.ch/?page_id=205) or [for Ubuntu Server 20.04 LTS (32/64 bit)](https://www.torbox.ch/?page_id=1629).

### I want to help...
GREAT! There is a lot to improve and to fix (security of the entire system, graphical menu, cool logos ...). We are searching for people who want to help, and **we need especially your feedback** to improve the system.
You can also [donate to the Tor Project](https://donate.torproject.org) -- without them, TorBox would not exist.

### Contact
* [TorBox website](https://www.torbox.ch)
* [TorBox email](mailto:anonym@torbox.ch)
