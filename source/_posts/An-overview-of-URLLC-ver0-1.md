---
title: An overview of URLLC ver0.1
date: 2020-09-11 21:33:38
tags: 
- URLLC
- wireless communication
- overview
- research
---

# **A preliminary understanding of URLLC**

<!--more-->

  A preliminary understanding of URLLC is summarized in the form of questions as follows.

## **a.**   **Definition: what is URLLC?**

  URLLC (ultra-reliable low-latency communications) is one of three primary 5G New Radio use cases defined by 3GPP. It requires ultra-reliability and low-latency service for mission critical communications. URLLC is not a kind of communication technology but a service class which needs a number of technology components including coding scheme, access scheme, channel resource allocation, network slicing and so on.

## **b.**   **Significance: why is it essential to study URLLC?**

  In the context of Industry 4.0, it is foreseeable that URLLC will be a potential enabler of a vast set of mission critical applications. Examples of URLLC use cases include remote surgery, industrial control, auto-driving and so on, all of which require stringent reliability and short latency down to the millisecond level.

## **c.**   **Motivation: why can’t current cellular network meet the requirements of URLLC?** 

  3GPP aims at realizing URLLC applications with ultra-low latency of 1ms and 10ms for user plane and control plane, respectively, and ultra-high reliability of more than 99.999% in terms of packet delivery performance [1]. However, current cellular network cannot meet these requirements due to a series of technical bottlenecks. For example, uplink transmissions are subject to resource reservation procedures with numerous stages and heavy signaling, which has a tremendous impact on latency and reliability.

## **d.**   **Improvements in standard: what improvements have been done to support URLLC in 3GPP standard?**

  To support URLLC in 5G NR, a series of techniques and specifications are introduced, including minimum scheduling unit (mini-slot), early data transmission and so on. In a nutshell, the main features introduced in 3GPP release 16 [2] to support URLLC include:

·     Redundant transmission for high-reliability communication,

·     QoS Monitoring,

·     Dynamic division of packet delay budget,

·     Enhancements of session continuity.

## **e.** **Related work: what related work has been done to improve the performance of URLLC?**

There is a rich literature on the topics of URLLC, from physical layer to transport layer, from theoretical analysis to system level simulations, and from simple URLLC scenarios to mixed scenarios.

