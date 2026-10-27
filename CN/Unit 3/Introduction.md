zs# Unit 3: Transport Congestion Control, the Network Data Plane, and IP

Welcome to Unit 3 of Computer Networks.

In Unit 2, we examined how transport protocols provide reliable, process-to-process communication across an inherently unreliable packet network. We developed the principles of reliable data transfer (`rdt 1.0` through `rdt 3.0`) and proved that pipelining is essential to achieve high throughput across long-distance links.

However, pipelining introduces an immediate existential danger: **Congestion**.

If every host transmits hundreds of packets into the network as fast as its local link allows, intermediate routers become overwhelmed. Queue buffers overflow, packets are dropped, latency skyrockets toward infinity, and the network suffers a catastrophic throughput collapse.

In Unit 3, we complete the transport layer by studying **TCP Congestion Control**, and then cross the grand boundary into **Layer 3: The Network Layer**.

Here, we explore the machinery that powers global packet forwarding:
1. The fundamental division of the network layer into the **Data Plane** (hardware-accelerated, nanosecond packet forwarding) and the **Control Plane** (software-driven, millisecond path calculation).
2. The physical anatomy of modern high-speed routers: input ports, output ports, and the evolution of switching fabrics (memory, bus, and crossbar).
3. The foundational protocol of the global Internet: **IPv4**, its 20-byte header, fragmentation mechanics across heterogeneous MTUs, and classless inter-domain routing (**CIDR**).
4. Address conservation and edge privacy via **Network Address Translation (NAT)**.
5. The modern revolution in network architecture: **Generalized Forwarding** and **Software-Defined Networking (SDN)** via OpenFlow.

---

## Unit 3 Roadmap

The lectures in this unit are structured across nine dedicated decks:

- [**L01: TCP Congestion Control and Flow Control**](L01%20-%20TCP%20Congestion%20Control%20and%20Flow%20Control.md) — Principles of network congestion; three analytical scenarios of congestion costs; end-to-end vs. network-assisted congestion control; Additive Increase Multiplicative Decrease (AIMD); Slow Start, Congestion Avoidance, Fast Retransmit, and Fast Recovery; complete state machine evolution from TCP Tahoe to TCP Reno.
- [**L02: Network Layer Overview - Data Plane vs. Control Plane**](L02%20-%20Network%20Layer%20Overview%20-%20Data%20Plane%20vs%20Control%20Plane.md) — Network layer service models; host-to-host datagram delivery; forwarding vs. routing; the architectural separation between the per-router data plane (nanosecond hardware lookup) and the control plane (distributed routing algorithms vs. logically centralized controllers).
- [**L03: Router Architecture and Input Output Ports**](L03%20-%20Router%20Architecture%20and%20Input%20Output%20Ports.md) — High-level router anatomy; input port processing pipeline (physical termination, data link decapsulation, lookup engine); ternary content-addressable memory (TCAM); Longest Prefix Matching (LPM); input buffer queueing and Head-of-Line (HOL) blocking.
- [**L04: Switching Fabrics and Queuing**](L04%20-%20Switching%20Fabrics%20and%20Queuing.md) — The physical core of the router; switching via memory, shared bus, and crossbar interconnects; scaling switching rate to $N \times R$; output port buffering; buffer sizing rule-of-thumb ($RTT \times C / \sqrt{N}$); packet scheduling disciplines (FIFO, Priority, Round Robin, Weighted Fair Queuing).
- [**L05: IPv4 Datagram Format and Protocol Fields**](L05%20-%20IPv4%20Datagram%20Format%20and%20Protocol%20Fields.md) — Complete breakdown of the 20-byte IPv4 header; Version, IHL, Type of Service / DSCP, Total Length, Identification, DF and MF flags, Fragment Offset, TTL hop-limit counter, Upper Layer Protocol demultiplexing, and Header Checksum.
- [**L06: IPv4 Fragmentation and Reassembly**](L06%20-%20IPv4%20Fragmentation%20and%20Reassembly.md) — Maximum Transmission Unit (MTU) boundaries; why intermediate routers fragment packets but only the destination host reassembles them; fragment offset math (8-byte units); step-by-step numerical fragmentation traces with headers and payloads.
- [**L07: IPv4 Addressing, Subnetting, and CIDR**](L07%20-%20IPv4%20Addressing%2C%20Subnetting%2C%20and%20CIDR.md) — 32-bit dotted-decimal notation; host and router interfaces; demise of classful addressing (Classes A, B, C); Classless Inter-Domain Routing (CIDR `/x`); subnet masks; route aggregation and address summarization; step-by-step subnet calculation problems.
- [**L08: Network Address Translation (NAT)**](L08%20-%20Network%20Address%20Translation%20%28NAT%29.md) — Private IPv4 address spaces (RFC 1918); NAT translation tables mapping internal private sockets to external public IP and port tuples; connection traversal; firewall benefits vs. architectural violations of the end-to-end principle and layer layering.
- [**L09: Generalized Forwarding and Software Defined Networking (SDN)**](L09%20-%20Generalized%20Forwarding%20and%20Software%20Defined%20Networking%20%28SDN%29.md) — Traditional per-router control plane vs. logically centralized SDN controllers; match-plus-action forwarding paradigm (OpenFlow); multi-field flow table matching; unifying routers, switches, NATs, and firewalls into programmable middleboxes.

---

The unifying theme across Unit 3 is **scale and mechanics**: how billions of packets moving through millions of independent networks can be throttled, switched, addressed, and forwarded at hardware wire speed without collapsing under global load.
