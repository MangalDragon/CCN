# Computer Communication Networks — Modules 1–3 Question-Bank Answer Bank

**Course:** ECE23701  
**Coverage:** All 31 questions in `Question_Bank.pdf`  
**Primary sources:** `Module1_Reference_PPT.pptx`, `Module2_Reference_PPT.pptx`, and `Module3_Reference_PPT.pptx`  
**Diagram copies:** Each `_rendered.pdf` page number is identical to its corresponding PPT slide number.

## Exam-writing instructions

1. Begin with the definition or direct answer.
2. Use numbered points and underline protocol names, field names, formulas, and final results.
3. Reproduce the supplied text diagram, or copy the clearer source diagram from the cited PPT slide/PDF page.
4. For numericals, write the formula, substitution with units, calculation, and boxed result.
5. Where a source slide contains an inconsistency, this answer bank uses the independently verified networking result.

---

# Module 1 — Data Communications and Network Models

## M1-Q1. The five components involved in data communication along suitable example along with its characteristics.

### Definition

A data-communication system is the exchange of data between two or more devices through a transmission medium according to an agreed set of rules.

### Five components of data communication

1. **Message**
   - The message is the information or data that must be communicated.
   - It may be text, numbers, images, audio, video, or a combination of these.

2. **Sender**
   - The sender is the device that originates and transmits the message.
   - Examples include a computer, workstation, telephone, camera, or mobile phone.

3. **Receiver**
   - The receiver is the device that accepts the transmitted message.
   - Examples include a computer, television, telephone, or another mobile phone.

4. **Transmission medium**
   - It is the physical or wireless path through which the message travels.
   - Examples include twisted-pair cable, coaxial cable, optical fibre, microwave, and radio waves.

5. **Protocol**
   - A protocol is a set of rules governing communication between devices.
   - It specifies matters such as data format, addressing, transmission timing, error handling, and interpretation of messages.
   - Two devices may be physically connected but cannot communicate correctly without compatible protocols.

### Example

```text
Mobile Phone A
     |
     |  Message: text, image, audio, or video
     v
Wi-Fi / Cellular Network / Internet
     |
     v
Mobile Phone B
```

- **Sender:** Mobile Phone A  
- **Message:** Text message or photograph  
- **Transmission medium:** Wi-Fi, cellular radio, and fibre links  
- **Receiver:** Mobile Phone B  
- **Protocol:** TCP/IP, cellular protocols, and application protocols such as HTTPS  

### Characteristics of an effective data-communication system

1. **Delivery**
   - Data must reach the correct destination.
   - It should be delivered only to the intended device or user.

2. **Accuracy**
   - Data must be delivered without undetected alteration, loss, or corruption.
   - Corrupted data that is not corrected or detected is generally unusable.

3. **Timeliness**
   - Data must arrive within the required time.
   - This is especially important in real-time voice and video communication.

4. **Jitter**
   - Jitter is the variation in packet-arrival time.
   - Excessive jitter causes uneven audio or video playback.
   - For example, if successive video packets are expected every 30 ms but arrive with varying delays of 30 ms, 40 ms, and 25 ms, the resulting playback may be distorted.

**Citation:** Module1_Reference_PPT, slide 1 (rendered PDF page 1)

---

## M1-Q2. The various methods of data representation used in data communication.

Data communicated through a network is represented internally as binary information. Depending on the type of information, different representation methods are used.

### 1. Text representation

1. Text is represented using binary codes.
2. Each character is assigned a unique binary code.
3. Common character-coding schemes include:
   - **ASCII:** Traditionally uses 7 bits, commonly stored using 8 bits.
   - **Unicode:** Supports characters and symbols from most of the world's writing systems.
4. The same coding scheme must be understood by both the sender and receiver.

**Example:**

```text
Character: A
Binary code: 01000001  (ASCII)
```

### 2. Number representation

1. Numbers are represented in binary form using 0s and 1s.
2. Computers represent both:
   - Integers
   - Floating-point numbers
3. The representation is different from text representation. For example, a numeric value should not be confused with the character string containing its digits.

**Example:**

```text
Decimal 25 = Binary 11001
```

### 3. Image representation

1. An image is represented as a two-dimensional array of pixels.
2. Each pixel is assigned a binary pattern representing its colour or intensity.
3. Colour images are commonly represented using components such as:
   - Red, Green, and Blue (RGB)
   - Cyan, Magenta, and Yellow (CMY/CMYK)
4. Increasing the number of pixels improves spatial resolution but also increases storage and transmission requirements.

```text
Image
+----+----+----+
| p1 | p2 | p3 |
+----+----+----+
| p4 | p5 | p6 |
+----+----+----+
```

### 4. Audio representation

1. Audio is naturally a continuous signal.
2. To transmit it digitally, the analogue sound wave is sampled at regular intervals.
3. Each sample is converted into a digital value using an analogue-to-digital converter (ADC).
4. A higher sampling rate and greater sample precision improve quality but require a higher bit rate.

```text
Analogue sound → Sampling → Quantization → Binary audio data
```

### 5. Video representation

1. Video is a sequence of still images called frames displayed rapidly.
2. Each frame is represented in the same manner as a digital image.
3. Audio associated with the video is represented separately.
4. Compression is normally used to reduce the storage and transmission requirements.
5. Video may be generated continuously by a camera or constructed from a sequence of discrete images.

```text
Frame 1 → Frame 2 → Frame 3 → Frame 4 → Moving video
```

**Citation:** Module1_Reference_PPT, slide 2 (rendered PDF page 2)

---

## M1-Q3. Different modes of data flow with suitable examples.

Data-flow mode specifies the direction in which data can travel between two communicating devices.

### 1. Simplex mode

In simplex communication, data travels in only one direction.

```text
Device A  -------------------->  Device B
          Data flow only
```

#### Characteristics

1. One device can only transmit.
2. The other device can only receive.
3. The entire channel capacity can be used in the single direction.
4. No reverse communication is possible through the same connection.

#### Examples

- Keyboard to computer
- Traditional computer monitor
- Television broadcasting
- Radio broadcasting

### 2. Half-duplex mode

In half-duplex communication, both devices can transmit and receive, but not simultaneously.

```text
Time 1:  Device A  ------------>  Device B
Time 2:  Device A  <------------  Device B
```

#### Characteristics

1. Both stations can transmit and receive.
2. Only one station transmits at a time.
3. The channel capacity is used by whichever station is transmitting.
4. A turn-taking or control mechanism may be needed.

#### Examples

- Walkie-talkies
- Citizens-band radio
- Shared wireless communication systems

### 3. Full-duplex mode

In full-duplex communication, both devices can transmit and receive simultaneously.

```text
Device A  =====================>  Device B
Device A  <=====================  Device B
```

#### Characteristics

1. Transmission occurs in both directions at the same time.
2. The channel may use:
   - Two physically separate paths, or
   - One medium whose capacity is divided between the two directions.
3. It provides better interaction and lower waiting time than half-duplex communication.
4. The available capacity is shared between the two directions when a single medium is used.

#### Example

- Telephone communication
- Modern switched Ethernet
- Video-conferencing communication

### Comparison

| Feature | Simplex | Half-duplex | Full-duplex |
|---|---|---|---|
| Direction | One-way | Two-way, one direction at a time | Two-way simultaneously |
| Simultaneous transmission | Not applicable | No | Yes |
| Channel use | Entire capacity in one direction | Entire capacity assigned to current sender | Capacity divided or separate paths |
| Example | Keyboard-to-computer | Walkie-talkie | Telephone |

**Citation:** Module1_Reference_PPT, slide 3 (rendered PDF page 3)

---

## M1-Q4. The physical structures and network criteria parameters of computer networks.

A computer network consists of two or more devices connected through communication links. The physical structure describes how devices are connected to the links, while network criteria describe how well the network operates.

## A. Types of physical connection

### 1. Point-to-point connection

A point-to-point connection provides a dedicated link between exactly two devices.

```text
Device A  ====================  Device B
             Dedicated link
```

#### Characteristics

1. The complete capacity of the link is reserved for the two devices.
2. Data is not directly shared with other devices on that link.
3. It may use copper cable, optical fibre, microwave, infrared, or satellite communication.
4. It is generally simple to manage and provides predictable link performance.

**Example:** A dedicated link between two routers or an infrared remote control communicating with a television.

### 2. Multipoint connection

A multipoint, or multidrop, connection allows more than two devices to share one link.

```text
             Device B
                 |
Device A --------+-------- Device C
                 |
             Device D
             Shared link
```

#### Characteristics

1. The link capacity is shared among multiple devices.
2. Sharing may be:
   - **Spatially shared:** More than one device can use different portions of the medium at the same time.
   - **Timeshared:** Devices take turns using the link.
3. Access-control rules are usually required to prevent simultaneous transmissions from interfering with one another.
4. It can reduce cabling cost compared with separate point-to-point links.

## B. Network criteria

### 1. Performance

Performance indicates how effectively the network transfers data.

It may be measured using:

- **Transit time:** Time required for a message to travel from source to destination.
- **Response time:** Time between an inquiry and the corresponding response.
- **Throughput:** Actual amount of successfully delivered data per unit time.
- **Delay:** Total time taken by a packet to travel from source to destination.

A network generally aims for high throughput and low delay. However, sending more traffic may increase throughput while also increasing congestion and delay.

### 2. Reliability

Reliability indicates the ability of the network to operate correctly and recover from failures.

It is evaluated using:

1. Frequency of failures.
2. Time required to recover from a failure.
3. Robustness during equipment, link, or catastrophic failures.
4. Accuracy and continuity of data delivery.

### 3. Security

Security protects network resources and data from unauthorized actions.

Important objectives include:

1. Preventing unauthorized access.
2. Protecting data from alteration, destruction, or loss.
3. Preserving confidentiality and integrity.
4. Using policies and recovery procedures after security breaches.

**Citation:** Module1_Reference_PPT, slides 4–5 (rendered PDF pages 4–5)

---

## M1-Q5. Different network topologies with advantage and disadvantages of each topology.

Network topology is the arrangement of network devices and links. The following are the principal **physical topologies**.

## 1. Mesh topology

In a full mesh, every device has a dedicated point-to-point link to every other device.

```text
       A
      /|\\
     / | \\
    B--+--C
     \\ | /
      \\|/
       D
```

For four devices, the six dedicated links are `AB`, `AC`, `AD`, `BC`, `BD`, and `CD`; the centre crossing in the sketch is not a device.

For `n` devices, the number of full-duplex links is:

```text
Number of links = n(n − 1) / 2
```

### Advantages

1. Provides dedicated links and high privacy.
2. Failure of one link normally affects only the two devices using that link.
3. Multiple paths provide high reliability and fault tolerance.
4. Dedicated links can provide good performance.

### Disadvantages

1. Requires a large number of cables and ports.
2. Installation cost is high.
3. Configuration and maintenance are difficult as the network grows.
4. Adding a device requires several additional links.

## 2. Star topology

Each device has a dedicated link to a central hub or switch.

```text
             A
             |
      B ---- SW ---- C
             |
             D
```

### Advantages

1. Easier and less expensive to install than a full mesh.
2. Each device requires only one link and one network interface.
3. Failure of one individual link generally affects only its attached device.
4. Fault detection and isolation are comparatively easy.
5. Adding or removing a device is simple.

### Disadvantages

1. The central hub or switch is a critical point of failure.
2. Failure of the central device can stop communication for the entire network.
3. It may require more cabling than a bus topology.
4. Communication between two end devices normally passes through the central device.

## 3. Bus topology

All devices share one common backbone cable.

```text
Terminator --+------ +------ +------ Terminator
             |       |       |
             A       B       C
          Drop lines to common bus
```

### Advantages

1. Simple and relatively inexpensive to install.
2. Requires less cable than star or mesh topologies.
3. Suitable for small or temporary networks.
4. No central switching device is required.

### Disadvantages

