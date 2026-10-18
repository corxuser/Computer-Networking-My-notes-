# 1.1 What Is the Internet?

There are multiple ways to answer the question "What is the Internet?" One approach is to describe it in detail through its specific hardware and software components. Another approach is to view the Internet as a networking infrastructure that provides services to distributed applications. Let us begin our discussion with a hardware and software description using **Figure 1.1**.

## 1.1.1 A Nuts-and-Bolts Description

The Internet is a global computer network connecting billions of computing devices worldwide.

<img width="640" height="913" alt="image" src="https://github.com/user-attachments/assets/4ceee03a-8c27-43fd-8d84-ec6c3476debb" />

*Figure 1.1: A nuts-and-bolts description of the Internet.*

In Internet terminology, all of these connected devices are referred to as **hosts** or **end systems**. End systems are interconnected by a network of **communication links** and **packet switches**.

### Key Concepts

* **Transmission Rate:** Different links transmit data at different speeds, with the transmission rate measured in bits per second (bps).

* **Packets:** When one end system needs to send data to another, the sending end system breaks the data into segments and adds header bytes to each segment. These resulting data units are called **packets** in computer networking terminology. The packets are then transmitted through the network to the destination end system, where they are reassembled into the original data.

* **Packet Switching:** A packet switch takes a packet arriving on one of its incoming communication links and forwards it onto one of its outgoing communication links.

  * The two most common types of packet switches on the Internet are **routers** and **link-layer switches**. Both types forward packets toward their ultimate destinations.

  * **Link-layer switches** are typically used in access networks.

  * **Routers** are typically used in the network core.

* **Network Path (Route):** The sequence of communication links and packet switches traversed by a packet from the sending end system to the receiving end system is known as a **network path** or **route**.

### Internet Service Providers (ISPs)

End systems access the Internet through **Internet Service Providers (ISPs)**. Because the main purpose of the Internet is to interconnect end systems, the ISPs providing access to these end systems must also be interconnected with one another. Upper-tier ISPs consist of high-speed routers interconnected by high-speed fiber-optic links.

---

## 1.1.2 A Services Description

While the discussion above identifies many of the components that comprise the Internet, we can also describe the Internet from a completely different perspective: as an infrastructure that provides services to applications.

* **Distributed Applications:** These applications are called distributed applications because they involve multiple end systems exchanging data with each other.

* **Location of Execution:** Internet applications run on end systems—they do not run on packet switches within the network core.

* **Socket Interface:** How does a program running on one end system instruct the Internet to deliver data to a program running on another end system? The **Internet Socket Interface** is a set of rules that the sending program must follow so that the Internet can deliver the data to the destination program.

Thus, the Internet can be described in two complementary ways:

1. In terms of its **hardware and software components**.
2. In terms of an **infrastructure providing services to distributed applications**.

---

## 1.1.3 What Is a Protocol?

### A Human Analogy

To understand the concept of a computer network protocol, it is often easiest to consider a human analogy first, as humans execute human network protocols continuously.

In a human protocol, we send specific messages and take specific actions based on the responses we receive or other events (such as the absence of a response within a certain timeframe).

![Uploading image.png…]()



*Figure 1.2: A human protocol and a computer network protocol.*

### Network Protocols

A network protocol is similar to a human protocol, except that the entities exchanging messages and taking actions are hardware or software components of a device (e.g., a computer, smartphone, tablet, router, or other network-capable device). All activities on the Internet involving two or more communicating entities are governed by protocols.

**Examples of protocols in action:**

* **Hardware-implemented protocols** in physically connected computers control the flow of bits on the wire between two network interface cards (NICs).

* **Congestion-control protocols** in end systems govern the rate at which packets are transmitted between sender and receiver.

* **Routing protocols** in routers determine a packet’s path from source to destination.

#### Example: Web Request Scenario

Consider what happens when you make a request to a web server by typing a Web page URL into your browser (as shown on the right side of Figure 1.2):

1. **Connection Request:** Your computer sends a TCP connection request message to the web server and waits for a response.

2. **Connection Reply:** The web server receives the connection request message and returns a connection reply message.

3. **HTTP GET Request:** Knowing that it is now safe to request the document, your computer sends an HTTP `GET` message containing the name of the web page it wishes to fetch.

4. **File Response:** Finally, the web server returns the web page (file) to your computer.

### Definition of a Protocol

> **Protocol Definition:** A protocol defines the format and order of messages exchanged between two or more communicating entities, as well as the actions taken upon the transmission and/or receipt of a message or other events.
