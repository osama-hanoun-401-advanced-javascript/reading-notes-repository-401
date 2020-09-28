## TCP Servers

**Event Queues**

- Much of the NodeJS architecture is built around the use of events. All objects that emit events in NodeJS are instances of the `EventEmitter` constructor. EventEmitters are a great way to handle controlling asynchronous events. Functions can be registered as listeners for an event on instances of the EventEmitter class. These instances can emit events and pass the listener's data.

- In practical applications, multiple "disconnected" services can communicate with one another using various protocols using proprietary APIs. Generally, this is done through a central "Hub" server (or Queue) which receives all inbound messages, scrubs the content, and then broadcasts those messages to connected subscribers.

**OSI Model**

- Programmers and engineers have been able to network computers since the early 1970s. As the needs of networked computers evolved, there were many solutions developed to connect two or more computers together and share information between them. Over time, several different conceptual models have also been developed to help describe the different networking solutions. In the mid 1980s the *"Open Systems Interconnection Reference Model"* (OSI Model) was developed as a seven layer model. This seven layer OSI model has continued to accurately describe the different processes in computer networking, and is still widely used as a point of reference while working in networked systems today. A developer or engineer is usually responsible for the goals of a specific layer and communication with the layer above and below. Not every computer network solution uses all seven layers, for example HTTP skips the presentation and session layers and lives directly on top of the transport layer.

**Internet Protocol Suite**

- The internet Protocol Suite is the conceptual model for the protocols used by the internet. It is often referred to as **TCP/IP** because the IP and the TCP were the original protocols in the suite. The Internet Protocol Suite is described using four layers - Link, Internet, Transport, and Application. Web developers often reference the Internet Protocol Suite model when discussing network communication and data exchange.

**TCP**

- The Transmission Control Protocol is widely used by applacation layer protocols in the Internet Protocol Suite. TCP creates a two way communication between two hosts and provides reliable, ordered, and error checked byte streams between the applications. TCP data transfers manage network congestion and use flow control to limit the rate a sender transfers data to guarantee reliable delivery. Each IP packet between the hosts carries a single TCP Segment. A TCP segment is made up of header and data sections.

**TCP Header**

- The TCP Header is used at each end to control the type of interaction being sent. It contains the following information:

  - a 16 bit `source port`

  - a 16 bit `destination port`

  - a 32 bit `sequence number` that sets the initial sequence number and manages the accumulated sequence number

  - if ACK is set, it contains a 32 bit `acknowledgement number` that is the next sequence number that the sender is expecting. It is used for acknowledging the bytes it has so far received

  - a 4 bit `data offset` specifies the size of the tcp header in 32 bit words

  - 9 flag bits

    - `NS` - an experimantal feature for a nonce sum - a nonce is a random cryptographic number used to prevent people from lying about who they are (authentication)

    - `CWR` - used to acknowledge that a TCP segment with the ECE flag has been received, and the Window has been reduced to alleviate congestion

    - `ECE` - if SYN is 1 it indicates that the peer is ECN capable, otherwise it is sued to indicate that there is network congestion

    - `URG` - indicates that the Urgent pointer filed is significant

    - `ACK` - indicates that the ACK fiel is significant - all packets after the initial SYN should have this flag set

    - `PSH` - used to ask to push the buffered data to the receiving application

    - `RST` - used to reset the connection

    - `SYN` sent only on the first packet sent from each end to synchronize the sequence numbers

    - `FIN` - indicates the last package from a sender, and is used in closing a connection

  - a 16 bit `window size`

  - a 16 bit `checksum` used for error checking the header

  - if URG is set it contains a 16 bit `urgent Pointer`

  - a variable 0 to 320 bit (divisible by 32) `options` section

**Connection Establishment**

- The client sends a SYN packet with a random sequence number. The server sends a SYN-ACK packet with the acknowledgement number set to one more than the initial sequence number. The client responds with and ACK and an acknowledgement number incremented by one.

**Connection Termination**

- One end sends a FIN segment and the other sends and ACK segment followed by a FIN segment. The termination initiation will then respond with an ACK segment.