1. Failure of the backbone may disable the whole network.
2. Collisions can occur when multiple devices transmit simultaneously.
3. Performance decreases as the number of devices and traffic load increase.
4. Fault detection can be difficult.
5. Adding devices may require interruption of the backbone.

## 4. Ring topology

Each device is connected to two neighbouring devices, forming a closed loop. In a basic ring, the signal normally travels in one direction, and each device acts as a repeater before forwarding it to the next device.

```text
       A -------- B
       |          |
       D -------- C
       Data normally travels around the ring
```

### Advantages

1. Each device has connections only to its immediate neighbours.
2. Installation and reconfiguration are relatively systematic.
3. Controlled access, such as token passing, can avoid collisions.
4. Fault location can be easier because devices follow a definite sequence.

### Disadvantages

1. A single link or device failure can interrupt the ring.
2. Adding or removing a device may temporarily disrupt operation.
3. Data may need to pass through several intermediate devices.
4. A dual ring or bypass mechanism may be required for improved fault tolerance.

### Summary table

| Topology | Main structure | Major advantage | Major disadvantage |
|---|---|---|---|
| Mesh | Every device connected to every other device | Very reliable | Very costly and complex |
| Star | Devices connected to a central device | Easy management and expansion | Central-device failure |
| Bus | Devices share a backbone | Low cabling cost | Backbone failure and collisions |
| Ring | Devices form a closed loop | Predictable controlled access | Link/device failure can break ring |

**Citation:** Module1_Reference_PPT, slides 6–7 (rendered PDF pages 6–7)

---

## M1-Q6. Circuit switched and packet switched network in data communication.

Switching is the process of forwarding data from an incoming link to an appropriate outgoing link. The two important forms are circuit switching and packet switching.

## A. Circuit-switched network

A circuit-switched network establishes a dedicated path between the sender and receiver before data transfer begins.

```text
Source
  |
  v
[S1] ===== [S2] ===== [S3]
                         |
                         v
                      Destination
       Dedicated circuit reserved throughout communication
```

### Phases of circuit switching

1. **Connection establishment**
   - A path is selected between the two end systems.
   - Resources such as link capacity and switch connections are reserved.

2. **Data transfer**
   - Data flows continuously through the established path.
   - The path normally remains unchanged during the communication session.

3. **Connection release**
   - The circuit is disconnected after communication ends.
   - Reserved resources are returned to the network.

### Advantages

1. Provides a fixed path and predictable service.
2. Once established, data transfer has little or no per-packet routing overhead.
3. Suitable for continuous traffic such as traditional voice calls.
4. Data generally arrives in sequence.

### Disadvantages

1. Setup time is required before data can be sent.
2. Reserved capacity cannot be efficiently used by others, even during silence.
3. It is inefficient for bursty computer data.
4. A circuit may remain partly or completely idle while resources are unavailable to other users.
5. A failure in the path can terminate the connection.

## B. Packet-switched network

In a packet-switched network, a message is divided into packets. Each packet is forwarded using shared network resources.

```text
                 +----[R2]----+
P1, P3: Source--[R1]          [R4]--Destination: reorder P1,P2,P3
                 +----[R3]----+
P2 path:       Source--[R1]--[R3]--[R4]--Destination

Each router stores a packet in a queue, then forwards it over the selected shared link.
Different packets may follow different paths.
```

### Operation

1. The sender divides the message into packets.
2. Each packet contains control information such as:
   - Source address
   - Destination address
   - Sequence or packet number
   - Payload data
3. Packets are stored temporarily in router queues and forwarded.
4. Packets may follow the same or different routes.
5. The receiver reorders and reassembles the packets.

### Advantages

1. Network resources are shared efficiently.
2. No dedicated circuit or setup is necessary for basic datagram delivery.
3. It is well suited to bursty computer communication.
4. Many users can share the same links.
5. A packet may be rerouted around a failed or congested path.

### Disadvantages

1. Packets may experience variable delay and queuing.
2. Packets can be lost, duplicated, or delivered out of order.
3. Additional protocols may be needed for reliability and reassembly.
4. Congestion can significantly reduce performance.

### Comparison

| Feature | Circuit switching | Packet switching |
|---|---|---|
| Resource allocation | Dedicated resources | Shared resources |
| Setup | Required | Usually not required for datagram service |
| Data unit | Continuous stream | Packets |
| Delay | More predictable after setup | Variable due to queuing |
| Efficiency | Good for continuous traffic | Good for bursty traffic |
| Failure handling | Circuit may fail | Packets may be rerouted |
| Example | Traditional telephone network | Internet |

**Citation:** Module1_Reference_PPT, slides 9–10 (rendered PDF pages 9–10)

---

## M1-Q7. The layered architecture of the TCP/IP protocol suite and the functions of each layer.

TCP/IP is a hierarchical protocol suite used for communication over the Internet. The commonly used conceptual TCP/IP architecture has five layers.

```text
+-----------------------------+
| 5. Application              |
+-----------------------------+
| 4. Transport                |
+-----------------------------+
| 3. Network / Internet       |
+-----------------------------+
| 2. Data Link                |
+-----------------------------+
| 1. Physical                 |
+-----------------------------+
```

## 1. Physical layer

The physical layer carries individual bits across a physical link.

### Functions

1. Converts bits into electrical, optical, or radio signals.
2. Defines hardware and interface specifications.
3. Specifies encoding and signalling.
4. Defines data rate and bit duration.
5. Provides bit synchronization between sender and receiver.
6. Specifies physical media, connectors, and transmission characteristics.
7. Defines line configuration and transmission mode.

### Examples

- Ethernet physical media
- Optical-fibre signalling
- RS-232 interfaces
- Radio transmission

## 2. Data-link layer

The data-link layer provides node-to-node delivery across a single link.

### Functions

1. Encapsulates network-layer datagrams into frames.
2. Performs framing and frame synchronization.
3. Uses link-layer or MAC addresses.
4. Controls access to a shared medium.
5. Detects transmission errors and may provide error recovery.
6. May provide link-level flow control.
7. Delivers a frame across a local wired or wireless link.

### Examples

- Ethernet MAC
- Wi-Fi MAC
- Point-to-point link protocols

## 3. Network or Internet layer

The network layer provides host-to-host delivery across interconnected networks.

### Functions

1. Provides logical addressing using IP addresses.
2. Packetizes data into network-layer datagrams.
3. Determines routes between source and destination.
4. Forwards packets through intermediate routers.
5. Supports internetworking across different physical networks.
6. Handles fragmentation where required by the network technology.
7. Supports unicast and multicast delivery.

The core protocol is IP. IP itself is connectionless and does not inherently guarantee delivery, flow control, or congestion control.

### Examples

- IPv4
- IPv6
- ICMP
- Routing protocols

## 4. Transport layer

The transport layer provides process-to-process communication between applications on different hosts.

### Functions

1. Segments application messages and reassembles them.
2. Uses port numbers to identify source and destination applications.
3. Provides end-to-end delivery.
4. TCP provides:
   - Connection establishment
   - Reliable delivery
   - Error control
   - Flow control
   - Congestion control
5. UDP provides a lightweight connectionless service with low overhead.
6. SCTP supports additional transport applications and message-oriented services.

### Examples

- TCP
- UDP
- SCTP

## 5. Application layer

The application layer provides network services directly to user applications and processes.

### Functions

1. Supports web communication.
2. Provides file-transfer services.
3. Supports electronic mail.
4. Provides remote login and remote-access services.
5. Provides name and directory services.
6. Supports network management.
7. Defines application-level data formats and exchanges.

### Examples

| Protocol | Main use |
|---|---|
| HTTP/HTTPS | Web access |
| FTP | File transfer |
| SMTP | E-mail transfer |
| DNS | Name resolution |
| SSH | Secure remote access |
| SNMP | Network management |

### Participation of intermediate devices

```text
Source host       Router             Destination host
Application       —                  Application
Transport         —                  Transport
Network           Network            Network
Data Link         Data Link          Data Link
Physical          Physical           Physical
```

- End hosts implement all five layers.
- A router normally implements the physical, data-link, and network layers.
- A link-layer switch normally implements the physical and data-link layers.

**Citation:** Module1_Reference_PPT, slides 17–20 (rendered PDF pages 17–20)

---

## M1-Q8. The concepts of encapsulation and decapsulation in the TCP/IP protocol suite with suitable illustrations.

Encapsulation is the addition of layer-specific control information as data moves down the protocol stack at the sender. Decapsulation is the removal and processing of that information as data moves up the stack at the receiver.

## A. Encapsulation at the source host

```text
Application layer
        Message
          |
          v
Transport layer
   Transport header + message
        Segment / UDP user datagram
          |
          v
Network layer
   Network header + segment
        IP datagram
          |
          v
Data-link layer
   Link header + datagram + trailer
        Frame
          |
          v
Physical layer
        Bits/signals
```

### Step-by-step process

1. The application creates the original message.
2. The transport layer treats the message as its payload and adds a transport header.
   - The header includes port numbers and transport-control information.
   - The result is a TCP segment or UDP user datagram.
3. The network layer adds an IP header.
   - It includes source and destination logical addresses and other network-layer information.
   - The result is an IP datagram.
4. The data-link layer adds a frame header and usually a trailer.
   - The header contains link-layer addresses.
   - The trailer may contain an error-detection value.
   - The result is a frame.
5. The physical layer converts the frame into bits and transmits signals through the medium.

## B. Decapsulation at the destination host

```text
Received bits/signals
      |
      v
Physical layer
      |
      v
Data-link layer: received frame
      |
      v
Network layer: IP datagram
      |
      v
Transport layer: segment/user datagram
      |
      v
Application layer: message
```

At each receiving layer, the protocol data unit is examined and its control information is processed. The layer removes its own header and any applicable trailer, then passes the payload upward. The physical layer only converts received signals and bits; it does not remove a protocol header or trailer.

## C. Router operation

A router performs both decapsulation and re-encapsulation.

```text
Incoming frame
      |
      v
Remove old link-layer header/trailer
      |
      v
Inspect IP datagram and forwarding table
      |
      v
Add new link-layer header/trailer
      |
      v
Outgoing frame on next link
```

1. The incoming frame is processed by the data-link layer.
2. The IP datagram is extracted and passed to the network layer.
3. The router examines the destination IP address and selects the next hop.
4. The IP datagram is normally retained, except for required network-layer operations such as fragmentation.
5. A new frame appropriate for the outgoing link is created.
6. The new frame is transmitted through the physical layer.

### Encapsulation and decapsulation comparison

| Aspect | Encapsulation | Decapsulation |
|---|---|---|
| Location | Sender, and outgoing side of a router | Receiver, and incoming side of a router |
| Direction | Higher layer to lower layer | Lower layer to higher layer |
| Main action | Adds headers and trailers | Removes and processes headers and trailers |
| Result | Data becomes a protocol data unit at each layer | Original application message is recovered |
| Example sequence | Message → Segment → Datagram → Frame → Bits | Bits → Frame → Datagram → Segment → Message |

**Citation:** Module1_Reference_PPT, slide 21 (rendered PDF page 21)

---

## M1-Q9. The OSI reference model and describe the functions of each layer.

The Open Systems Interconnection (OSI) reference model divides network communication into seven logically related layers.

```text
+-----------------------------+
| 7. Application              |
+-----------------------------+
| 6. Presentation             |
+-----------------------------+
| 5. Session                  |
+-----------------------------+
| 4. Transport                |
+-----------------------------+
| 3. Network                  |
+-----------------------------+
| 2. Data Link                |
+-----------------------------+
| 1. Physical                 |
+-----------------------------+
```

## 1. Physical layer

The physical layer transmits raw bits over the communication medium.

### Functions

1. Defines electrical, mechanical, and physical characteristics.
2. Converts bits into electrical, optical, or radio signals.
3. Specifies cables, connectors, interfaces, and media.
4. Defines data rate and signal representation.
5. Establishes, maintains, and terminates physical connections.

