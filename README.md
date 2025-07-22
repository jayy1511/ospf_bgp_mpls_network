# GNS3 Lab: OSPF + BGP + MPLS

## 🧠 Objective

This lab simulates a multi-router enterprise network setup integrating:

- **OSPF** for internal routing,
- **BGP** for external AS communication,
- **MPLS** for label-switched packet forwarding.

It demonstrates end-to-end connectivity and routing using dynamic protocols, loopback interfaces, and label distribution across a 5-router network.

---

## 🌐 Network Topology

![Topology](.//ospf_bgp_mpls_network/images/Topology/Topology.png)

---

## 🔧 Network Structure

### ✅ OSPF Configuration
- OSPF enabled on all routers (R1–R5).
- Verified OSPF neighbor relationships.
- Loopbacks advertised in OSPF.

### ✅ BGP Setup
- BGP configured between **R3 (AS 11)** and **R5 (AS 12)**.
- R5's loopback `5.5.5.5` advertised into BGP.
- R3 redistributes BGP into OSPF.
- R1 learns BGP loopback via OSPF.

### ✅ MPLS Setup
- MPLS enabled globally and on interfaces.
- Loopbacks used for LDP router-IDs.
- Verified MPLS LDP neighbors and labels.

---

## 🔁 Redundancy

- OSPF path cost manipulated for primary (via R2) and backup (via R4).
- Failover tested by shutting R2 path.
- Attempted virtual link (R3 ↔ R5) failed due to BGP AS separation.

---

## ✅ Final Validation

- Successful ping from R1 to R5 (`5.5.5.5`).
- Traceroute confirms MPLS label switching across core routers.
- OSPF and BGP path logic confirmed.

---

## 📎 Included Files

- `ospf_bgp_mpls_network.gns3` – GNS3 project file
- `project-files/dynamips/` – GNS3 router configurations
- `images/` – Screenshots of step-by-step configuration
- `images/Topology/Topology.png` – Full network topology diagram

---

## 📚 Requirements

- GNS3
- Cisco IOS images (e.g., `c7200` or `IOSv`)
- Basic understanding of OSPF, BGP, and MPLS

---

## 🏁 Author

Created by Jay Patel. For academic use and advanced routing practice.
