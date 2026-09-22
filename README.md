# Secure Campus Network Design & Implementation

A cybersecurity project that designs, simulates, and secures a college campus network using **Cisco Packet Tracer**. The project performs a security audit of the existing network, implements a hybrid access architecture with layered security, and enforces role- and time-based web access policies.

## Project Overview

Educational institutions rely heavily on campus networks for teaching, learning, and administration, but these networks are often flat, poorly segmented, and vulnerable to attacks. This project addresses those weaknesses through three interlinked parts:

1. **Campus Network Security Audit** – Analyzes the current network topology and identifies vulnerabilities.
2. **Hybrid Access Design** – Implements a secure architecture supporting both faculty and students with differentiated access privileges.
3. **Smart Web Access Policies** – Enforces web usage rules to prevent misuse while allowing legitimate academic resources.

## Repository Contents

| File | Description |
|------|-------------|
| `Topology of the college network..pkt` | The full Cisco Packet Tracer topology with all security implementations |
| `Project report.pdf` | Detailed report documenting the audit, design, and policies |
| `README.md` | This file |

## Security Measures Implemented

### 1. Network Segmentation
- **VLAN configuration** – Faculty, Student, and Management VLANs with separate DHCP pools and IP assignment
- **DMZ** – Isolated zone for public-facing servers (proxy, web filtering, syslog)
- **ACLs** – Access control lists to filter traffic and block unauthorized sources

### 2. Access & Remote Connectivity
- **VPN Gateway** – Secure remote access for faculty
- **Reverse Proxy (Identity-Aware Proxy)** – Publishes student-facing web apps without exposing internal services to the Internet
- **Edge Firewall** – Protects the DMZ and internal network boundary

### 3. Wireless Security
- Dedicated access points per VLAN secured with **WPA2-PSK**

### 4. Web Access Control & Monitoring
- **Web Filtering Server** – Content filtering by user role and time of day
- **Syslog Server** – Centralized logging of network events and violations
- **Role-based policies** – Students (academic-only during class hours), Faculty (full access, logged), Guests (internet only)

## Topology Overview

The campus network is built on a **cluster-based model**:

```
Main Cluster (Circular Block)
    Router, Server (DHCP), Switch, AP + end devices
    |
    |-- Admin Cluster
    |-- 4 x Academic Clusters (Staff Room, Classrooms, Computer Lab)
    |-- Library Cluster (e-library servers, student terminals)
    |-- Canteen Cluster (PoS, Wi-Fi)
```

Security components (DMZ, firewall, proxy, VPN gateway, web filtering, syslog) are integrated into the main cluster for centralized control.

## Technologies Used

- **Cisco Packet Tracer** – Network simulation and implementation
- **Cisco Networking Academy curriculum** – Cybersecurity Essentials concepts
- Networking protocols: DHCP, VLAN, WPA2-PSK, ACLs, VPN, DNS filtering, Syslog

## How to Use

1. Open the `.pkt` file in **Cisco Packet Tracer** (version that supports the included devices).
2. Explore the topology and inspect device configurations.
3. Refer to the PDF report for architecture diagrams, policy details, and design rationale.

## Key Outcomes

- Layered defense: segmentation + firewall + monitoring + access control
- Least-privilege, role-based access for faculty, students, and guests
- Internal services are never exposed directly to the Internet
- Centralized logging and alerting for compliance and threat detection