### Examples

- Copper Ethernet cable
- Optical fibre
- Radio signals

## 2. Data-link layer

The data-link layer provides reliable or controlled node-to-node delivery over a single link.

### Functions

1. Divides data into frames.
2. Adds physical or MAC addresses.
3. Detects transmission errors.
4. Controls access to a shared communication medium.
5. May provide flow control and link-level error recovery.

### Examples

- Ethernet
- Wi-Fi MAC

## 3. Network layer

The network layer delivers packets from the source network to the destination network.

### Functions

1. Provides logical addressing, such as IP addresses.
2. Determines suitable paths through the internetwork.
3. Performs routing and forwarding.
4. Performs packetization and fragmentation when required.
5. Supports internetwork communication between different networks.

### Example

- IP and router-based forwarding

## 4. Transport layer

The transport layer provides end-to-end communication between processes on different devices.

### Functions

1. Segments data and reassembles it at the destination.
2. Provides process-to-process delivery.
3. Uses port numbers to identify applications.
4. Provides flow control.
5. Provides error control and reliable delivery when required.
6. May provide connection management and congestion control.

### Examples

- TCP
- UDP

## 5. Session layer

The session layer establishes, manages, synchronizes, and terminates communication sessions between applications.

### Functions

1. Establishes a session before data exchange.
2. Maintains and manages the session.
3. Controls the dialogue between communicating systems.
4. Provides synchronization points or checkpoints.
5. Supports recovery from interruptions.
6. Terminates the session after communication is complete.

## 6. Presentation layer

The presentation layer ensures that data sent by one system is understood by another system.

### Functions

1. **Translation:** Converts between data formats and character encodings.
2. **Encryption and decryption:** Provides data confidentiality.
3. **Compression and decompression:** Reduces and restores data size.
4. **Data formatting:** Defines how information is represented.

### Examples

- ASCII and Unicode conversion
- JPEG and MPEG formats
- Encryption formats

## 7. Application layer

The application layer provides network services to end-user applications.

### Functions

1. Supports web communication.
2. Enables file transfer.
3. Supports e-mail services.
4. Provides name and directory services.
5. Supports remote access and resource sharing.
6. Acts as an interface between applications and the network.

### Examples

- HTTP/HTTPS
- FTP
- SMTP
- DNS

### Layer summary

| Layer | Main responsibility | Typical data unit or example |
|---|---|---|
| Application | Services for user applications | HTTP, FTP, DNS |
| Presentation | Translation, encryption, compression | JPEG, Unicode |
| Session | Session and dialogue management | Session/checkpoint |
| Transport | End-to-end process delivery | Segment, TCP, UDP |
| Network | Logical addressing and routing | Packet/datagram, IP |
| Data Link | Framing and node-to-node delivery | Frame, Ethernet |
| Physical | Bit transmission and signalling | Bits, cable, radio |

**Citation:** Module1_Reference_PPT, slides 23–25 (rendered PDF pages 23–25)

---

## M1-Q10. Differentiate between OSI and TCP/IP model in data communication network.

The OSI model is a general reference model developed by ISO, whereas TCP/IP is a practical protocol architecture developed around the Internet protocol suite.

### Layer relationship

```text
OSI model                 TCP/IP five-layer model

Application       ┐
Presentation      ├──>    Application
Session           ┘

Transport         ───>    Transport

Network           ───>    Network / Internet

Data Link         ┐
Physical          ┘──>    Data Link + Physical
```

### Comparison

| Basis | OSI model | TCP/IP model |
|---|---|---|
| Full form | Open Systems Interconnection | Transmission Control Protocol / Internet Protocol |
| Developed by | ISO | DARPA/DoD and the Internet research community |
| Purpose | General reference and teaching model | Practical architecture for Internet communication |
| Number of layers | Seven | Commonly represented as five; some descriptions use four |
| Layers | Physical, Data Link, Network, Transport, Session, Presentation, Application | Physical, Data Link, Network/Internet, Transport, Application |
| Session and Presentation | Separate layers | Their functions are generally included in the Application layer |
| Physical and Data Link | Separate layers | Often combined as a single Network Access layer in the four-layer representation; separated in the five-layer model |
| Network service | Model allows discussion of connection-oriented and connectionless services | IP primarily provides a connectionless network-layer service |
| Transport protocols | Defines transport-layer functions without being tied to one protocol suite | Uses protocols such as TCP and UDP |
| Protocol dependence | Protocol-independent reference model | Closely associated with the TCP/IP protocol suite |
| Development sequence | Model was specified before many protocols | Protocols existed first; the architecture was refined around them |
| Practical use | Useful for conceptual analysis and education | Widely used in real-world Internet and network communication |
| Examples | Conceptual placement of Ethernet, IP, and TCP | Ethernet/Wi-Fi, IP, TCP/UDP, HTTP, DNS |

### Important observations

1. The OSI model has finer separation of functions because it has distinct Session and Presentation layers.
2. TCP/IP combines several OSI functions to keep the architecture practical.
3. In the five-layer TCP/IP model, Physical and Data Link remain distinct for clarity.
4. In the traditional four-layer TCP/IP model, these two layers are combined into the Network Access layer.
5. Neither model should be treated as a literal description of every modern protocol implementation; they are architectural models used to organize communication functions.

**Citation:** Module1_Reference_PPT, slides 17 and 26 (rendered PDF pages 17 and 26)

---

## M1-Q11. The addressing mechanism used in the TCP/IP protocol suite and the concepts of multiplexing and demultiplexing.

TCP/IP uses different addresses at different layers because communication must identify an application, a host, a network interface, and sometimes a human-readable service or resource.

## A. Addressing mechanisms

The physical layer transmits bits and normally does not require an address. Four important address types are therefore used.

### 1. Specific address

A specific address identifies a service, resource, user, or application in a human-readable form.

- It is used at the application level.
- It may identify a website, domain, e-mail account, or URL.
- DNS can translate a domain name into an IP address.

**Examples:**

```text
Domain name:  www.example.com
E-mail:       student@example.com
URL:          https://www.example.com
```

### 2. Port address

A port address identifies a particular application or process on a host.

- It operates at the transport layer.
- It enables process-to-process delivery.
- Port numbers range from 0 to 65,535.
- Well-known services use standard port numbers.

| Application/service | Typical port |
|---|---:|
| HTTP | 80 |
| HTTPS | 443 |
| FTP control | 21 |
| DNS | 53 |

### 3. Logical address

A logical address identifies a host or interface across interconnected networks.

- It operates at the network layer.
- It is commonly called an IP address.
- IPv4 uses 32-bit addresses.
- IPv6 uses 128-bit addresses.
- Routers use logical addresses to forward packets.
- Logical addresses may change when the device moves to another network or receives a new configuration.

**Example:**

```text
IPv4 address: 192.168.1.10
```

### 4. Physical address

A physical address identifies a network interface on a local link.

- It operates at the data-link layer.
- It is commonly called a MAC address.
- It is used for node-to-node delivery.
- Ethernet MAC addresses are normally 48 bits and written in hexadecimal.
- Switches use MAC addresses to forward frames within a local network.

**Example:**

```text
00:1A:2B:3C:4D:5E
```

### Addressing sequence

```text
Application:  www.example.com
       |
Transport:    Port 443
       |
Network:      IP address
       |
Data Link:    MAC address of next hop
       |
Physical:     Bits and signals
```

## B. Multiplexing

Multiplexing allows several higher-layer data streams or protocols to share a lower-layer service or communication path.

```text
Application streams
 HTTP     DNS     SMTP
    \\      |      /
     \\     |     /
      +---- MUX ----+
             |
       Shared lower layer
```

### Operation

1. Multiple application processes generate data.
2. The transport layer accepts data from different applications.
3. Port numbers are added to identify the originating and destination processes.
4. The network layer can accept segments from TCP, user datagrams from UDP, and messages from protocols such as ICMP.
5. The data-link layer can carry IP packets and other network-layer payloads such as ARP messages.
6. The appropriate protocol identifier in a header allows the receiving layer to distinguish the payload type.

## C. Demultiplexing

Demultiplexing is the reverse process. It separates received data and delivers it to the correct higher-layer protocol or application.

```text
Shared received data
          |
          v
        DEMUX
       /      \
    TCP/UDP   Other protocol
      |
      v
 Correct application selected by port number
```

### Operation at the destination

1. The data-link layer identifies the payload type and passes it to the proper network-layer protocol.
2. IP examines its protocol field and delivers the payload to TCP, UDP, ICMP, or another appropriate protocol.
3. TCP or UDP examines port numbers.
4. The transport layer delivers the data to the correct application process.
5. The application may use DNS to associate a human-readable name with the corresponding IP address.

### Multiplexing and demultiplexing comparison

| Feature | Multiplexing | Demultiplexing |
|---|---|---|
| Direction | Sender side | Receiver side |
| Data flow | Many inputs to one lower-layer stream | One received stream to many outputs |
| Purpose | Share a protocol or communication path | Separate and deliver data correctly |
| Main identifiers | Protocol fields and port numbers | Protocol fields and port numbers |
| Example | TCP accepts data from HTTP and FTP | TCP delivers received data to the correct process |

**Citation:** Module1_Reference_PPT, slides 29–30 (rendered PDF pages 29–30)

---

# Module 2 — Data-Link Layer and Media Access Control

## M2-Q1 — Explain link layer addressing with examples: 1. Unicast 2. Multicast 3. Broadcast

### Definition

Link-layer addressing identifies the destination interface on a particular data-link network. In Ethernet, the link-layer or MAC address is **48 bits**, normally written as six hexadecimal bytes separated by colons.

The address is used for delivery over a single local link. It is different from an IP address, which provides logical, end-to-end network-layer addressing.

### 1. Unicast addressing

Unicast means **one-to-one communication**.

- A frame is sent from one interface to one specific destination interface.
- Only the station whose MAC address matches the destination address accepts the frame.
- Example:

```text
Source MAC:      10:22:33:44:55:66
Destination MAC: A2:34:45:11:92:F1

        Sender  -------------------->  One receiver
```

Example unicast address:

```text
A2:34:45:11:92:F1
```

### 2. Multicast addressing

Multicast means **one-to-many communication within a group**.

- A frame is addressed to a group of stations.
- All stations belonging to that multicast group process the frame.
- Other stations discard it.
- Multicast has local-link jurisdiction at the link layer.

```text
                 +--> Receiver 1
Sender ----------+--> Receiver 2
                 +--> Receiver 3
                 X   Other stations ignore it
```

Example multicast address:

```text
A3:34:45:11:92:F1
```

In Ethernet, the least significant bit of the first octet indicates an individual/group address:

- `0` → individual/unicast address
- `1` → group address, normally multicast

### 3. Broadcast addressing

Broadcast means **one-to-all communication** on the local link.

- Every station on the local network receives and examines the frame.
- Ethernet uses the all-ones MAC address:

```text
FF:FF:FF:FF:FF:FF
```

```text
                 +--> Station A
                 +--> Station B
Sender ----------+--> Station C
                 +--> Station D
```

### Comparison

| Type | Meaning | Receivers | Ethernet example |
|---|---|---:|---|
| Unicast | One-to-one | One interface | `A2:34:45:11:92:F1` |
| Multicast | One-to-many | Selected group | `A3:34:45:11:92:F1` |
| Broadcast | One-to-all | Every station on local link | `FF:FF:FF:FF:FF:FF` |

### Important example: ARP

When a host knows the destination IP address but not the destination MAC address:

1. It creates an ARP Request.
2. It sends the request using the broadcast MAC address `FF:FF:FF:FF:FF:FF`.
3. All local stations receive the request.
4. Only the station having the requested IP address sends an ARP Reply.
5. The reply is sent as a unicast frame to the requesting host.
6. The sender stores the IP-to-MAC mapping and sends the data frame using the destination’s unicast MAC address.

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **3–6**; especially p. **4** for unicast, multicast and broadcast, and pp. **5–6** for ARP.

