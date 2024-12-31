# What is the OSI Model?

The **OSI model** (Open Systems Interconnection Model) is a fundamental framework used in networking. This model provides a structured approach to how devices on a network send, receive, and interpret data.

One of the primary benefits of the OSI model is that devices with different functions and designs can communicate with each other on a network. Data sent across a network that adheres to the uniformity of the OSI model can be understood by other devices.

The OSI model consists of **seven layers**, each with specific responsibilities. These layers are illustrated in the diagram below and are arranged from **Layer 7 to Layer 1**.

At each layer, specific processes occur, and pieces of information are added to the data. This process is called **encapsulation**, and the OSI model is visually represented in the diagram below:

![OSI 7 Layers](./images/OSI%20Model/OSI%207%20layers.png)

## Layer 1 (Physical)
![Layer 1 - Physical](./images/OSI%20Model/layer%201.png)

This is the lowest layer, and it handles the physical hardware components used in networking. It involves the transmission of data using electrical signals in a binary format (1's and 0's). Devices such as **Ethernet cables** and network connectors operate at this layer.

## Layer 2 (Data Link)
![Layer 2 - Data Link](./images/OSI%20Model/layer%202.png)

The Data Link Layer is responsible for physical addressing. It receives data from the Network Layer, including the IP address of the remote computer, and adds the MAC (Media Access Control) address of the destination device. Each network device has a unique **MAC address** embedded by the manufacturer, which cannot be changed (though it can be spoofed). The Data Link Layer ensures that data is in a suitable format for transmission.

## Layer 3 (Network)
![Layer 3 - Network](./images/OSI%20Model/layer%203.png)

The Network Layer handles **routing** and the reassembly of data packets. It decides the optimal path for data to travel using protocols like **OSPF** (Open Shortest Path First) and **RIP** (Routing Information Protocol). This layer primarily uses **IP addresses** (e.g., 192.168.1.100) for routing, and devices like **routers** operate at this layer.

## Layer 4 (Transport)
![Layer 4 - Transport](./images/OSI%20Model/layer%204.png)

The Transport Layer is responsible for ensuring data is correctly transmitted between devices. It can use two protocols:

### TCP (Transmission Control Protocol)
- **Advantages**: Guarantees data accuracy, synchronizes devices to avoid overload, and includes error checking.
- **Disadvantages**: Requires a reliable connection, can cause delays due to connection management, and is slower than UDP.

TCP is used for applications that require accuracy, like file transfers, web browsing, or sending emails.

![TCP File Transfer](./images/TCP%20file%20transfer.png)

### UDP (User Datagram Protocol)
- **Advantages**: Much faster than TCP, does not reserve a continuous connection, and allows more flexibility.
- **Disadvantages**: No guarantee that data is received, and an unstable connection can cause a poor user experience.

UDP is ideal for applications like device discovery (ARP and DHCP) and video streaming, where speed is more critical than accuracy.

![UDP File Transfer](./images/UDP%20file%20transfer.png)

## Layer 5 (Session)
![Layer 5 - Session](./images/OSI%20Model/layer%205.png)

The Session Layer manages the communication session between devices. It establishes, maintains, and closes connections as necessary. This layer ensures data is transmitted without interference and can resume from where it left off using "checkpoints."

## Layer 6 (Presentation)
![Layer 6 - Presentation](./images/OSI%20Model/layer%206.png)

The Presentation Layer acts as a **translator** for data between the Application Layer (Layer 7) and the lower layers. It ensures that data is in a standardized format, so the receiving device can understand it, regardless of the software used. It also handles **data encryption** and **compression** (e.g., HTTPS for secure websites).

## Layer 7 (Application)
![Layer 7 - Application](./images/OSI%20Model/layer%207.png)

The **Application Layer** is the layer most familiar to users. It handles user-facing protocols and applications, such as **email clients**, **web browsers**, and **file-sharing software**. This layer is where you interact with the data, often through a **Graphical User Interface (GUI)**. It also includes protocols like **DNS** (Domain Name System), which translates website addresses into IP addresses.

