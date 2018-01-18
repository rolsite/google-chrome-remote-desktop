# google-chrome-remote-desktop
Install a light Ubuntu Desktop in VPS Low Ram With Google Chrome Remote Desktop

From Ubuntu 16.04 LTS
```
sudo apt-get update
sudo apt-get install lubuntu-core
sudo reboot
sudo apt-get install gdebi firefox
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo gdebi google-chrome-stable_current_amd64.deb
wget http://dl.google.com/linux/direct/chrome-remote-desktop_current_amd64.deb
sudo gdebi chrome-remote-desktop_current_amd64.deb
echo "exec /usr/bin/lxsession -s Lubuntu -e LXDE" > ~/.chrome-remote-desktop-session
sudo groupadd chrome-remote-desktop
sudo usermod -a -G chrome-remote-desktop *user*
echo "CHROME_REMOTE_DESKTOP_DEFAULT_DESKTOP_SIZES=1366x768" > ~/.profile
sudo /etc/init.d/chrome-remote-desktop stop
sudo /etc/init.d/chrome-remote-desktop start
```