---

## M2-Q2 — Explain the character-oriented framing and bit oriented framing techniques used in the Data Link Layer with suitable examples.

### Definition of framing

Framing is the data-link-layer process of dividing a stream of bits into identifiable units called **frames**. A frame generally contains:

```text
+----------+-------------+----------+----------+
| Header   | Data        | Trailer  | Flag     |
+----------+-------------+----------+----------+
```

The header may contain source and destination addresses and control information. The trailer commonly contains error-detection information such as CRC.

For variable-size frames, delimiters are needed to identify the beginning and end of each frame.

### A. Character-oriented framing

In character-oriented, or byte-oriented, framing, the frame is treated as a sequence of 8-bit characters.

A special character called a **flag** marks the beginning and end of the frame.

```text
+------+--------+------+------+
| FLAG | Header | Data | FLAG |
+------+--------+------+------+
```

Example:

```text
FLAG = a reserved one-byte delimiter, for example `F`
ESC  = a reserved escape byte, for example `E`
Data = A B C D
Frame = FLAG | Header | A B C D | Trailer | FLAG
```

#### Byte stuffing

A problem occurs when the flag character appears naturally inside the data. The receiver might incorrectly interpret it as the end of the frame.

To solve this, an **escape character**, usually called `ESC`, is inserted before any data byte having the same pattern as the flag.

Original data:

```text
A  FLAG  ESC  B
```

Transmitted data after byte stuffing:

```text
A  ESC FLAG  ESC ESC  B
```

Thus both an embedded flag byte and an embedded escape byte are escaped.

Receiver operation:

1. Detect the opening flag.
2. Read the frame contents.
3. If `ESC` is encountered, remove it.
4. Treat the following byte as data, not as a delimiter.
5. Detect the final flag.
6. Deliver the recovered data to the upper layer.

#### Advantages and limitations

- Simple for character-based data.
- Works naturally with byte-oriented protocols.
- Byte stuffing introduces extra bytes.
- The method is less natural for arbitrary binary, audio or video data.

### B. Bit-oriented framing

In bit-oriented framing, the data field is treated as an arbitrary sequence of bits. A commonly used flag pattern is:

```text
01111110
```

The frame format is:

```text
+----------+--------+-------------+----------+
| Flag     | Header | Data        | Flag     |
|01111110  |        |             |01111110  |
+----------+--------+-------------+----------+
```

#### Bit stuffing

To ensure that the flag pattern does not accidentally occur in the data:

1. The sender examines the data bit stream.
2. Whenever it finds five consecutive `1`s, it inserts a `0`.
3. The receiver removes the inserted `0` after every sequence of five consecutive `1`s.
4. The actual flag pattern is not stuffed and is recognized as a delimiter.

Example:

```text
Data before stuffing:  01111110
Data after stuffing:   011111010
```

The inserted zero prevents the data from being mistaken for the flag.

#### Receiver operation

```text
Received bit stream
          |
          v
   Detect opening flag
          |
          v
 Remove a 0 after every five 1s
          |
          v
   Detect closing flag
          |
          v
       Deliver data
```

### Comparison

| Feature | Character-oriented framing | Bit-oriented framing |
|---|---|---|
| Basic unit | 8-bit character/byte | Individual bit |
| Delimiter | Special character or byte | Bit pattern, commonly `01111110` |
| Protection method | Byte stuffing | Bit stuffing |
| Suitable data | Traditionally text/characters | Arbitrary binary data |
| Extra information | Escape byte | Inserted zero bit |
| Receiver action | Remove escape byte | Remove stuffed zero |

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **6–7**.

---

## M2-Q3 — Describe the Simple Protocol with all suitable diagrams.

### Definition

The **Simple Protocol** is the simplest data-link-layer protocol. It is used to explain basic communication between a sender and a receiver under ideal channel conditions.

### Assumptions

1. The channel is error-free.
2. Frames are not lost, damaged or duplicated.
3. The receiver can process frames as quickly as they arrive.
4. The receiver always has sufficient buffer space.
5. Communication is unidirectional.
6. No acknowledgement is required.
7. No timer, retransmission or flow-control mechanism is used.

### Operation

1. The sender’s network layer produces a packet.
2. The packet is passed to the sender’s data-link layer.
3. The data-link layer encapsulates the packet in a frame.
4. The sender transmits the frame.
5. The receiver accepts the frame.
6. The receiver removes the header and trailer.
7. The recovered packet is delivered to the receiver’s network layer.
8. The sender is immediately ready to send the next frame.

### Flow diagram

```text
SENDER                                      RECEIVER
------                                      --------
Wait for packet                             Wait for frame
      |                                           |
      v                                           v
Packet arrives                              Frame arrives
      |                                           |
      v                                           v
Make frame                                  Extract packet
      |                                           |
      v                                           v
Send frame  ----------------------------->  Deliver packet
      |                                           |
      v                                           v
Ready for next packet                       Ready for next frame
```

### Sender FSM

```text
              Packet from network layer /
              make frame and send
       +--------------------------------------+
       |                                      |
       v                                      |
   +--------+                                 |
   | Ready  |---------------------------------+
   +--------+
```

The sender remains in the `Ready` state. It waits for a packet, creates a frame, sends it and returns to the same state.

### Receiver FSM

```text
              Frame arrives /
              extract and deliver
       +--------------------------------------+
       |                                      |
       v                                      |
   +--------+                                 |
   | Ready  |---------------------------------+
   +--------+
```

The receiver remains in the `Ready` state. It waits for a frame, extracts the packet, delivers it to the network layer and waits for the next frame.

### Characteristics

| Property | Simple Protocol |
|---|---|
| Flow control | Not provided |
| Error control | Not provided |
| ACK | Not used |
| Timer | Not used |
| Retransmission | Not used |
| Outstanding frames | Multiple frames may be sent continuously |
| Channel assumption | Error-free and reliable |
| Main advantage | Very simple and low overhead |
| Main limitation | Cannot handle loss, corruption or receiver overload |

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **8–10**.

---

## M2-Q4 — Describe the Stop-and-Wait Protocol and explain how it provides reliable data transmission.

### Definition

**Basic Stop-and-Wait** provides flow control by allowing only one outstanding frame. For reliable transmission over a noisy link, it is extended as **Stop-and-Wait ARQ**, which uses ACKs, a timer, retransmission, and a 1-bit sequence number. The sender transmits one frame and waits for its acknowledgement before transmitting the next frame.

Only one frame can be outstanding at a time.

### Operation

1. The network layer gives a packet to the sender’s data-link layer.
2. The sender creates a frame and retains a copy.
3. The sender transmits the frame.
4. The sender starts a timer.
5. The receiver checks the received frame and its 1-bit sequence number (`0` or `1`).
6. If the frame is correct and new, the receiver extracts and delivers the packet; if it is a duplicate, the receiver does not deliver it again.
7. The receiver sends the corresponding ACK.
8. When the sender receives the ACK, it stops the timer.
9. The sender accepts the next packet and repeats the process.
10. If the timer expires before an ACK arrives, the sender assumes that the frame or ACK was lost or corrupted.
11. The sender retransmits the retained copy of the frame.

### Normal transmission timeline

```text
Sender                                      Receiver
------                                      --------
Frame 0  ------------------------------->  Receive frame 0
Start timer                                Check frame 0
                                           Deliver packet
        <-------------------------------   ACK 0
Receive ACK 0
Stop timer
Send next frame
```

### Timeout and retransmission

```text
Sender                                      Receiver
------                                      --------
Frame 0  ------------------------------->  Frame lost/damaged
Start timer
        <-------------------------------   No ACK
Timer expires
Retransmit Frame 0 --------------------->  Receive correctly
        <-------------------------------   ACK 0
```

### Sender flowchart

```text
       +----------------------+
       | Wait for packet      |
       +----------+-----------+
                  |
                  v
       +----------------------+
       | Make and send frame  |
       | Start timer          |
       +----------+-----------+
                  |
                  v
       +----------------------+
       | Wait for ACK         |
       +-----+------------+---+
             |            |
       ACK received   Timeout
             |            |
             v            v
     +---------------+  +------------------+
     | Stop timer    |  | Retransmit frame |
     | Send next     |  | Restart timer    |
     +-------+-------+  +--------+---------+
             |                   |
             +--------<----------+
```

### Receiver operation

```text
Wait for frame
      |
      v
Receive and check frame
      |
      +-- Incorrect/lost --> Discard; no positive ACK
      |
      +-- Correct ---------> Extract and deliver packet
                             Send ACK
                             Wait for next frame
```

### How reliability is achieved

- **Flow control:** The sender cannot overrun a slow receiver because it waits for an ACK after each frame.
- **Error control:** A corrupted frame is not accepted.
- **Timer:** Detects a lost frame or lost ACK.
- **Retransmission:** The sender resends the frame after timeout.
- **Frame copy:** The sender retains the frame until successful acknowledgement.
- **Acknowledgement:** Confirms successful reception.
- **Alternating-bit sequence number:** Distinguishes a new frame from a retransmission after a lost ACK, preventing duplicate delivery.

Therefore, ACK and timeout alone are insufficient for complete lost-ACK reliability; duplicate suppression using the alternating `0/1` sequence number is required.

### Simple Protocol versus Stop-and-Wait

| Feature | Simple Protocol | Stop-and-Wait |
|---|---|---|
| Flow control | No | Yes |
| Error control | No | Yes, in Stop-and-Wait ARQ |
| ACK | No | Yes |
| Timer | No | Yes |
| Retransmission | No | Yes |
| Frames in transit | Several possible | One |
| Channel assumption | Ideal | May lose or corrupt frames |
| Efficiency | High on ideal links | Lower because of waiting |
| Reliability | Not guaranteed | Improved through ACK and retransmission |

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **11–15**.

---

## M2-Q5 — Describe the operation of the Pure ALOHA and Slotted ALOHA protocols. Compare their performance.

## A. Pure ALOHA

### Definition

In Pure ALOHA, a station transmits a frame **whenever it has a frame to send**. It does not wait for a slot boundary and does not sense the channel before transmission.

### Operation

1. A station obtains a frame.
2. It immediately transmits the frame.
3. The receiver sends an ACK if the frame is received successfully.
4. If two or more frames overlap, a collision occurs.
5. The collided frames are destroyed.
6. The sender waits for an ACK.
7. If no ACK arrives before timeout, the sender selects a random backoff time.
8. The sender retransmits the frame.
9. The procedure continues until successful transmission or the retry limit is reached.

```text
Time -------------------------------------------------------->

Station A:        [--------- Frame A ---------]
Station B:                    [--------- Frame B ---------]
                              <--- overlap --->
                                      Collision
```

### Vulnerable time

If T is the frame transmission time, another frame may begin up to T before or T after the beginning of the current frame.

\[
T_v = 2T
\]

### Throughput

\[
S = Ge^{-2G}
\]

where:

- \(G\) = average number of generated frames per frame transmission time
- \(S\) = successful frames per frame time

Maximum throughput occurs at:

\[
G = 0.5
\]

\[
S_{\max}=0.5e^{-1}=0.184
\]

Therefore, the maximum theoretical efficiency is approximately:

\[
\boxed{18.4\%}
\]

## B. Slotted ALOHA

### Definition

Slotted ALOHA divides time into equal slots, each having a duration equal to one frame transmission time. A station may begin transmission **only at the beginning of a slot**.

### Operation

1. Time is divided into synchronized slots.
2. Each slot has duration T.
3. A station with a frame waits for the next slot boundary.
4. It transmits the complete frame during that slot.
5. If only one station transmits in a slot, the frame succeeds.
6. If two or more stations transmit in the same slot, a collision occurs.
7. Collided stations wait for random numbers of slots.
8. They retransmit in later slots.

