# Unit 4: Routing Control, Link Layer Protocols, Local Area Networks, and Physical Foundations

Welcome to Unit 4 of Computer Networks.

In Units 1, 2, and 3, we descended the protocol stack:
- We started at the **Application Layer**, examining how user programs communicate via HTTP, DNS, P2P, and socket APIs.
- We crossed into the **Transport Layer**, constructing reliable data transfer (`rdt`) and mastering TCP Congestion Control (AIMD).
- We entered the **Network Layer Data Plane**, exploring router hardware, TCAM lookups, IPv4 headers, fragmentation, subnetting, and Software-Defined Networking.

In Unit 4, we complete our journey across the remaining layers of the Internet architecture.

First, we resolve the great unanswered question of the network layer: **how do routers actually discover the topology and compute optimal end-to-end paths?** We explore the **Control Plane** through Link-State (Dijkstra) and Distance-Vector (Bellman-Ford) routing algorithms, examine diagnostic protocols like **ICMP**, and dissect the next-generation architecture of **IPv6**.

Next, we cross the boundary into **Layer 2: The Link Layer**. Here, we investigate how raw datagrams are framed, protected against physical bit flips via **Cyclic Redundancy Checks (CRC)**, and transmitted across shared media using **Multiple Access Protocols (CSMA/CD and CSMA/CA)**. We study the operation of **Ethernet switches**, self-learning algorithms, and **VLANs**.

We bring our entire study together in a grand pedagogical capstone: **A Day in the Life of a Web Page Request**, tracing every single protocol interaction from the moment a laptop plugs into an Ethernet port to the rendering of an HTML page.

Finally, we descend into **Layer 1: The Physical Layer** and **Wireless LANs**, exploring Shannon's capacity limit, modulation schemes, and 802.11 Wi-Fi.

---

## Unit 4 Roadmap

The lectures in this unit are structured across eleven dedicated decks:

- [**L01: ICMP and DHCP in the Network Layer**](L01%20-%20ICMP%20and%20DHCP%20in%20the%20Network%20Layer.md) — Network diagnostics and host auto-configuration. ICMP architecture (Type and Code fields); `ping` (Echo Request/Reply); `traceroute` mechanics exploiting TTL expiration; DHCP review in Layer 3 bootstrapping.
- [**L02: IPv6 Architecture and Transition Strategies**](L02%20-%20IPv6%20Architecture%20and%20Transition%20Strategies.md) — The 128-bit address space; colon-hexadecimal notation and zero-compression rules; fixed 40-byte base header; elimination of checksums, options, and router-side fragmentation; transition strategies: Dual Stack and IPv6-in-IPv4 Tunneling.
- [**L03: Routing Algorithms - Link-State and Dijkstra**](L03%20-%20Routing%20Algorithms%20-%20Link-State%20and%20Dijkstra.md) — Global vs. decentralized routing; graph abstraction $G=(V,E)$; Link-State broadcast; Dijkstra's Shortest Path Algorithm: step-by-step table derivation ($N', D(v), p(v)$), computational complexity, and oscillation hazards.
- [**L04: Routing Algorithms - Distance-Vector and Hierarchical Routing**](L04%20-%20Routing%20Algorithms%20-%20Distance-Vector%20and%20Hierarchical%20Routing.md) — Bellman-Ford algorithm ($D_x(y) = \min_v \{ c(x,v) + D_v(y) \}$); iterative, asynchronous vector updates; the Count-to-Infinity problem and Poisoned Reverse heuristic; Link-State vs. Distance-Vector trade-offs; Autonomous Systems (AS), Intra-AS (OSPF) vs. Inter-AS (BGP) routing.
- [**L05: Link Layer Overview, Framing, and ARP**](L05%20-%20Link%20Layer%20Overview%2C%20Framing%2C%20and%20ARP.md) — Node-to-node frame delivery across single links; Network Interface Cards (NICs); 48-bit MAC addresses; Address Resolution Protocol (ARP, RFC 826): translating IP to MAC on local subnets, broadcast requests, unicast replies, and ARP cache timeouts.
- [**L06: Error Detection and Correction Techniques (Parity, Checksum, CRC)**](L06%20-%20Error%20Detection%20and%20Correction%20Techniques%20%28Parity%2C%20Checksum%2C%20CRC%29.md) — Protecting bit integrity across noisy links; single-bit parity vs. two-dimensional parity (error correction); mathematical mechanics of Cyclic Redundancy Checks (CRC): polynomial division in Galois Field Modulo-2 arithmetic, generator polynomials, and hardware shift registers.
- [**L07: Multiple Access Protocols (Channel Partitioning, Random Access, Taking Turns)**](L07%20-%20Multiple%20Access%20Protocols%20%28Channel%20Partitioning%2C%20Random%20Access%2C%20Taking%20Turns%29.md) — Broadcast channels and collision domains; Channel Partitioning (TDMA, FDMA, CDMA orthogonal chip codes); Random Access (Pure ALOHA, Slotted ALOHA, CSMA, CSMA/CD with binary exponential backoff); Taking-Turns (Polling, Token Passing).
- [**L08: Switched Local Area Networks, Ethernet, and VLANs**](L08%20-%20Switched%20Local%20Area%20Networks%2C%20Ethernet%2C%20and%20VLANs.md) — Ethernet frame structure (preamble, MACs, type, CRC-32); Ethernet switches vs. hubs; self-learning switch tables (filtering, forwarding, flooding); loop prevention; Virtual LANs (VLANs, 802.1Q trunking).
- [**L09: Synthesis - A Day in the Life of a Web Page Request**](L09%20-%20Synthesis%20-%20A%20Day%20in%20the%20Life%20of%20a%20Web%20Page%20Request.md) — The ultimate end-to-end integration: DHCP IP acquisition $\to$ ARP gateway resolution $\to$ DNS query routing $\to$ TCP three-way handshake $\to$ HTTP GET request $\to$ web page reception.
- [**L10: Physical Layer Fundamentals, Modulation, and Bandwidth Limits**](L10%20-%20Physical%20Layer%20Fundamentals%2C%20Modulation%2C%20and%20Bandwidth%20Limits.md) — Transmission media (twisted pair, coaxial, optical fiber, wireless spectrum); analog vs. digital signals; physical channel impairments (attenuation, distortion, thermal noise); Nyquist Maximum Data Rate formula vs. Shannon Channel Capacity Theorem; digital modulation (ASK, FSK, PSK, QAM).
- [**L11: Wireless LANs, 802.11 Wi-Fi, and Mobility**](L11%20-%20Wireless%20LANs%2C%20802.11%20Wi-Fi%2C%20and%20Mobility.md) — Wireless challenges: path loss, interference, multipath fading; why CSMA/CD fails in wireless; Hidden Terminal and Exposed Terminal problems; CSMA/CA protocol (DIFS, SIFS, link ACKs); RTS/CTS frame reservation; 802.11 frame format and the 4 MAC address fields; cellular mobility.

---

The mental model uniting Unit 4 is **closing the loop**: from the algorithmic brains of global routing to the physical photons vibrating across optical fibers, every layer works in synchronized harmony to move human information across the globe.
