### Lab Machine Instructions

Step-by-step instructions for configuring Windows and Linux Pivot–Target machines in an isolated VMware lab environment, including the required network interfaces, services, and connectivity settings.


# Setup

On the top:

* Press **Edit**
* Press **Virtual Network Editor**

Clear all the network.

### Add Network — VMnet0

* Add Network: `vmnet0`
* Connect to bridge

### Add Network — VMnet2

* Network: `VMnet2`
* Type: `Host-only`
* Subnet IP: `10.10.10.0`
* Subnet Mask: `255.255.255.0`
* DHCP: **UNtick** this `Use (local DHCP service to distribute IP addresses)`

### Add Network — VMnet3

* Network: `VMnet3`
* Type: `Host-only`
* Subnet IP: `10.20.20.0`
* Subnet Mask: `255.255.255.0`
* DHCP: **Untick** this `Use (local DHCP service to distribute IP addresses)`


## Attacker Machine

Set this network: `NAT`

Also Set this network: `Custom/VMnet2`

```bash
sudo dhclient eth1
```


## Linux Pivot

Set two VM adapters:

* Press **Add Network**
* First network: `Custom/VMnet2`
* Second network: `Custom/VMnet3`


## Windows Pivot

Set two VM adapters:

* Press **Add Network**
* First network: `Custom/VMnet2`
* Second Network: `Custom/VMnet3`


## Linux Target

Set the network: `Custom/VMnet3`


## Windows Target

Set the network: `Custom/VMnet3`




# Archiecture
<img width="900" height="500" alt="archietecture" src="https://github.com/user-attachments/assets/7b498728-e7db-4981-b267-ed5aba2ae512" />