```text
Slot:       |    1    |    2    |    3    |    4    |

Station A: |         | Frame A |         |         |
Station B: |         | Frame B |         |         |
                              Collision
```

### Vulnerable time

Because transmissions can start only at slot boundaries:

\[
T_v=T
\]

### Throughput

\[
S=Ge^{-G}
\]

Maximum throughput occurs at:

\[
G=1
\]

\[
S_{\max}=1e^{-1}=0.368
\]

Therefore, the maximum theoretical efficiency is approximately:

\[
\boxed{36.8\%}
\]

### Comparison

| Parameter | Pure ALOHA | Slotted ALOHA |
|---|---|---|
| Transmission start | Any time | Only at slot boundary |
| Time division | No slots | Equal time slots |
| Slot duration | Not applicable | Equal to frame time T |
| Synchronization | Not required | Required |
| Vulnerable time | 2T | T |
| Collision probability | Higher | Lower |
| Throughput | \(S=Ge^{-2G}\) | \(S=Ge^{-G}\) |
| Optimum offered load | \(G=0.5\) | \(G=1\) |
| Maximum throughput | 18.4% | 36.8% |
| Complexity | Simpler | More complex |
| Main disadvantage | High collision probability | Requires synchronization |

### Conclusion

Slotted ALOHA approximately doubles the maximum throughput of Pure ALOHA because it reduces the vulnerable time from 2T to T. However, it requires synchronization among all stations.

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **18–25**.

---

## M2-Q6 — A pure ALOHA network transmits 200-bits frames on a shared channel of 200 kbps. What is the throughput if the system produces? a. 1000 frames per second b. 500 frames per second c. 250 frames per second

### Given

\[
L=200\text{ bits}
\]

\[
R=200\text{ kbps}=200,000\text{ bits/s}
\]

Frame transmission time:

\[
T=\frac{L}{R}
 =\frac{200}{200,000}
 =0.001\text{ s}
 =1\text{ ms}
\]

For Pure ALOHA:

\[
S=Ge^{-2G}
\]

where G is the number of generated frames during one frame time.

For a generation rate lambda:

\[
G=\lambda T
\]

The successful throughput in frames per second is:

\[
\lambda_s=\frac{S}{T}
\]

Equivalently:

\[
\lambda_s=\lambda e^{-2G}
\]

### (a) Generation rate = 1000 frames/s

\[
G=(1000)(0.001)=1
\]

\[
S=1\times e^{-2}
\]

\[
S=0.1353
\]

Thus, the successful throughput is:

\[
\lambda_s=\frac{0.1353}{0.001}
=135.3\text{ frames/s}
\]

In bits per second:

\[
135.3\times200=27,060\text{ bits/s}
\]

\[
\boxed{\lambda_s\approx135\text{ frames/s}}
\]

\[
\boxed{\text{Throughput}\approx27.1\text{ kbps}}
\]

### (b) Generation rate = 500 frames/s

\[
G=(500)(0.001)=0.5
\]

\[
S=0.5e^{-1}
\]

\[
S=0.1839\approx0.184
\]

Successful throughput:

\[
\lambda_s=\frac{0.1839}{0.001}
=183.9\text{ frames/s}
\]

Alternatively:

\[
\lambda_s=500e^{-1}
=183.9\text{ frames/s}
\]

In bits per second:

\[
183.9\times200=36,780\text{ bits/s}
\]

\[
\boxed{\lambda_s\approx184\text{ frames/s}}
\]

\[
\boxed{\text{Throughput}\approx36.8\text{ kbps}}
\]

This is the maximum-throughput operating point for Pure ALOHA.

### (c) Generation rate = 250 frames/s

\[
G=(250)(0.001)=0.25
\]

\[
S=0.25e^{-0.5}
\]

\[
S=0.1516\approx0.152
\]

Successful throughput:

\[
\lambda_s=\frac{0.1516}{0.001}
=151.6\text{ frames/s}
\]

Alternatively:

\[
\lambda_s=250e^{-0.5}
=151.6\text{ frames/s}
\]

In bits per second:

\[
151.6\times200=30,320\text{ bits/s}
\]

\[
\boxed{\lambda_s\approx152\text{ frames/s}}
\]

\[
\boxed{\text{Throughput}\approx30.3\text{ kbps}}
\]

### Final results

| Generated rate lambda | G=lambda T | Normalized throughput S | Successful frames/s | Bit throughput |
|---:|---:|---:|---:|---:|
| 1000 frames/s | 1.00 | 0.1353 | 135.3 | 27.1 kbps |
| 500 frames/s | 0.50 | 0.1839 | 183.9 | 36.8 kbps |
| 250 frames/s | 0.25 | 0.1516 | 151.6 | 30.3 kbps |

**Citation:** Module 2 Reference PPT, Slide/PDF p. **21**. The formula and vulnerable-time basis are on p. **20**.

---

## M2-Q7 — A slotted ALOHA network transmits 200-bit frames using a shared channel with a 200-kbps bandwidth. Find the throughput if the system produces a. 1000 frames per second. b. 500 frames per second. c. 250 frames per second.

### Given

\[
L=200\text{ bits}
\]

\[
R=200,000\text{ bits/s}
\]

\[
T=\frac{200}{200,000}
=0.001\text{ s}
=1\text{ ms}
\]

For Slotted ALOHA:

\[
S=Ge^{-G}
\]

\[
G=\lambda T
\]

Successful throughput:

\[
\lambda_s=\frac{S}{T}
=\lambda e^{-G}
\]

### (a) Generation rate = 1000 frames/s

\[
G=(1000)(0.001)=1
\]

\[
S=1e^{-1}=0.3679
\]

Successful throughput:

\[
\lambda_s=\frac{0.3679}{0.001}
=367.9\text{ frames/s}
\]

In bits per second:

\[
367.9\times200=73,580\text{ bits/s}
\]

\[
\boxed{\lambda_s\approx368\text{ frames/s}}
\]

\[
\boxed{\text{Throughput}\approx73.6\text{ kbps}}
\]

This is the maximum-throughput operating point for Slotted ALOHA.

### (b) Generation rate = 500 frames/s

\[
G=(500)(0.001)=0.5
\]

\[
S=0.5e^{-0.5}
\]

\[
S=0.3033
\]

Successful throughput:

\[
\lambda_s=\frac{0.3033}{0.001}
=303.3\text{ frames/s}
\]

Alternatively:

\[
\lambda_s=500e^{-0.5}
=303.3\text{ frames/s}
\]

In bits per second:

\[
303.3\times200=60,660\text{ bits/s}
\]

\[
\boxed{\lambda_s\approx303\text{ frames/s}}
\]

\[
\boxed{\text{Throughput}\approx60.7\text{ kbps}}
\]

### (c) Generation rate = 250 frames/s

\[
G=(250)(0.001)=0.25
\]

\[
S=0.25e^{-0.25}
\]

\[
S=0.1947
\]

Successful throughput:

\[
\lambda_s=\frac{0.1947}{0.001}
=194.7\text{ frames/s}
\]

Alternatively:

\[
\lambda_s=250e^{-0.25}
=194.7\text{ frames/s}
\]

In bits per second:

\[
194.7\times200=38,940\text{ bits/s}
\]

\[
\boxed{\lambda_s\approx195\text{ frames/s}}
\]

\[
\boxed{\text{Throughput}\approx38.9\text{ kbps}}
\]

### Final results

| Generated rate lambda | G=lambda T | Normalized throughput S | Successful frames/s | Bit throughput |
|---:|---:|---:|---:|---:|
| 1000 frames/s | 1.00 | 0.3679 | 367.9 | 73.6 kbps |
| 500 frames/s | 0.50 | 0.3033 | 303.3 | 60.7 kbps |
| 250 frames/s | 0.25 | 0.1947 | 194.7 | 38.9 kbps |

**Citation:** Module 2 Reference PPT, Slide/PDF p. **24**. The formula and vulnerable-time basis are on p. **23**.

---

## M2-Q8 — Explain the working principle of the Carrier Sense Multiple Access (CSMA) protocol and discuss its persistence methods.

### Definition

**Carrier Sense Multiple Access (CSMA)** is a random-access MAC protocol in which a station senses the shared channel before transmitting.

It follows the principle:

> **Listen before transmit.**

CSMA reduces collisions compared with ALOHA, but it cannot eliminate them completely. Two stations may sense the channel as idle at nearly the same time and begin transmitting together.

### Basic CSMA operation

1. A station obtains a frame for transmission.
2. It senses the channel.
3. If the channel is idle, it follows the selected persistence rule and transmits.
4. If the channel is busy, it waits according to the persistence rule.
5. If two stations transmit nearly simultaneously, a collision may occur.
6. After a collision, each station waits for a backoff interval.
7. The stations sense the channel again and retry.

```text
             Frame ready
                  |
                  v
          Sense the channel
             /           \\
          Busy           Idle
           |              |
           v              v
  Apply persistence   Apply persistence
       method             method
           |              |
           +-------> Transmit
                         |
                 Collision possible
                         |
                         v
                    Backoff/retry
```

### Vulnerable time

In CSMA, a station may not immediately know that another station has started transmitting because of propagation delay.

\[
T_v\approx\tau
\]

where tau is the maximum propagation time between two stations.

This is generally much smaller than the Pure ALOHA vulnerable time 2T, but it is not zero.

### 1. 1-persistent CSMA

1-persistent CSMA continuously senses the channel.

1. If the channel is idle, the station transmits immediately with probability 1.
2. If the channel is busy, the station continuously senses the channel.
3. As soon as the channel becomes idle, it transmits.
4. If several stations are waiting, they may all transmit at the same instant and collide.

```text
Sense channel
      |
      +-- Busy --> Keep sensing continuously
      |                    |
      |                    v
      +-- Idle <------- Channel idle
                           |
                           v
                       Transmit
```

**Advantage:** Low waiting time.

**Disadvantage:** Several waiting stations may transmit together when the channel becomes free.

### 2. Nonpersistent CSMA

1. The station senses the channel.
2. If the channel is idle, it transmits.
3. If the channel is busy, it does not continuously monitor the channel.
4. It waits for a random backoff time.
5. It senses the channel again.
6. The process repeats until transmission begins.

```text
Sense channel
      |
      +-- Idle --> Transmit
      |
      +-- Busy --> Random wait
                       |
                       v
                  Sense again
```

**Advantage:** Reduces the probability that many stations transmit simultaneously.

**Disadvantage:** Random waiting increases delay, even when the channel may become idle shortly afterward.

### 3. p-persistent CSMA

p-persistent CSMA is generally used with a slotted channel.

When the channel is idle:

1. Transmit with probability p.
2. With probability 1-p, defer transmission to the next slot.
3. Sense the channel again in the next slot.
4. Repeat until transmission occurs or the channel becomes busy.

```text
Channel idle
      |
      +-- Probability p ------> Transmit
      |
      +-- Probability 1-p ----> Wait one slot
                                      |
                                      v
                               Sense again
```

**Advantage:** Provides a compromise between the immediate transmission of 1-persistent CSMA and the random deferral of nonpersistent CSMA.

**Disadvantage:** Requires slot synchronization and proper selection of p.

### Comparison of persistence methods

| Feature | 1-persistent | Nonpersistent | p-persistent |
|---|---|---|---|
| Channel condition | Continuously sensed | Resensed after random wait | Resensed every slot |
| If idle | Transmit immediately | Transmit immediately | Transmit with probability p |
| If busy | Keep sensing | Wait random time | Wait according to slots |
| Synchronization | Not necessarily required | Not necessarily required | Required |
| Collision tendency | Highest among waiting stations | Lower | Controlled by p |
| Delay | Low when idle | Higher due to random wait | Intermediate |
| Typical use | Basic CSMA | Reduced collision probability | Slotted channels |

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **26–28**.

---

## M2-Q9 — Describe the operation of the CSMA/CD protocol with a neat flowchart and explain how it resolves collisions in wired networks.

### Definition

