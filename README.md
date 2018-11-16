# Woodcliff Homebridge

## Setup

* Install [Raspbian OS Image][raspbian-downloads]
* [Enable WiFi][raspbian-wifi] via `raspi-config`
* [Enable SSHd][raspbian-ssh] via `raspi-config`
* Install needed apt utilities/dependencies
  ```
  sudo apt install -y \
    git \
    dirmngr \
    vim \
    ffmpeg \
    tmux
  ```
* Install [asdf][asdf-vm]
  ```
  $ git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.6.0
  $ echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc
  $ echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc
  $ source ~/.bashrc
  ```
* Install asdf nodejs plugin
  ```
  $ asdf plugin-add nodejs
  $ bash ~/.asdf/plugins/nodejs/bin/import-release-team-keyring
  ```
* Clone this repository
  ```
  $ git clone https://github.com/nickveys/woodcliff-homebridge.git
  ```
* Install Node.js for the project
  ```
  $ cd ~/woodcliff-homebridge && asdf install
  ```
* Install [BCM2835 library][bcm2835-lib]
  ```
  $ cd
  $ wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.57.tar.gz # or latest
  $ tar zxf bcm2835-1.57.tar.gz # or latest
  $ cd bcm2835-*
  $ ./configure
  $ make
  $ sudo make install
  ```
* Install NPM dependencies
  ```
  $ cd ~/woodcliff-homebridge
  $ npm install
  ```
* Copy `config.sample.json` to `~/.homebridge/config.json`
* Update `username` and `pin` to actual values

## Misc Notes (incorporate into readme eventually)

Running on boot: https://github.com/nfarina/homebridge/wiki/Running-HomeBridge-on-a-Raspberry-Pi

[asdf-vm]: https://github.com/asdf-vm/asdf
[bcm2835-lib]: http://www.airspayce.com/mikem/bcm2835
[raspbian-downloads]: https://www.raspberrypi.org/downloads
[raspbian-ssh]: https://www.raspberrypi.org/documentation/remote-access/ssh
[raspbian-wifi]: https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md