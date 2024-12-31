# User Datagram Protocol (UDP)

The **User Datagram Protocol (UDP)** is a lightweight and stateless protocol used for communicating data between devices.

### Key Characteristics of UDP
Unlike its "brother" **TCP**, UDP:
- Is **stateless**, meaning it does not maintain a constant connection between devices.
- Does not perform processes such as the **Three-Way Handshake** or synchronization between devices.
- Relies on the application (user software) to handle issues like data order or retransmission.  

UDP is commonly used in applications where:
- Data loss is tolerable (e.g., video streaming or voice chat).
- A stable connection is not critical.

---

### Advantages and Disadvantages of UDP
| **Advantages**                                                                                         | **Disadvantages**                                                                                     |
|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| UDP is significantly **faster** than TCP.                                                             | UDP does not guarantee that the data will be received.                                               |
| Allows applications to control the speed of packet transmission, offering greater flexibility.        | Unstable connections can lead to a poor user experience.                                             |
| Does not reserve a continuous connection, reducing system resource usage.                             | No safeguards like data integrity checks or retransmission mechanisms (as seen in TCP).              |

---

### UDP Packet Headers
UDP packets are simpler than TCP packets and contain fewer headers. However, both protocols share some common header fields. The table below highlights these headers:

| **Header**                 | **Description**                                                                                         |
|----------------------------|---------------------------------------------------------------------------------------------------------|
| **Time to Live (TTL)**     | Sets an expiry timer for the packet to prevent it from lingering in the network indefinitely.           |
| **Source Address**         | The IP address of the sending device, so responses know where to return.                               |
| **Destination Address**    | The IP address of the receiving device, indicating where the packet should travel.                     |
| **Source Port**            | The randomly chosen port (0–65535) used by the sender to send the UDP packet.                          |
| **Destination Port**       | The port number of the application/service on the receiving device (e.g., a webserver running on port 80). |
| **Data**                   | Contains the actual payload (e.g., bytes of a file or message) being transmitted.                      |

---

### Connection Process in UDP
Unlike TCP, UDP does not establish a connection or perform acknowledgment processes during data transmission. The stateless nature of UDP means:
- There is **no guarantee** that the data will be received.
- **No acknowledgment messages** are exchanged between the sender and receiver.  

This makes UDP faster but less reliable than TCP.

---

![UDP requests & responses](./images/UDP%20request%20and%20response.png)

UDP’s simplicity and speed make it ideal for applications where performance is prioritized over reliability, such as streaming or real-time communications. However, developers must handle potential issues like lost or unordered packets within their application logic.