**Carrier Sense Multiple Access with Collision Detection (CSMA/CD)** is a CSMA protocol in which a station:

1. Listens before transmitting.
2. Transmits on a shared medium.
3. Continues monitoring the medium while transmitting.
4. Detects a collision if another station transmits simultaneously.

It was traditionally associated with shared, half-duplex Ethernet.

### Operation

1. A frame becomes ready.
2. The station senses the channel.
3. If the channel is busy, the station waits.
4. If the channel is idle, the station begins transmission.
5. It monitors the channel during transmission.
6. If no collision is detected, transmission completes successfully.
7. If a collision is detected, the station transmits a jam sequence so all stations recognize the collision.
8. It then aborts the corrupted frame transmission.
9. It increments the collision count.
10. It selects a random backoff interval using binary exponential backoff.
11. After backoff, it senses the channel again.
12. It retransmits if the channel is idle.
13. The process ends after successful transmission or the maximum retry limit.

### CSMA/CD flowchart

```text
             Frame ready
                  |
                  v
          Sense the channel
             /           \\
          Busy           Idle
           |              |
           v              v
          Wait       Start transmission
                          |
                          v
              Monitor while transmitting
                     /             \\
              Collision?            No
                  |                 |
                 Yes                v
                  |          Complete frame
                  v
       Transmit jam sequence
                  |
                  v
        Abort corrupted frame
                  |
                  v
       Increment collision counter
                  |
                  v
       Binary exponential backoff
                  |
                  v
       Retry limit exceeded?
             /             \\
           Yes              No
            |                |
            v                v
          Give up       Sense channel again
```

### Collision resolution

Binary exponential backoff reduces repeated collisions.

After the nth collision, the station chooses a random integer K from:

\[
K\in\{0,1,2,\ldots,2^m-1\}
\]

where:

\[
m=\min(n,10)
\]

The waiting time is:

\[
T_{\text{backoff}}=K\times T_{\text{slot}}
\]

For classic Ethernet, the slot time is related to the maximum round-trip propagation time. After repeated collisions, the contention range expands, reducing the probability that the same stations retransmit together.

After the maximum permitted number of attempts, the frame is discarded and an error is reported.

### Why collision detection is useful

Without collision detection, stations would continue transmitting a frame that has already been corrupted. CSMA/CD:

- Detects a collision early.
- Stops wasting channel time.
- Notifies all stations with a jam signal.
- Randomizes retransmission times.
- Reduces the chance of repeated collisions.

### Important limitation

CSMA/CD is suitable for shared wired, half-duplex media. Modern switched full-duplex Ethernet normally eliminates collisions, so CSMA/CD is generally not active in that environment.

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **29–30**.

---

## M2-Q10 — Explain the working of the CSMA/CA protocol and discuss the techniques used to avoid collisions in wireless LANs.

### Definition

**Carrier Sense Multiple Access with Collision Avoidance (CSMA/CA)** is a random-access protocol used mainly in IEEE 802.11 wireless LANs.

Collision detection is difficult in wireless networks because:

- A station’s own transmitted signal is much stronger than a received signal.
- A station generally cannot listen reliably while transmitting.
- Hidden terminals may be unable to hear one another.
- A collision may occur at the receiver even though the sender senses the channel as idle.

Therefore, wireless LANs try to **avoid** collisions rather than detect them during transmission.

### Basic CSMA/CA operation

1. A wireless station obtains a frame.
2. It senses the channel.
3. If the channel is busy, it waits.
4. If the channel is idle, it waits for an interframe space.
5. It selects a random backoff value from the contention window.
6. It counts down while the channel remains idle.
7. If the channel becomes busy, it freezes the counter.
8. After the channel becomes idle again and the required IFS elapses, it resumes countdown.
9. When the counter reaches zero, it transmits.
10. The receiver sends an ACK after a short interframe space.
11. If the ACK arrives, the transmission is successful.
12. If no ACK arrives, the sender assumes failure or collision.
13. The contention window is increased and the frame is retransmitted after another random backoff.

### CSMA/CA flowchart

```text
              Frame ready
                   |
                   v
           Sense wireless channel
              /             \\
           Busy             Idle
            |                |
            v                v
           Wait        Wait for IFS
                             |
                             v
                Select random backoff
                from contention window
                             |
                             v
                  Countdown while idle
                       /          \\
             Channel busy          Counter = 0
                  |                    |
                  v                    v
          Freeze counter          Transmit frame
                  |                    |
                  +--> Wait for idle   v
                              Receive ACK?
                              /         \\
                            Yes          No
                             |            |
                             v            v
                         Success   Increase CW,
                                   select new backoff
```

### Interframe Space (IFS)

An **Interframe Space** is a required idle interval between transmissions.

In IEEE 802.11, common IFS categories include:

- **SIFS:** Short Interframe Space. Used before immediate responses such as ACK, CTS and certain control frames.
- **DIFS:** Distributed Interframe Space. Used by a station before beginning normal contention.
- Other IFS values may be used for priority and coordination.

The shorter SIFS gives ACK and other immediate control responses priority over new data transmissions.

### Contention window and random backoff

A station chooses a random integer B from the contention window:

\[
B\in[0,CW]
\]

The backoff delay is:

\[
T_{\text{backoff}}=B\times T_{\text{slot}}
\]

Stations whose counters reach zero first transmit first. If a collision or transmission failure occurs, the contention window is increased, commonly by binary exponential growth up to a maximum value. After successful transmission, it is reduced toward its minimum value.

### ACK mechanism

The sender cannot directly detect a collision while transmitting. Instead:

1. The sender transmits the data frame.
2. The receiver checks the frame.
3. If the frame is correct, the receiver waits SIFS.
4. It sends an ACK.
5. If the sender does not receive the ACK within the expected time, it assumes that the frame was lost or collided.
6. It increases the contention window and retransmits later.

### RTS/CTS collision-avoidance mechanism

The **Request-to-Send/Clear-to-Send (RTS/CTS)** exchange can reduce collisions caused by hidden terminals.

```text
Sender                         Receiver                 Other stations
  |                                |                         |
  |-------- RTS -----------------> |                         |
  |<------- CTS ------------------ |                         |
  |-------- DATA ----------------> |  Other stations defer  |
  |<------- ACK ------------------ |                         |
```

Operation:

1. The sender contends for the channel.
2. It sends an RTS control frame.
3. The receiver responds with CTS.
4. Stations hearing the RTS or CTS defer transmission for the announced duration.
5. The sender transmits the data frame.
6. The receiver replies with an ACK.

RTS/CTS is especially useful for long frames or networks with hidden terminals, but it introduces control overhead. It may be omitted for short frames.

### Collision-avoidance techniques

| Technique | Purpose |
|---|---|
| Carrier sensing | Avoid transmitting while the channel is busy |
| IFS | Establish priority and separation between frames |
| Random backoff | Prevent simultaneous retransmission |
| Contention window | Controls the range of random waiting values |
| ACK | Confirms successful reception |
| Exponential contention-window increase | Reduces repeated collisions |
| RTS/CTS | Addresses hidden-terminal collisions |
| NAV/virtual carrier sensing | Allows stations to defer for a reserved duration |

### CSMA/CD versus CSMA/CA

| Feature | CSMA/CD | CSMA/CA |
|---|---|---|
| Main environment | Shared wired Ethernet | Wireless LAN |
| Collision handling | Detects during transmission | Attempts to avoid collision |
| ACK | Not fundamental to collision detection | Essential for confirming reception |
| Random backoff | After detected collision | Before transmission and after failure |
| RTS/CTS | Normally not used | May be used |
| Reason | Wired station can monitor medium | Wireless station cannot reliably detect while transmitting |

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **31–32**.

---

## M2-Q11 — Explain the controlled access techniques—Reservation, Polling and Token Passing used in Media Access Control.

### Definition

In **controlled access**, stations do not compete randomly for the shared medium. Access is coordinated so that only an authorized station transmits at a particular time.

The major controlled-access methods are:

1. Reservation
2. Polling
3. Token passing

Their common objective is to avoid collisions and provide orderly access.

### 1. Reservation

#### Operation

Reservation divides time into:

1. A reservation phase.
2. A data-transmission phase.

Steps:

1. Time is divided into reservation intervals and data intervals.
2. A station that wants to transmit marks or reserves an interval.
3. Reservation information is made known to all stations.
4. The stations determine the transmission order.
5. Reserved stations transmit during their assigned periods.
6. A new reservation cycle begins.

```text
One reservation cycle
+----------------------+-----------------------------+
| Reservation phase    | Data-transmission phase    |
| R1 R2 R3 ...         | S2 | S5 | S7 | ...          |
+----------------------+-----------------------------+
```

Only stations with reservations transmit during the corresponding data phase.

**Advantages**

- Collisions are avoided.
- Access is organized.
- Fair and predictable access is possible.
- Suitable for traffic requiring guaranteed opportunities.

**Disadvantages**

- Reservation bits or messages create overhead.
- A reserved period may be wasted if the station has no data.
- More complex than random access.
- Inefficient under very light traffic.

### 2. Polling

#### Definition

Polling uses a central controller, called the **primary station**, to ask other stations, called **secondary stations**, whether they have data to send.

#### Operation

1. One station is designated as the primary.
2. The remaining stations are secondaries.
3. The primary polls stations in a predefined order.
4. A polled station transmits if it has data.
5. If it has no data, the primary polls the next station.
6. The process continues repeatedly.

```text
              Poll
       +----------------+
       | Primary        |
       +----------------+
        /      |       \\
       v       v        v
    Station A Station B Station C
       |         |        |
   Transmit?  Transmit? Transmit?
```

**Advantages**

- No collisions because only the polled station may transmit.
- Simple and orderly.
- Priority can be assigned.
- Suitable for centralized networks.

**Disadvantages**

- The primary station is a single point of failure.
- Polling creates overhead and delay.
- Inefficient if most stations have no data.
- Delay increases as the number of stations increases.

### 3. Token passing

#### Definition

In token passing, stations form a logical ring or a predefined sequence. A special control frame called a **token** circulates among them.

> **Possession of the token gives permission to transmit.**

#### Operation

1. Stations are arranged in a logical order.
2. A token circulates from one station to the next.
3. A station receiving the token checks whether it has data.
4. If it has no data, it passes the token onward.
5. If it has data, it holds the token and transmits.
6. After transmission, it releases or passes the token.
7. The process continues around the logical ring.

```text
       +---------+       +---------+
       |   A     | ----> |   B     |
       +---------+       +---------+
          ^                  |
          |                  v
       +---------+ <---- +---------+
       |   D     |       |   C     |
       +---------+       +---------+

             Token circulates
```

**Advantages**

- No collisions during normal operation.
- Fair access to all stations.
- Predictable waiting time.
- Suitable for heavy traffic.

**Disadvantages**

- Token-management procedures are required.
- A lost or damaged token must be regenerated.
- A malfunctioning station may affect the ring.
- More complex than random access.
- Token circulation creates overhead.

### Comparison

| Feature | Reservation | Polling | Token passing |
|---|---|---|---|
| Control mechanism | Reservation intervals | Central primary station | Circulating token |
| Collision possibility | Avoided | Avoided | Avoided during normal operation |
| Central controller | Not essential | Required | Not required |
| Main delay | Reservation phase | Polling cycle | Token rotation |
| Failure concern | Wasted reservations | Primary failure | Lost token/station failure |
| Best suited for | Predictable scheduled traffic | Centralized networks | Fair access and heavy traffic |

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **33–36**.

---

## M2-Q12 — Explain the channelization techniques FDMA, TDMA, and CDMA with neat diagrams and discuss their characteristics.

### Definition

**Channelization** divides a shared communication resource among multiple users. The users are separated using frequency, time or code so that several users can communicate with minimum mutual interference.

The three important techniques are:

1. FDMA — Frequency Division Multiple Access
2. TDMA — Time Division Multiple Access
3. CDMA — Code Division Multiple Access

