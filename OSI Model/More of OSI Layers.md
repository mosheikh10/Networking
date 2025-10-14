# POV of Sender & Receiver 👀

### 🌐 The OSI Layers (Sender's Perspective)
Layer 7 - Application
- Action: The user initiates a POST request to an HTTP web page.
- Data: The request includes JSON data intended for the HTTPS server.

Layer 6 - Presentation
- Action: The data (JSON) is prepared for transmission.
- Process: Serialise JSON into flat byte data strings. This ensures the data is in a format that can be understood by the receiving application.

Layer 5 - Session
- Action: Preparing to establish a connection.
- Process: A Request to establish a TCP connection is made. This layer also manages sessions, including security protocols like TLS (Transport Layer Security) for HTTPS.

Layer 4 - Transport
- Action: The reliable connection is initiated.
- Process: Sends a SYN request (Synchronization) to the target server's port 443, which is the standard port for HTTPS traffic.

Layer 3 - Network
- Action: Addressing the data for routing across networks.
- Process: The SYN request is put into one or more IP packet(s). The source IP and destination IP addresses are added to the header of the packet(s).

Layer 2 - Data Link Layer
- Action: Preparing the data for local network transmission.
- Process: Each IP packet is encapsulated into a single frame. The source MAC address and destination MAC address are added to the frame.

Layer 1 - Physical
- Action: Converting the data into a physical signal.
- Process: Each frame becomes a string of bits. This bit stream is then converted into a physical signal for transmission:
   - Radio signal (for Wi-Fi)
   - Electrical signal (for Ethernet)
   - Light (for Fibre Optic)
 
### 🌐 The OSI Layers (Receiver's Perspective)
The receiver works its way up the stack, starting from the physical medium and ending at the application.

Layer 1 - Physical
- Action: Receiving the physical signal.
- Process: The radio, electric, or light signal is received and converted back into a digital string of bits.

Layer 2 - Data Link Layer
- Action: Reassembling the data into frames.
- Process: The bits from Layer 1 are assembled into a frame. The receiver checks the MAC address to ensure the frame is intended for it and removes the MAC addresses.

Layer 3 - Network
- Action: Reassembling the frames into packets.
- Process: The frame(s) from Layer 2 are assembled into an IP packet. The receiver checks the destination IP address and removes the IP header information.

Layer 4 - Transport
- Action: Reassembling the packets into segments.
- Process: The IP packets from Layer 3 are assembled into TCP segments. The receiver acknowledges receipt and uses the port number (e.g., 443 for HTTPS) to determine which application (Layer 7) should receive the data.

Layer 5 - Session
- Action: Managing the connection.
- Process: The connection session is established (or maintained). This layer manages the state and security (TLS/SSL decryption) of the communication channel.

Layer 6 - Presentation
- Action: Preparing the data for the application.
- Process: The data is decrypted (since it was HTTPS/TLS) and decompressed (if applicable). The data is then presented to the application in its original format (e.g., JSON).

Layer 7 - Application
- Action: Processing the request.
- Process: The server's application interprets the HTTP request (e.g., sees it is a POST request with JSON data) and processes it accordingly, such as saving data to a database or generating a response.



