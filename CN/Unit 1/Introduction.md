# Unit 1: Foundations, Network Architecture, and Application Protocols

Welcome to Unit 1 of Computer Networks.

Most courses in computer science approach systems from the bottom up, beginning with physical voltages, electromagnetic frequencies, and link-layer framing before ever explaining why data is being moved. 

This coursework adopts the **Top-Down Approach** (pioneered by Kurose and Ross). We begin with the applications you interact with every day—web browsers, streaming video, email, and network sockets—and systematically peel back the underlying machinery:
1. What service does an application require from transport?
2. What does transport require from the global routing mesh?
3. How do physical communication links, packet switches, and queueing delays govern the speed of the entire system?

---

## Unit 1 Roadmap

The lectures in this unit trace the journey of network communication across eleven dedicated decks:

- [**L01: Introduction to Computer Networks and the Internet**](L01%20-%20Introduction%20to%20Computer%20Networks%20and%20the%20Internet.md) — Defining networks of autonomous devices, the nuts-and-bolts vs. service views of the Internet, the anatomy of network protocols, and the standards process (RFCs/IETF).
- [**L02: The Network Edge - Access Networks and Physical Media**](L02%20-%20The%20Network%20Edge%20-%20Access%20Networks%20and%20Physical%20Media.md) — End systems, residential access (DSL, Cable HFC, FTTH), enterprise Ethernet, wireless access (WiFi, 4G/5G), and guided vs. unguided physical media.
- [**L03: The Network Core - Packet Switching vs. Circuit Switching**](L03%20-%20The%20Network%20Core%20-%20Packet%20Switching%20vs%20Circuit%20Switching.md) — Store-and-forward packet switching, queueing delays, forwarding vs. routing, circuit switching (FDM/TDM), and the statistical multiplexing advantage.
- [**L04: Network Core Structure and ISP Interconnection**](L04%20-%20Network%20Core%20Structure%20and%20ISP%20Interconnection.md) — The $N(N-1)/2$ mesh dilemma, the multi-tier ISP hierarchy (Tier-1 transit, Regional ISPs, Access ISPs), peering agreements, Internet Exchange Points (IXPs), and private Content Provider Networks (Google, Meta, Netflix).
- [**L05: Delay, Loss, and Throughput in Packet Networks**](L05%20-%20Delay%2C%20Loss%2C%20and%20Throughput%20in%20Packet%20Networks.md) — The four sources of nodal delay ($d_{\text{proc}}, d_{\text{queue}}, d_{\text{trans}}, d_{\text{prop}}$), the car-caravan analogy, traffic intensity ($La/R$), traceroute mechanics, packet loss, and bottleneck throughput.
- [**L06: Protocol Layering and the Internet Stack**](L06%20-%20Protocol%20Layering%20and%20the%20Internet%20Stack.md) — Why systems require modular layers, the 5-layer Internet stack vs. the 7-layer OSI reference model, Protocol Data Units (PDUs), and the lifecycle of encapsulation and decapsulation.
- [**L07: Network Hardware Devices**](L07%20-%20Network%20Hardware%20Devices.md) — Structural hardware progression from Layer 1 through Layer 7: repeaters, hubs, modems, bridges, switches, network interface cards (NICs), routers, NAT gateways, and firewalls; collision domains vs. broadcast domains.
- [**L08: End-to-End Delay and Throughput Numerical Problems**](L08%20-%20End-to-End%20Delay%20and%20Throughput%20Numerical%20Problems.md) — Step-by-step mathematical solutions and analytical proofs for multi-hop delay, queueing dynamics, binomial probability of packet switching, and shared bottleneck flows.
- [**L09: Application Layer Principles**](L09%20-%20Application%20Layer%20Principles.md) — Network application architectures (Client-Server vs. P2P), communicating processes, socket programming abstractions, transport service requirements (loss, throughput, timing, security), and the TCP vs. UDP service contract.
- [**L10: The Web and HTTP**](L10%20-%20The%20Web%20and%20HTTP.md) — Hypertext Transfer Protocol, web pages and objects, HTTP statelessness, non-persistent vs. persistent connections (RTT calculations), HTTP request/response headers, status codes, and packet traces.
- [**L11: HTTPS, Cookies, and Web Caching**](L11%20-%20HTTPS%2C%20Cookies%2C%20and%20Web%20Caching.md) — Transport Layer Security (TLS handshake), state tracking over stateless protocols using Cookies, Web Caches / Forward Proxies, and the Conditional GET protocol.

---

The single habit that binds this entire unit together is **following a single packet**: ask who created it, what link it is waiting for, which device reads which header, which rate limits it, and what must happen before the receiving process can consume it.
