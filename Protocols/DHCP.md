# Understanding IP Address Assignment via DHCP

IP addresses can be assigned either **manually**, by physically entering them into a device, or **automatically**, most commonly through a **DHCP (Dynamic Host Configuration Protocol)** server.

## How DHCP Works

When a device connects to a network, if it does not already have a manually assigned IP address, it will send a request to discover any available DHCP servers on the network. This is called a **DHCP Discover** message.

### 1. DHCP Offer

The DHCP server responds to the request with an available IP address that the device can use. This is called a **DHCP Offer**.

### 2. DHCP Request

The device then sends a reply confirming that it wants to use the offered IP address. This is the **DHCP Request**.

### 3. DHCP ACK

Finally, the DHCP server sends an **ACK (acknowledgement)**, confirming that the device can now use the assigned IP address and start communication on the network.

![DHCP diagram](./images/DHCP.png)
