# Woodcliff Homebridge

## Setup

* Install [Raspbian OS Image][raspbian-downloads]
* [Enable SSHd][raspbian-ssh] via `raspi-config`
* Install needed apt utilities/dependencies
  ```
  sudo apt-get install -y \
    git \
    dirmngr \
    vim \
    pigpio python-pigpio python3-pigpio
  ```
* Install asdf
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
  $ cd woodcliff-homebridge && asdf install
  ```
* Copy `config.sample.json` to `~/.homebridge/config.json`
* Update `username` and `pin` to actual values

## Misc Notes (incorporate into readme eventually)

Running on boot: https://github.com/nfarina/homebridge/wiki/Running-HomeBridge-on-a-Raspberry-Pi

[raspbian-downloads]: https://www.raspberrypi.org/downloads
[raspbian-ssh]: https://www.raspberrypi.org/documentation/remote-access/ssh