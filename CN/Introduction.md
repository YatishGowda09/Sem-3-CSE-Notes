# Introduction to Computer Networks

## What is a Computer Network?

A computer network is an interconnected collection of autonomous computing devices (end systems, switches, routers, and servers) communicating over physical and wireless transmission links to exchange data and share hardware and software resources.

---

## What is the Internet?

In simple terms, the **Internet is a network of networks**. It connects billions of independently administered, heterogeneous devices that agree on common standards and protocols for addressing, packet formatting, routing, and traffic exchange.

*Note:* A lowercase `internet` denotes any private collection of two or more interconnected networks. The capitalized `Internet` refers specifically to the public, global communication system.

---

## The Internet: Nuts-and-Bolts vs. Service Views

The Internet can be understood from two distinct viewpoints:

1. **The Nuts-and-Bolts View (Infrastructure)**:
   - **Network Edge**: End systems (hosts) including smartphones, laptops, servers, and IoT devices running network applications.
   - **Access Networks**: The physical cabling and transmission links (DSL, Cable HFC, FTTH, Wi-Fi, 4G/5G) connecting end systems to their first router.
   - **Network Core**: The global mesh of interconnected packet switches (routers and switches) and high-capacity communication links that transport packets between endpoints.

2. **The Service View (Application Platform)**:
   - From the programmer's perspective, the Internet is an infrastructure that provides communication services to distributed applications (the Web, video streaming, email, multiplayer gaming).
   - It exposes the **Socket Application Programming Interface (API)**, allowing user-space processes to send and receive data without needing to manage low-level routing, link voltages, or queueing mechanics.

---

## Coursework Vault Navigation

This study vault organizes the entire Computer Networks curriculum across four comprehensive units, following the **Top-Down Approach**:

- [**Master Curriculum Index & Architecture Map (README.md)**](README.md)
- [**Unit 1: Foundations, Network Architecture, and Application Protocols**](Unit%201/Introduction.md)
- [**Unit 2: Application Infrastructure, Sockets, and Transport-Layer Reliability**](Unit%202/Introduction.md)
- [**Unit 3: Transport Congestion Control, the Network Data Plane, and IP**](Unit%203/Introduction.md)
- [**Unit 4: Control Plane, Link Layer, LANs, and Physical/Wireless**](Unit%204/Introduction.md)
