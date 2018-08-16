# Setup Raspbian on a Raspberry
I use a Raspberry for home automation. Because I love automation, I want to have my Rapsberry setup in an automated fashion. Using [ansible](http://ansible.com), I'm able to transform manual steps that need to be repeated many times when setting up devices and systems into automated repeatable and idempotent tasks.

## Testing Ansible playbook
For testing and development, I use [Vagrant](http://vagrantup.com) a lot. Although Vagrant, respectively [VirtualBox](https://www.virtualbox.org) does not support ARM architectures, "cross compiling" to a Debian Jessie running on VirtualBox seems viable to me.

## Install tools and all dependencies
To execute the playbook on each and every Raspberry, simply run
`ansible-playbook -i inventory raspberry.yml`

### deCONZ
Control [zigbee](https://www.dresden-elektronik.de/funktechnik/products/software/pc/deconz/) compatible networks

### HomeKit support
Install [homebridge](https://github.com/nfarina/homebridge) to be able to talk to HomeKit API

### HomeBridge Plugins
* HomeBridge Hue
To be able to control IKEA's [Trådfri](https://www.ikea.com/gb/en/products/lighting/smart-lighting/) devices, I use [HomeBridge Hue](https://www.npmjs.com/package/homebridge-hue)
