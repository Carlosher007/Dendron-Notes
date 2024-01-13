---
id: m8csxytgrvq84lqd2zs5qcb
title: First Step
desc: ''
updated: 1704648704858
created: 1704643967143
---

- Open a terminal and do this things for not have problems, it's only to have a best temporal experience:
  - Edit → Cursor shape: I-beam 
  - Edit -> terminal bell: desactivate

## Validate to have IP

With the command `hostname -I` you can see your IP, if you don't have IP, you have to configure your network. So **do this things**:

### If you don't have IP

- Write `ifconfig` and make sure in addition to gaving the normal interface we alse have another one, or writting `iwconfig` you can see the wireless interface.
- If the interface is off, you have to turn it on with `sudo ifconfig <interface> up`

If you still don't have the other interface, you can open the cmd in your princripal OS and write `ipconfig` or the similar command for your IP. Then do this:
- Find the IPv4 direction and the network mask. The idea is working with the same subnetwork. So, if you **Ipv4 direction is 192.168.1.39** while we have in the **192.168.1.anything** we would be fine.
- So take in mind that in this case we ipv4 direction is _192.168.1.39_ and the network mask is _255.255.255.0_.
- In the parrot, write `sudo ifconfig <interface> 192.168.1.12`. And then, `sudo ifconfig <interface> 192.168.1.212 netmask 255.255.255.0` (if you already have the interface, you can skip the first command).
- Lastly, we have to see in our system (not parrot) what is the ip of the Default Gateway. Imagine that is _192.168.1.1_.
- In our parrot write `sudo route add default gw 198.168.1.1`. If with this, show you "the red is inaccesible", is because this ip is already in use or you already have and ip from the beginning.

## Continue with the installation

We have to validate that we have internet connection. So, write ``ping -c 1 8.8.8.8` and write `ping -c 1 google.com`. If you have a response, you have internet connection. If the last one doesn't work, you have to do this:

- Write `sudo nano /etc/resolv.conf` and in **nameserver** you have to put `8.8.8.8`, and in the another **nameserver** put `1.1.1.1`. Now, the ping should work

## To resume
In case you have problems with the red and the machine doesnt assign you an IP, you can on the hand one to execute:
- `ifconfig tuInterfaz up`
- `ifconfig tuInterfaz ipDeseada netmask 255.255.255.0`
- `route add default gw ipGateway`

In the case you wanr to configure a static IP in order to no have to apply this instructions every time you start the machine, you can create a file in `/etc/network/interfaces` as a **root** the following content:

  ```bash
  auto <interface>
  iface <interface> inet static
      address 192.168.1.150
      netmask 255.255.255.0
      gateway 192.168.1.1
      dns-nameservers 8.8.8.8
  ```
  Rememeber that is necessary ajust the interface name, the ip directions that you want to assign and the gateway ip direction.

Now, go to the next step [[study.my-self.linux.linux-personalization.personalization.installing-bspwm-sxhkd]]