### 1. FDMA

#### Definition

FDMA divides the available bandwidth into non-overlapping frequency bands. Each user receives a separate frequency band.

#### Diagram

```text
Frequency
   ^
   |       User C
   |    +---------+
   |    |         |
   |    +---------+
   |       Guard
   |       band
   |    +---------+
   |    | User B  |
   |    +---------+
   |       Guard
   |       band
   |    +---------+
   |    | User A  |
   |    +---------+
   +----------------------------> Time
```

#### Operation

1. The total bandwidth is divided into frequency channels.
2. Each user is allocated one frequency band.
3. Users transmit simultaneously.
4. Guard bands separate adjacent channels.
5. The frequency allocation generally remains fixed during communication.

#### Characteristics

- Each user has a separate frequency band.
- Users can transmit simultaneously.
- Guard bands are required.
- Precise time synchronization is not essential.
- Suitable for continuous traffic such as voice.
- Bandwidth may be wasted when a user is inactive.
- Accurate frequency filtering is required.
- Adjacent-channel interference must be controlled.

### 2. TDMA

#### Definition

TDMA allows all users to share the same frequency band but assigns each user a different time slot.

#### Diagram

```text
Time -------------------------------------------------------->

        Frame 1                         Frame 2
+------+------+------+------+    +------+------+------+------+
| U1   | U2   | U3   | U4   |    | U1   | U2   | U3   | U4   |
+------+------+------+------+    +------+------+------+------+
        Same frequency band; users transmit in different slots
```

Guard time may be inserted between slots:

```text
| U1 |guard| U2 |guard| U3 |guard| U4 |
```

#### Operation

1. The available time is divided into frames.
2. Each frame is divided into time slots.
3. Each user receives one or more slots.
4. Users transmit only during their assigned slots.
5. The slots repeat periodically.
6. Synchronization ensures that users transmit in the correct intervals.

#### Characteristics

- All users use the same frequency.
- Users are separated in the time domain.
- Time synchronization is required.
- Guard time may be needed.
- Suitable for digital and bursty traffic.
- A transmitter need not operate continuously.
- Fixed allocation can waste unused slots.
- A user may experience delay while waiting for its slot.

### 3. CDMA

#### Definition

CDMA allows multiple users to transmit at the same time and on the same frequency. Each user is separated by a unique spreading code.

#### Diagram

```text
User A data --+
              | multiply by code A --\\
User B data --+ multiply by code B ----+--> Shared channel
              |                       /
User C data --+ multiply by code C --/

Shared received signal
          |
          v
Correlate with code A --> Recover User A
Correlate with code B --> Recover User B
Correlate with code C --> Recover User C
```

#### Operation

1. All users share the same frequency band.
2. Each user is assigned a unique code sequence.
3. The user’s data is multiplied by its code.
4. The resulting signal is spread over a wider bandwidth.
5. All spread signals are transmitted simultaneously.
6. The receiver correlates the composite signal with the desired user’s code.
7. Signals using different, suitably designed codes can be separated because of their low correlation.

#### Characteristics

- All users use the same frequency.
- All users may transmit simultaneously.
- Users are separated using unique codes.
- Good power control is required.
- It provides resistance to narrowband interference.
- It provides frequency diversity through spreading.
- It has soft capacity rather than a strict fixed channel count.
- It is more complex than FDMA and TDMA.
- The near-far problem and multiple-access interference must be controlled.
- Code synchronization and accurate code generation are required.

### Comparison

| Feature | FDMA | TDMA | CDMA |
|---|---|---|---|
| Separation basis | Frequency | Time | Code |
| Frequency use | Separate band per user | Same band | Same band |
| Time use | Simultaneous | Separate slots | Simultaneous |
| Code use | Not required | Not required | Unique code per user |
| Synchronization | Frequency filtering | Time synchronization | Code synchronization |
| Guard requirement | Guard bands | Guard times | Code separation |
| Continuous transmission | Possible | Not necessary | Possible |
| Inactive-user efficiency | Low with fixed allocation | Low with fixed slots | More flexible |
| Interference concern | Adjacent-channel interference | Slot overlap | Multiple-access and near-far interference |
| Complexity | Low | Moderate | High |
| Typical suitability | Continuous voice | Digital/bursty traffic | Mobile and spread-spectrum systems |

### Summary diagrams

```text
FDMA:  User A = f1, User B = f2, User C = f3
       Different frequencies, same time

TDMA:  User A = t1, User B = t2, User C = t3
       Same frequency, different times

CDMA:  User A = code A
       User B = code B
       User C = code C
       Same frequency and same time, different codes
```

**Citation:** Module 2 Reference PPT, Slide/PDF pp. **37–41**.

---

# Module 3 — Wired LANs and Wireless LANs

## M3-Q1. Describe the frame format of Ethernet and explain the purpose of each field.

An Ethernet frame carries a network-layer packet over an IEEE 802.3 LAN. The MAC frame contains addressing, protocol-identification, data, and error-detection information.

### Ethernet frame format

```text
Transmission direction ─────────────────────────────────────────────────────►

┌──────────┬─────┬──────────────┬──────────────┬──────────────┬──────────────┬─────────┐
│ Preamble │ SFD │ Destination  │ Source       │ Length/Type  │ Data +       │ CRC/FCS │
│ 7 bytes  │  1 B │ Address 6 B  │ Address 6 B  │ 2 bytes      │ Padding      │ 4 bytes │
└──────────┴─────┴──────────────┴──────────────┴──────────────┴──────────────┴─────────┘
                                                               46–1500 bytes
```

| Field | Size | Purpose |
|---|---:|---|
| **Preamble** | 7 bytes | A pattern of alternating 0s and 1s used to alert the receiver to an incoming frame and synchronize timing. It is normally added at the physical layer and is not counted as part of the MAC frame. |
| **Start Frame Delimiter (SFD)** | 1 byte | The pattern `10101011` marks the actual beginning of the frame. Its final two 1s indicate that the destination address follows. |
| **Destination Address (DA)** | 6 bytes | The MAC address of the intended receiving station, group of stations, or all stations on the LAN. |
| **Source Address (SA)** | 6 bytes | The MAC address of the station that transmitted the frame. |
| **Length/Type** | 2 bytes | In IEEE 802.3, this field can specify the length of the data field. In Ethernet II, it identifies the upper-layer protocol, such as IPv4 or ARP. |
| **Data and Padding** | 46–1500 bytes | Carries the encapsulated upper-layer packet. Padding is added when necessary to make the frame reach the minimum length required for collision detection. |
| **CRC/FCS** | 4 bytes | Contains a 32-bit cyclic redundancy check (CRC-32) used by the receiver to detect errors in the frame. |

The minimum data field is 46 bytes, and the maximum is 1500 bytes. From Destination Address through FCS, the Ethernet MAC frame is **64–1518 bytes**. Including the 7-byte preamble and 1-byte SFD, **72–1526 bytes** are transmitted before any interpacket gap. Ethernet detects errors using CRC-32 but does not provide frame acknowledgements at the MAC layer.

**Source:** Question Bank, p. 2, Module 3, Q1; Module 3 slide 3 / `Module3_Reference_PPT_rendered.pdf`, p. 3, and slide 4 / PDF p. 4.

---

## M3-Q2. Analyze the following destination MAC addresses and determine whether each address represents a unicast, multicast, or broadcast destination. Justify your classification based on the address format. a. 4A:30:10:21:10:1A b. 47:20:1B:2E:08:EE c. FF:FF:FF:FF:FF:FF

The classification is determined from the **least significant bit of the first octet**. This bit is called the **I/G bit**:

- `0` → individual or **unicast** address.
- `1` → group or **multicast** address.
- `FF:FF:FF:FF:FF:FF` → **broadcast** address.

The test must use the first octet as a complete binary octet. In hexadecimal notation, it is equivalent to checking whether the **second hexadecimal digit of the first octet** is even or odd, because that digit contains the I/G bit.

| MAC address | First octet in binary | I/G bit | Classification | Reason |
|---|---|---:|---|---|
| `4A:30:10:21:10:1A` | `01001010` | 0 | **Unicast** | The least significant bit of `4A` is 0. |
| `47:20:1B:2E:08:EE` | `01000111` | 1 | **Multicast** | The least significant bit of `47` is 1. |
| `FF:FF:FF:FF:FF:FF` | `11111111:...:11111111` | 1 | **Broadcast** | All 48 bits are 1, which is the Ethernet broadcast address. |

Therefore:

1. `4A:30:10:21:10:1A` — **Unicast**
2. `47:20:1B:2E:08:EE` — **Multicast**
3. `FF:FF:FF:FF:FF:FF` — **Broadcast**

**Source:** Question Bank, p. 2, Module 3, Q2; Module 3 slide 5 / `Module3_Reference_PPT_rendered.pdf`, p. 5. The classification above uses the correct I/G-bit rule; the slide’s wording is interpreted as referring to the least significant bit of the first octet.

---

## M3-Q3. Analyze the destination MAC address 47:20:1B:2E:08:EE and determine how a frame with this address would be transmitted on the network.

The destination address is:

```text
47:20:1B:2E:08:EE
```

The first octet is:

```text
47₁₆ = 01000111₂
```

Its least significant bit is `1`, so this is a **multicast MAC address**.

### Bit transmission order

Ethernet transmits the MAC address **byte by byte from left to right**, but transmits the bits within each byte **least significant bit first**.

| Address byte | Normal binary representation | Transmitted bit order |
|---|---|---|
| `47` | `01000111` | `11100010` |
| `20` | `00100000` | `00000100` |
| `1B` | `00011011` | `11011000` |
| `2E` | `00101110` | `01110100` |
| `08` | `00001000` | `00010000` |
| `EE` | `11101110` | `01110111` |

Thus, the bit stream on the medium is:

```text
11100010 00000100 11011000 01110100 00010000 01110111
```

### Transmission behavior

1. The transmitting station places the frame onto the shared Ethernet medium.
2. The physical signal is propagated so that all stations sharing that LAN can observe it.
3. Each receiving NIC examines the destination MAC address.
4. Only stations belonging to the multicast group accept and pass the frame upward.
5. Other stations discard the frame after recognizing that it is not addressed to them.

This is different from:

- **Unicast:** intended for one specific station.
- **Broadcast:** accepted by all stations on the local broadcast domain.
- **Multicast:** intended for a selected group of stations.

**Source:** Question Bank, p. 2, Module 3, Q3; Module 3 slide 5 / `Module3_Reference_PPT_rendered.pdf`, p. 5.

---

## M3-Q4. Analyze the following destination MAC addresses and determine whether each address represents a unicast, multicast, or broadcast destination. Justify your classification based on the address format. a. 4B:30:10:21:10:1A b. 48:20:1B:2E:08:EE c. FF:FF:FF:FF:FF:FF

The classification is determined by the least significant bit of the first octet.

| MAC address | First octet in binary | I/G bit | Classification | Reason |
|---|---|---:|---|---|
| `4B:30:10:21:10:1A` | `01001011` | 1 | **Multicast** | The least significant bit of `4B` is 1. |
| `48:20:1B:2E:08:EE` | `01001000` | 0 | **Unicast** | The least significant bit of `48` is 0. |
| `FF:FF:FF:FF:FF:FF` | `11111111:...:11111111` | 1 | **Broadcast** | All 48 bits are 1. |

Therefore:

1. `4B:30:10:21:10:1A` — **Multicast**
2. `48:20:1B:2E:08:EE` — **Unicast**
3. `FF:FF:FF:FF:FF:FF` — **Broadcast**

The first address is multicast because the second hexadecimal digit of its first octet is `B` (odd). The decisive bit is the **least significant bit of the entire first octet**, not the first hexadecimal digit.

**Source:** Question Bank, p. 2, Module 3, Q4; Module 3 slide 5 / `Module3_Reference_PPT_rendered.pdf`, p. 5. The result follows the correct I/G-bit interpretation.

