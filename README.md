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

## 📊 (Optional) Visual Diagram

Here’s a simple **MermaidJS diagram** (GitHub renders this automatically):

```mermaid
graph LR
    A[Network A 10.1.1.0/24] --- RY[Router Y]
    RY --- B[Network B 192.168.1.0/24]
    B --- RZ[Router Z]
    RZ --- C[Network C 172.16.1.0/24]
![Network Diagram](https://github.com/user-attachments/assets/1096fc7c-f723-4a85-ae68-9a485e39f30d)
