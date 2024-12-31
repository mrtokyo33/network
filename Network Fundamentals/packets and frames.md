# What are Packets and Frames?

Packets and frames are small pieces of data that, when combined, form a larger piece of information or message. However, they are two different concepts in the **OSI model**.

### Frames (Layer 2 - Data Link Layer)
A **frame** operates at **Layer 2**, the **Data Link Layer**, where IP addresses do not exist. Think of a frame as an "envelope within an envelope" when sending data. The first envelope represents the **packet**, which contains the actual data. Once the outer envelope is opened, the inner envelope is revealed, and that's the **frame**.

This process is called **encapsulation**. When discussing **IP addresses**, we're referring to **packets**, and when the encapsulating information is stripped away, we're talking about the **frame** itself.

### Packets (Layer 3 - Network Layer)
**Packets** are efficient units of data for communication across networks. By breaking data into small packets, the network can prevent bottlenecks and improve data transmission speed, as large chunks of data would create congestion.

For example, when loading an image from a website, the image isn't sent in one large chunk; it's divided into smaller packets, which are then reassembled on your computer. The image below illustrates this process, where the cat's picture is split into three packets and reconstructed on the computer.

![cat transfer webserver - computer](./images/TCP%20file%20transfer.png)

### Packet Structure and Headers
Packets have different structures depending on the protocol being used. Networking relies on standards and protocols to ensure smooth data exchange across billions of devices. Without these standards, communication would break down.

Let's consider a packet using **Internet Protocol (IP)**. This type of packet includes several **headers** containing critical information that guides the packet through the network.

Some notable **headers** include:

| Header                | Description |
| ----------------------| ----------- |
| **Time to Live (TTL)** | This field sets an expiry timer for the packet to prevent it from clogging up the network if it fails to reach its destination. |
| **Checksum**           | Provides integrity checking for protocols like TCP/IP. If any data is changed, this value will differ, indicating corruption. |
| **Source Address**     | The IP address of the device sending the packet, so the data knows where to return to. |
| **Destination Address**| The IP address of the device receiving the packet, guiding it to the correct destination. |

These headers ensure that the packet is properly routed, checked for integrity, and handled appropriately as it travels through the network.