![related_work](https://raw.githubusercontent.com/Zhaoxinran1999/RifleBlog.github.io/master/2020/09/11/An-overview-of-URLLC-ver0-1/related_work.png)

### **Physical layer**

  In order to satisfy URLLC requirements, new techniques in physical layer design are demanded. The problems in URLLC in physical layer design and a set of techniques specified in Release 16 are summarized in [3]. Improvements of detection techniques for short packet transmission are proposed in [4] and [5]. In [4], a multiuser MIMO wireless communication system is analytically studied. An approach where the channel estimation error is treated as a signal rather than noise, while the zero-forcing detection is applied at the receiver. [5] focuses on the critical industrial control scenario and proposes to use a short one-symbol PHY preamble for critical wireless industrial communications in order to reduce the transmission latency. To be mentioned, [5] is based on WLAN described in the IEEE 802.11 standard and it is still a question whether WLAN is an alternative to 5G NR for URLLC (more detailed description about this question is in Q5 of part Ⅱ).

  To implement ultra-reliability and low-latency, coding and decoding scheme, which has a huge impact on processing efficiency and error rate, is a basic issue. [6] indicates that, in current turbo decoder, a large number of processors remain idle when decoding short frame lengths. This paper proposes a novel turbo decoding algorithm that supports a high degree of parallel processing and lower processing latency. Further work is done in [7] where OFDM demodulation and a fully-parallel turbo decoding are executed concurrently, rather than consecutively, which reduces the processing time.

### **Link layer**

  Access networking represents a critical segment for development of URLLC services in cellular networks. [8] outlines two potential approaches to access protocol redesign, respectively grant-free access and coordinated grant-free access. It indicates that grant-based slotted ALOHA is not suitable for URLLC services and redundancy and diversity should be the principal approach to achieve reliability with low latency. [9] discusses in details the MAC protocols compared to [8]. It mainly focuses on use of large number of antennas in massive MIMO for providing high reliability and the concept of interface diversity and multi-connectivity.

  Grant-free scheme for short packet transmission is a heated topic and a vast set of literature [10-12] have worked on it. [10] proposed an uplink contention-based transmission scheme where multiple transmission for the same packet is applied to reduce collision probability. But only collision performance is conducted in the simulations and there is a lack of detailed analysis in reliability and latency in [10]. [11] provides an overview of grant-free random access in 5G NR focusing on URLLC and presents two reliability-enhancing solutions, retransmissions and NOMA, both of which rely on more channel resources or more complex receivers. [12] proposes a novel multi-channel ALOHA-type grant-free access scheme for mMTC/ URLLC terminals coexistence based on service-martingales theory. Results show that the proposed algorithm can meet the delay and reliability QoS of URLLCs and also support more terminals.

  To achieve reliability, redundant packets and retransmissions play a major role in data transmission. HARQ is one of widely-used retransmission schemes, but conventional HARQ cannot meet URLLC requirements [13] and several retransmission schemes are proposed in [13-14], both of which are performed in specified scenarios. [13] performs its analysis and simulations in a large urban macro network and [14] is only suitable for low load scenarios.

### **Higher layer**

  In addition to physical layer and link layer improvements, there are some work focusing on higher layer to achieve URLLC requirements. [15] indicates that the latency caused by dual-stack network significantly impacts the user experience. A novel connectivity mechanism, which redesigns the DNS resolution and TCP connection phases, reduces the user-perceived latency in the dual-stack network for mobile devices.

### **Edge computing**

  Fueled by the availability of more data and computing power, machine learning (ML) has transformed every aspect of our lives. It is a trend to apply ML in communications. One of heated topics is edge computing, which is always used to acquire an accurate knowledge of the RF environment. However, classical ML exerts severe demands in terms of energy, memory, and computing resources, limiting their adoption for resource-constrained edge devices, and the additional latency induced by the inference is ignored [16]. Thus, a novel paradigm calls for distributed, low-latency and reliable ML at the wireless network edge.

### **Mixed scenarios**

  Three tenets of 5G revolution are URLLC, mMTC and eMBB, each of which cannot be totally independent from others in practical applications. Thus, coexistence and combination of these requirements are discussed unavoidably.

  Coexistence means that terminals with different service classes have to share the channel resources and computing resources. For these scenarios, appropriate network slicing and resource allocation schemes are needed. [17] focuses on network slicing for URLLC/eMBB/mMTC coexistence and proposes a communication-theoretic model that accounts for the heterogeneous requirements. About resource scheduling, [18] provides a punctured scheduling solution for URLLC/eMBB coexistence where URLLC traffic punctures part of the ongoing eMBB transmissions to meet the requirements of both URLLC and eMBB, while [19] proposes a joint link adaptation and resource allocation policy.

  Novel application scenarios call for combinations of different requirements, such as critical mMTC in emerging use cases and scalable URLLC in driverless vehicles. To this end, [20] presents a review of URLLC within mMTC and proposes potential approaches to prospective critical mMTC solutions at different layers.

# References
[1] 3GPP, “Study on Scenarios and Requirements for Next Generation Access Technologies,” 3rd Generation Partnership Project (3GPP), TR 38.913 V0.3.0, Mar. 2016.
[2] 3GPP, “Technical Specification Group Services and System Aspects,” 3rd Generation Partnership Project (3GPP), TR 21.916 V0.5.0, July 2020.
[3] Le T K, Salim U, Kaltenberger F. An overview of physical layer design for Ultra-Reliable Low-Latency Communications in 3GPP Release 15 and Release 16[J]. arXiv preprint arXiv:2002.03713, 2020.
[4] Miridakis N I, Tsiftsis T A, Wang H M. Zero forcing detection for short packet transmission under channel estimation errors[J]. IEEE Transactions on Vehicular Technology, 2019, 68(7): 7164-7168.
[5] Jiang X, Pang Z, Zhan M, et al. Packet detection by a single OFDM symbol in URLLC for critical industrial control: A realistic study[J]. IEEE Journal on Selected Areas in Communications, 2019, 37(4): 933-946.
[6] Xiang L, Brejza M F, Maunder R G, et al. Arbitrarily parallel turbo decoding for ultra-reliable low latency communication in 3GPP LTE[J]. IEEE Journal on Selected Areas in Communications, 2019, 37(4): 826-838.
[7] Xiang L, Maunder R G, Hanzo L. Concurrent OFDM Demodulation and Turbo Decoding for Ultra Reliable Low Latency Communication[J]. IEEE Transactions on Vehicular Technology, 2019, 69(2): 1281-1290.
[8] Popovski P, Nielsen J J, Stefanovic C, et al. Wireless access for ultra-reliable low-latency communication: Principles and building blocks[J]. Ieee Network, 2018, 32(2): 16-23.
[9] Popovski P, Stefanović Č, Nielsen J J, et al. Wireless access in ultra-reliable low-latency communication (URLLC)[J]. IEEE Transactions on Communications, 2019, 67(8): 5783-5801.
[10] Singh B, Tirkkonen O, Li Z, et al. Contention-based access for ultra-reliable low latency uplink transmissions[J]. IEEE Wireless Communications Letters, 2017, 7(2): 182-185.
[11] Mahmood N H, Abreu R, Böhnke R, et al. Uplink grant-free access solutions for URLLC services in 5G new radio[C]//2019 16th International Symposium on Wireless Communication Systems (ISWCS). IEEE, 2019: 607-612.
[12] Qi R, Chi X, Zhao L, et al. Martingales-Based ALOHA-Type Grant-Free Access Algorithms for Multi-Channel Networks With mMTC/URLLC Terminals Co-Existence[J]. IEEE Access, 2020, 8: 37608-37620.
[13] Jacobsen T, Abreu R, Berardinelli G, et al. System level analysis of uplink grant-free transmission for URLLC[C]//2017 IEEE Globecom Workshops (GC Wkshps). IEEE, 2017: 1-6.
[14] Pocovi G, Soret B, Pedersen K I, et al. MAC layer enhancements for ultra-reliable low-latency communications in cellular networks[C]//2017 IEEE International Conference on Communications Workshops (ICC Workshops). IEEE, 2017: 1005-1010.
[15] Ppallan J M, Jaiswal S, Arunachalam K, et al. Reducing User Perceived Latency in Smart Phones Exploiting IP Network Diversity[J]. IEEE Access, 2020, 8: 143055-143065.
[16] Park J, Samarakoon S, Bennis M, et al. Wireless network intelligence at the edge[J]. Proceedings of the IEEE, 2019, 107(11): 2204-2239.
[17] Popovski P, Trillingsgaard K F, Simeone O, et al. 5G wireless network slicing for eMBB, URLLC, and mMTC: A communication-theoretic view[J]. Ieee Access, 2018, 6: 55765-55779.
[18] Pedersen K I, Pocovi G, Steiner J, et al. Punctured scheduling for critical low latency data on a shared channel with mobile broadband[C]//2017 IEEE 86th Vehicular Technology Conference (VTC-Fall). IEEE, 2017: 1-6.
[19] Pocovi G, Pedersen K I, Mogensen P. Joint link adaptation and scheduling for 5G ultra-reliable low-latency communications[J]. Ieee Access, 2018, 6: 28912-28922.
[20] Pokhrel S R, Ding J, Park J, et al. Towards enabling critical mMTC: A review of URLLC within mMTC[J]. IEEE Access, 2020, 8: 131796-131813.
[21] 3GPP, “Physical channel design for 2-step RACH,” 3rd Generation Partnership Project (3GPP), TSG RAN WG1 Meeting NR R1-1700880, Jan. 2017.
[22] https://www.counterpointresearch.com/zh-hans/wi-fi-66e-a-viable-alternative-to-5g-nr-for-low-latency-applications

