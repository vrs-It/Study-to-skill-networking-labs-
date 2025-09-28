# Study-to-skill-networking-labs-
This lab was completed during my **CompTIA Network+ studies** as part of hands-on practice with **IP addressing, subnetting, and routing**.   The exercise involved analyzing a network topology, identifying which devices belonged to which subnets, and determining packet delivery paths.
# Networking Lab – Identifying Networks and Routing

## 🖥️ Network Topology

- **Router Y**  
  - Network A interface: `10.1.1.1`  
  - Network B interface: `192.168.1.254`

- **Router Z**  
  - Network B interface: `192.168.1.1`  
  - Network C interface: `172.16.1.1`

- **Networks**  
  - Network A: `10.1.1.0/24`  
  - Network B: `192.168.1.0/24`  
  - Network C: `172.16.1.0/24`

---

## ❓ Lab Question

> Computer 1 on Network A, with IP `10.1.1.8`, wants to send a packet to Computer 2 with IP `10.1.1.10`.  
> On which network is Computer 2?

---

## 📝 Step-by-Step Reasoning
I came to the conclusion of the answer by analyzing the traffic and where it's going: 
## 📝 Explanation (Traffic Analysis Approach)

When Computer 1 (`10.1.1.8`) wants to send a packet to Computer 2 (`10.1.1.10`), the first step is to check whether the destination IP is in the same subnet.  

- **Subnet of Network A:** `10.1.1.0/24` → valid host range: `10.1.1.1 – 10.1.1.254`  
- Both Computer 1 (`10.1.1.8`) and Computer 2 (`10.1.1.10`) fall within this range.  

Because the destination is on the **same subnet**, Computer 1 does not send traffic to the default gateway (Router Y). Instead, it communicates **directly with Computer 2** using ARP to resolve the MAC address.  

If Computer 2’s IP had been in a different subnet (for example, `192.168.1.x` or `172.16.1.x`), then Computer 1 would have forwarded the packet to Router Y to handle inter-network routing.  


Simplfied Step by step
1. **Check the IP address of Computer 2:** `10.1.1.10`  
2. **Match against subnet ranges:**  
   - Network A = `10.1.1.0/24` → valid range `10.1.1.1 – 10.1.1.254`  
   - Network B = `192.168.1.0/24`  
   - Network C = `172.16.1.0/24`  
3. Since `10.1.1.10` falls within Network A’s range, Computer 2 is **on Network A**.  
4. This means **the packet never leaves Network A**, and routing is not required — delivery will happen directly on the local subnet.

---

## ✅ Answer

**Computer 2 is on Network A.**

---

## 🔑 Key Concepts Reinforced

- Understanding **IP address ranges and subnet masks**  
- Determining whether traffic is **local or requires routing**  
- Reinforcing the difference between **intra-network vs. inter-network communication**  

---


![Network Diagram](https://github.com/user-attachments/assets/1096fc7c-f723-4a85-ae68-9a485e39f30d)