---

## M3-Q5. Analyze the destination MAC address 47:20:1C:2A:08:EE and determine how a frame with this address would be transmitted on the network.

The destination address is:

```text
47:20:1C:2A:08:EE
```

Since:

```text
47₁₆ = 01000111₂
```

the least significant bit of the first octet is `1`. Therefore, the address is a **multicast address**.

### Bit sequence transmitted on the line

Each byte is sent from left to right, while the bits within each byte are sent least significant bit first.

| Address byte | Normal binary representation | Transmitted bit order |
|---|---|---|
| `47` | `01000111` | `11100010` |
| `20` | `00100000` | `00000100` |
| `1C` | `00011100` | `00111000` |
| `2A` | `00101010` | `01010100` |
| `08` | `00001000` | `00010000` |
| `EE` | `11101110` | `01110111` |

The transmitted destination-address bit stream is:

```text
11100010 00000100 00111000 01010100 00010000 01110111
```

### How the frame is handled

The frame is placed on the Ethernet medium and is observable by stations on that LAN. The NIC of each station checks the destination address:

- A station registered as a member of the corresponding multicast group accepts the frame.
- A station that is not a member of the group discards it.
- It is not delivered to only one individual station, as a unicast frame would be.
- It is not accepted by every station as a broadcast frame would be.

**Source:** Question Bank, p. 2, Module 3, Q5; Module 3 slide 5 / `Module3_Reference_PPT_rendered.pdf`, p. 5.

---

## M3-Q6. In the Standard Ethernet with the transmission rate of 10 Mbps, we assume that the length of the medium is 2500 m and the size of the frame is 512 bits. The propagation speed of a signal in a cable is normally 2 × 10⁸ m/s.

### Given

\[
R = 10\ \text{Mbps} = 10 \times 10^6\ \text{bits/s}
\]

\[
L = 2500\ \text{m}
\]

\[
\text{Frame size} = 512\ \text{bits}
\]

\[
v = 2 \times 10^8\ \text{m/s}
\]

### 1. Frame transmission time

\[
T_{\text{tx}}=\frac{\text{frame size}}{\text{transmission rate}}
\]

\[
T_{\text{tx}}=\frac{512}{10\times10^6}
=51.2\times10^{-6}\ \text{s}
\]

\[
\boxed{T_{\text{tx}}=51.2\ \mu s}
\]

### 2. One-way propagation time

\[
T_{\text{prop}}=\frac{\text{medium length}}{\text{propagation speed}}
\]

\[
T_{\text{prop}}=\frac{2500}{2\times10^8}
=12.5\times10^{-6}\ \text{s}
\]

\[
\boxed{T_{\text{prop}}=12.5\ \mu s}
\]

The round-trip propagation time is:

\[
2T_{\text{prop}}=2(12.5)=25\ \mu s
\]

\[
\boxed{2T_{\text{prop}}=25\ \mu s}
\]

### 3. Ethernet timing parameter

The ratio of propagation time to frame transmission time is:

\[
a=\frac{T_{\text{prop}}}{T_{\text{tx}}}
=\frac{12.5}{51.2}
\approx0.244
\]

\[
\boxed{a\approx0.24}
\]

### 4. Collision-detection assessment

For CSMA/CD to detect a collision reliably, the transmitting station must still be transmitting when a possible collision signal returns:

\[
T_{\text{tx}}\geq 2T_{\text{prop}}
\]

Here:

\[
51.2\ \mu s > 25\ \mu s
\]

Therefore, the condition is satisfied:

\[
\boxed{\text{Collision detection is possible for the stated 512-bit frame.}}
\]

Equivalently, the minimum frame size required at this rate and distance is:

\[
R(2T_{\text{prop}})
=(10\times10^6)(25\times10^{-6})
=250\ \text{bits}
\]

Since 512 bits is greater than 250 bits, the frame is long enough.

### 5. Efficiency

Using the usual approximate Ethernet efficiency expression:

\[
\eta \approx \frac{1}{1+2a}
\]

\[
\eta \approx \frac{1}{1+2(0.244)}
=\frac{1}{1.488}
\approx0.672
\]

\[
\boxed{\eta\approx67.2\%}
\]

The question statement does not explicitly state which efficiency formula is required. If the intended quantity is only the timing ratio, the unambiguous result is \(a\approx0.24\). The approximate efficiency obtained from the standard expression is 67.2%; a 39% value sometimes associated with this slide is not consistent with \(a=0.24\) and is therefore not used.

**Source:** Question Bank, p. 2, Module 3, Q6; Module 3 slide 5 / `Module3_Reference_PPT_rendered.pdf`, p. 5. The collision-detection condition and efficiency calculation are stated explicitly here to resolve the abbreviated wording of the question.

---

## M3-Q7. In the Standard Ethernet with the transmission rate of 12 Mbps, we assume that the length of the medium is 1500 m and the size of the frame is 512 bits. The propagation speed of a signal in a cable is normally 3 × 10⁸ m/s.

**Technical note:** Standard Ethernet is normally 10 Mbps; the following calculation uses the **12 Mbps rate stated in the question**.

### Given

\[
R = 12\ \text{Mbps} = 12 \times 10^6\ \text{bits/s}
\]

\[
L = 1500\ \text{m}
\]

\[
\text{Frame size} = 512\ \text{bits}
\]

\[
v = 3 \times 10^8\ \text{m/s}
\]

### 1. Frame transmission time

\[
T_{\text{tx}}=\frac{512}{12\times10^6}
=42.6667\times10^{-6}\ \text{s}
\]

\[
\boxed{T_{\text{tx}}\approx42.67\ \mu s}
\]

### 2. One-way propagation time

\[
T_{\text{prop}}=\frac{1500}{3\times10^8}
=5\times10^{-6}\ \text{s}
\]

\[
\boxed{T_{\text{prop}}=5\ \mu s}
\]

The round-trip propagation time is:

\[
2T_{\text{prop}}=2(5)=10\ \mu s
\]

\[
\boxed{2T_{\text{prop}}=10\ \mu s}
\]

### 3. Ethernet timing parameter

\[
a=\frac{T_{\text{prop}}}{T_{\text{tx}}}
=\frac{5}{42.6667}
\approx0.1172
\]

\[
\boxed{a\approx0.117}
\]

### 4. Collision-detection assessment

The CSMA/CD requirement is:

\[
T_{\text{tx}}\geq2T_{\text{prop}}
\]

Substitution gives:

\[
42.67\ \mu s > 10\ \mu s
\]

Hence:

\[
\boxed{\text{Collision detection is possible for the stated 512-bit frame.}}
\]

The minimum frame size required would be:

\[
R(2T_{\text{prop}})
=(12\times10^6)(10\times10^{-6})
=120\ \text{bits}
\]

The specified 512-bit frame is considerably longer than this minimum.

### 5. Efficiency

Using the standard approximate expression:

\[
\eta\approx\frac{1}{1+2a}
\]

\[
\eta\approx\frac{1}{1+2(0.1172)}
=\frac{1}{1.2344}
\approx0.810
\]

\[
\boxed{\eta\approx81.0\%}
\]

The question gives the numerical parameters but does not explicitly say whether to calculate \(T_{\text{tx}}\), \(T_{\text{prop}}\), \(a\), efficiency, or all of them. The complete timing assessment above reports each relevant quantity. The collision-detection conclusion follows directly from comparing the frame transmission time with twice the propagation time.

**Source:** Question Bank, p. 2, Module 3, Q7; Module 3 slide 5 / `Module3_Reference_PPT_rendered.pdf`, p. 5.

---

## M3-Q8. Explain the implementation of Standard Ethernet with the help of a neat diagrams.

Standard Ethernet operates at 10 Mbps and was implemented using several physical media and topologies. The important implementations are **10Base5, 10Base2, 10Base-T, and 10Base-F**. The MAC frame format and the CSMA/CD access method remain common, while the physical medium and connection arrangement differ.

### 1. 10Base5 — Thick Ethernet or Thicknet

10Base5 uses thick coaxial cable in a **bus topology**. Each station is connected to the coaxial cable through an external transceiver and a tap.

```text
Station A         Station B         Station C         Station D
    │                 │                 │                 │
Transceiver       Transceiver       Transceiver       Transceiver
    │                 │                 │                 │
   Tap               Tap               Tap               Tap
════╧═════════════════╧═════════════════╧═════════════════╧════
                 Thick coaxial backbone (bus)
```

Each station reaches the backbone through its own transceiver cable, external transceiver, and tap.

**Characteristics**

- Thick coaxial cable.
- Bus topology.
- External transceiver connected through a tap.
- The transceiver transmits, receives, and detects collisions.
- One cable segment is limited to 500 m.
- Up to five segments can be interconnected using repeaters when a longer LAN is needed.

### 2. 10Base2 — Thin Ethernet or Cheapernet

10Base2 also uses a **bus topology**, but it uses thinner, more flexible coaxial cable. The transceiver is normally integrated into the station’s NIC.

```text
Station A        Station B        Station C        Station D
   │                │                │                │
   T                T                T                T
   └────────────────┴────────────────┴────────────────┘
              Thin coaxial cable (bus)
```

**Characteristics**

- Thin coaxial cable.
- Bus topology.
- T-connectors attach stations to the cable.
- Transceiver is generally part of the NIC.
- Maximum segment length is approximately 185 m.
- It is less expensive and simpler to install than 10Base5.
- Collisions occur in the shared thin-coaxial medium.

### 3. 10Base-T — Twisted-Pair Ethernet

10Base-T uses a **physical star topology**. Each station has a point-to-point connection to a central hub.

```text
                       Station A
                           │
                           │
Station B ─────────────── Hub ─────────────── Station C
                           │
                           │
                       Station D
```

Each station uses two pairs of twisted cable:

```text
Station NIC ═════ pair 1 ═══► Hub
Station NIC ◄════ pair 2 ════ Hub
```

**Characteristics**

- Twisted-pair cable.
- Physical star topology.
- Two pairs provide separate transmit and receive paths.
- Maximum station-to-hub cable length is 100 m.
- The hub acts as the shared collision point; collisions occur in the hub.
- The hub is a multiport repeater and forwards the signal to the other ports.

### 4. 10Base-F — Fiber Ethernet

10Base-F uses optical fiber in a **star topology**. Each station is connected to a central hub using two fiber-optic cables.

```text
                       Station A
                       ╱       ╲
                      ╱         ╲
                fiber transmit/receive
                    ╱             ╲
Station B ═══════ Fiber Hub ═══════ Station C
                      ╲         ╱
                       ╲       ╱
                       Station D
```

**Characteristics**

- Optical-fiber medium.
- Star topology.
- Two fibers are used for the two transmission directions.
- Suitable for longer-distance and electrically noise-sensitive LAN links.
- Stations connect to a central fiber hub.

### Comparison

| Implementation | Medium | Topology | Main connecting device | Collision location |
|---|---|---|---|---|
| **10Base5** | Thick coaxial cable | Bus | External transceiver and tap | Shared coaxial cable |
| **10Base2** | Thin coaxial cable | Bus | T-connector; transceiver in NIC | Shared coaxial cable |
| **10Base-T** | Twisted pair | Star | Hub | Hub/shared half-duplex domain |
| **10Base-F** | Optical fiber | Star | Fiber hub | Shared hub domain in half-duplex operation |

The principal devices used in these implementations are the **NIC**, external **transceiver**, **tap**, **T-connector**, **hub**, and **repeater**. Modern switched Ethernet generally uses point-to-point full-duplex links, but the original Standard Ethernet implementations used CSMA/CD on shared media.

**Source:** Question Bank, p. 2, Module 3, Q8; Module 3 slide 6 / `Module3_Reference_PPT_rendered.pdf`, p. 6; slide 7 / PDF p. 7; slide 8 / PDF p. 8; and the Standard/Fast/Gigabit comparison on slide 12 / PDF p. 12.
