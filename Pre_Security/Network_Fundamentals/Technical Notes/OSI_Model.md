# OSI Model – TryHackMe

## 1. What is the OSI Model?

### What It Is

The OSI model (or Open Systems Interconnection Model) is an essential model used in networking.  This critical model provides a framework dictating how all networked devices will send, receive and interpret data.

### How It Works

One of the main benefits of the OSI model is that devices can have different functions and designs on a network while communicating with other devices. Data sent across a network that follows the uniformity of the OSI model can be understood by other devices.
The OSI model consists of seven layers. Each layer has a different set of responsibilities and is arranged from Layer 7 to Layer 1.

## 2. Layer one (Physical)
This layer references the physical components of the hardware used in networking and is the lowest layer.
Devices use electrical signals to transfer data between each other in a binary numbering system (1's and 0's).

## 3. Layer two (Data Link)
The data link layer focuses on the physical addressing of the transmission. It receives a packet from the network layer (including the IP address for the remote computer) and adds in the physical MAC (Media Access Control) address of the receiving endpoint. Inside every network-enabled computer is a Network Interface Card (NIC) which comes with a unique MAC address to identify it.

## 4. Layer three (Network)
Routing simply determines the most optimal path in which these chunks of data should be sent. These protocols include OSPF (Open Shortest Path First) and RIP (Routing Information Protocol). 
**The factors that decide what route is taken is decided by the following:**
- What path is the shortest? I.e. has the least amount of devices that the packet needs to travel across.
- What path is the most reliable? I.e. have packets been lost on that path before?
- Which path has the faster physical connection? I.e. is one path using a copper connection (slower) or a fibre (considerably faster)?

## 5. Layer four (Transport)
When data is sent between devices, it follows one of two different protocols that are decided based upon several factors:
- **TCP (Transmission Control Protocol)**: This protocol reserves a constant connection between the two devices for the amount of time it takes for the data to be sent and received.
    ### Advantages
    - Guarantees the accuracy of data.
    - Capable of synchronising two devices to prevent each other from being flooded with data.
    - Performs a lot more processes for reliability. 

    ### Disadvantages
    - Requires a reliable connection between the two devices. If one small chunk of data is not received, then the entire chunk of data cannot be used.
    - A slow connection can bottleneck another device as the connection will be reserved on the receiving computer the whole time.
    - TCP is significantly slower than UDP because more work has to be done by the devices using this protocol.
TCP is used for situations such as file sharing, internet browsing or sending an email. This usage is because these services require the data to be accurate and complete

- **UDP (User Datagram Protocol)**: Any data that gets sent via UDP is sent to the computer whether it gets there or not. There is no synchronisation between the two devices or guarantee; just hope for the best, and fingers crossed.
    ### Advantages
    - UDP is much faster than TCP.
    - UDP leaves the application layer (user software) to decide if there is any control over how quickly packets are sent.
    - UDP does not reserve a continuous connection on a device as TCP does.

    ### Disadvantages
    - UDP doesn't care if the data is received.

## 6. Layer five (Session)
Once data has been correctly translated or formatted from the presentation layer (layer 6), the session layer (layer 5) will begin to create and maintain the connection to other computer for which the data is destined. When a connection is established, a session is created. Whilst this connection is active, so is the session.
The session layer is also responsible for closing the connection if it hasn't been used in a while or if it is lost. Additionally, a session can contain "checkpoints," where if the data is lost, only the newest pieces of data are required to be sent, saving bandwidth. 
What is worthy of noting is that sessions are unique — meaning that data cannot travel over different sessions, but in fact, only across each session instead.

## 7. Layer six (Presentation)
Layer 6 of the OSI model is the layer in which standardisation starts to take place. Because software developers can develop any software such as an email client differently, the data still needs to be handled in the same way — no matter how the software works. Security features such as data encryption (like HTTPS when visiting a secure site) occur at this layer.

## 8. Layer seven (Application)
The application layer of the OSI model is the layer that you will be most familiar with. This familiarity is because the application layer is the layer in which protocols and rules are in place to determine how the user should interact with data sent or received.
Everyday applications such as email clients, browsers, or file server browsing software such as FileZilla provide a friendly, Graphical User Interface (GUI) for users to interact with data sent or received. Other protocols include DNS (Domain Name System), which is how website addresses are translated into IP addresses.