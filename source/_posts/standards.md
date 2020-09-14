---
title: URLLC IN Standards
date: 2020-09-12 15:22:36
tags:
- URLLC
- 3GPP standard
- specification requirements
- random access
- research
---

To enable URLLC in 5G networks, novel scenarios and requirements as well as corresponding access protocols are introduced in 3GPP standards.

# Representative scenarios of URLLC

Some representative scenarios of URLLC are introduced in [1] and can be classified as follows.

- Cyber-physical control applications in vertical domains
  - Motion control
  - Remote control
  - Discrete automation
  - Process automation
  - Automation for electricity distribution (mainly medium and high voltage)
  - Automation solutions for the infrastructure supporting street-based traffic
- V2X

- Rail communications
  - Rail communications (e.g. railway, rail-bound mass transit) have been using 3GPP based mobile communication (e.g. GSM-R) already for some time, while there is still a driver on-board of the train. The next step of the evolution will be providing fully automated train operation that requires highly reliable communication with moderate latencies but at very high speeds of up to 500km/h.
- Critical Communications services
  - Public safety communications
  - Emergency communications
  - Public warning/emergency ( e.g. alert systems)
- Health and medicine
  - remote surgery 

**Note:** requiring very low latency and very high communication service availability

# Specification requirements for URLLC

As specified in [2], control plane latency and user plane latency for URLLC should be as follows.

- The target for control plane latency should be 10ms.
- For URLLC, the target for user plane latency should be 0.5ms for UL, and 0.5ms for DL.

# Representative access protocols for URLLC

As presented in [3], there are several existing random access enhancements in standards for URLLC.

- Early data transmission in release 15 aims to reduce the connection setup signaling overhead and shorten the overall transmission time.
- Flexible PHY layer numerology mainly adapt to URLLC by shortening transmission slots.

**Note:** 

- ACB with different back-offs depending upon the traffic priority has been introduced in LTE. But simulations results show that ACB does not satisfy the 3GPP control plane requirements for URLLC.
- Shortening the TTI results in capacity loss due to the higher relative overhead of control signals. In addition, a short TTI reduces the system coverage, particularly in the uplink direction, as less energy is gathered from the UEs with limited transmission power [4].

# Problems

- There are a series of standards for mMTC specially, such as LTE-M, NB-IOT and so on. But it seems like that there is no dedicated protocols for URLLC. Although early data transmission can be used for URLLC, it is designed for small packet data transmission, only suitable for a few URLLC scenarios.

# References

[1] 3GPP TS 22.261 V16.12.0 (2020-07)

[2] 3GPP TR 38.913 V16.0.0 (2020-07) 

[3]  J. Thota and A. Aijaz, "On Performance Evaluation of Random Access Enhancements for 5G uRLLC," 2019 IEEE Wireless Communications and Networking Conference (WCNC), Marrakesh, Morocco, 2019, pp. 1-7, doi: 10.1109/WCNC.2019.8885815.

[4] G. Pocovi, H. Shariatmadari, G. Berardinelli, K. Pedersen, J. Steiner and Z. Li, "Achieving Ultra-Reliable Low-Latency Communications: Challenges and Envisioned System Enhancements," in IEEE Network, vol. 32, no. 2, pp. 8-15, March-April 2018, doi: 10.1109/MNET.2018.1700257.