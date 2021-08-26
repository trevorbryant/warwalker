Warwalker
=========
A simple little device to war walk around the neighborhood.

Requirements
------------
My hardware configuration consists of:
- [Raspberry Pi 4](https://smile.amazon.com/Vilros-Raspberry-Fan-Cooled-Heavy-Duty-Aluminum/dp/B07XTRK8D4/?th=1)
- [SanDisk 128GB Extreme microSDXC UHS-I](https://smile.amazon.com/gp/product/B07FCMKK5X/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1)
- [GlobalSat BU-353-S4 USB GPS Receiver](https://smile.amazon.com/gp/product/B008200LHW/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1)
- [Panda Wireless PAU09 N600](https://smile.amazon.com/Panda-Wireless-PAU09-Adapter-Antennas/dp/B01LY35HGO/) x2

Instructions
--------------
These instructions assume the user is familiar with building a Raspberry Pi and navigating through a Linux environment.

Follow the instructions below after putting together the Raspberry Pi.

1. Download the [Ubuntu Server 20.04.2 LTS](https://ubuntu.com/download/raspberry-pi) for for Raspberry Pi
2. Use [balenaEtcher](https://www.balena.io/etcher/) (or another tool) to flash the pre-installed OS to the SD card
3. Determine if the device will be administered  or [wireless](https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi#4-boot-ubuntu-server)

Once the device is ready, update the `inventory` file for the IP address or FQDN before executing the playbook.

1. Update the `inventory` file for the IP address or FQDN
2. `ssh` into the device and change the default password `ubuntu:ubuntu`, then exit
3. [Copy an ssh public key](https://linux.die.net/man/1/ssh-copy-id) using the new password
4. Execute the playbook:

```
$ ansible-playbook install.yml -i inventory
```

Update and reboot the device as needed. Kismet server will start on boot and begin capturing networks.
