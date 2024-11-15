
if you need to install docker use the following:
```
cd ~/
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

on your home directory run:

```
git clone https://github.com/you55uf/raspquick.git
cd raspquick
docker compose up -d
```


At this stage, the RaspAP application is running and you may access the web interface as you would normally. This will depend on the method you use to access your device, but is usually one of the following:

http://raspberrypi.local
http://10.3.141.1
http://localhost


## Environment Variables
Several environment variables are made available in this docker image to aid in configuration.

| Environment Variable   | Description                                      | Default       |
|------------------------|--------------------------------------------------|---------------|
| RASPAP_SSID            | The SSID name                                    | raspap-webgui |
| RASPAP_SSID_PASS       | The SSID password                                | ChangeMe      |
| RASPAP_COUNTRY         | The SSID country code                            | GB            |
| RASPAP_WEBGUI_USER     | The admin username for the RaspAP user interface | admin         |
| RASPAP_WEBGUI_PASS     | The admin password for the RaspAP user interface | secret        |
| RASPAP_WEBGUI_PORT     | The RaspAP web user interface port               | 80            |

Some further configuration is also possible through the use of the following prefixed environment variables, in the form RASAPAP_\[target]_\[key]

| Environment Variable Prefix | Target File                    |
|-----------------------------|--------------------------------|
| RASPAP_hostapd_             | /etc/hostapd/hostapd.conf      |
| RASPAP_raspap_              | /etc/dnsmasq.d/090_raspap.conf |
| RASPAP_wlan0_               | /etc/dnsmasq.d/090_wlan0.conf  |

For example, `RASPAP_hostapd_driver` would set the `driver` value in `/etc/hostapd/hostapd.conf`
