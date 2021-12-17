# raspberry-pi-shellinabox
Access to ssh terminal on Raspberry pi through web url
Instead of using ssh terminal on putty or powershell to access Raspberry pi, we have another way to control Raspberry pi as a ssh terminal but through a browser.

Whereever you have have a laptop or mobile device which can run a browser and connected to Raspberry pi, you can easily control it through the web browser.

Shellinabox (or Shell in a box) is a web based AJAX terminal emulator to enable remotely control a Linux Server.

## 1. Install shellinabox on Raspberry pi

```bash
sudo apt update
sudo apt-cache search shellinabox
sudo apt install openssl shellinabox
```
## 2. Enable ssl connection by installing openssl
```bash
sudo apt-get install libssl0.9.8 libpam0g openssl
```
## 2. Edit configuration
Actually, all of configuration I leave it default. Pay attention that the listening port is 4200
```bash
vi /etc/default/shellinabox
```
```
# Should shellinaboxd start automatically
SHELLINABOX_DAEMON_START=1

# TCP port that shellinboxd's webserver listens on
SHELLINABOX_PORT=4200

# Parameters that are managed by the system and usually should not need
# changing:
# SHELLINABOX_DATADIR=/var/lib/shellinabox
# SHELLINABOX_USER=shellinabox
# SHELLINABOX_GROUP=shellinabox

# Any optional arguments (e.g. extra service definitions).  Make sure
# that that argument is quoted.
#
#   Beeps are disabled because of reports of the VLC plugin crashing
#   Firefox on Linux/x86_64.
SHELLINABOX_ARGS="--no-beep"
```
