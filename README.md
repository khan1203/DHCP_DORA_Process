# DHCP Exchange (DORA Process)

## 1. Concept of DHCP

Dynamic Host Configuration Protocol (DHCP) is a network management protocol used to automatically assign IP addresses and other network settings (subnet mask, gateway, DNS) to devices on a network.  
It removes the need for manual IP configuration and helps avoid configuration errors.  
A DHCP server manages a pool of IPs and provides them to clients using a process called **DORA**.

---

# DHCP Message Exchange (DORA)

The DHCP IP allocation process consists of four main messages:

---

## 1. DHCP Discover Message

- The first message sent by the **DHCP client**.  
- **Purpose:** To locate available DHCP servers.  
- **Type:** Broadcast (255.255.255.255).  
- **Contains:**  
  - Client MAC address  
  - Request for network configuration  
  - Indication that the client has no IP  

### Step 1: DHCP Discover

![DHCP DORA Process – Step 1](https://ipwithease.com/wp-content/uploads/2020/06/DORA-PROCESS-STEP1.jpg.webp)

*Client sends a DHCP Discover message to find available DHCP servers.*

### Explanation:
When a device joins a network, it does not know the DHCP server’s address.  
So, it broadcasts a **DHCPDISCOVER** message to reach all DHCP servers.

---

## 2. DHCP Offer Message

- Sent by the **DHCP server** in response to the discovery message.  
- **Purpose:** To offer an IP address lease to the client.  
- **Type:** Broadcast or unicast.  
- **Contains:**  
  - Offered IP address  
  - Subnet mask  
  - Default gateway  
  - DNS servers  
  - Lease duration  

### Explanation:
Any DHCP server receiving the discovery may send a **DHCPOFFER**.  
It informs the client:  
“Here is an IP address you can use.”

---

## 3. DHCP Request Message

*(Sometimes mistakenly called “recovery message,” but the correct term is **DHCP Request**)*

- Sent by the **client**.  
- **Purpose:** To accept one DHCP offer and reject others.  
- **Type:** Broadcast.  
- **Contains:**  
  - Selected DHCP server ID  
  - Requested IP address  
  - Client MAC address  

### Explanation:
If multiple offers are received, the client chooses one and broadcasts a **DHCPREQUEST**, telling all servers:  
“I accept the offer from this specific server.”

---

## 4. DHCP Acknowledgement (ACK) Message

- Sent by the **selected DHCP server**.  
- **Purpose:** To confirm the IP lease and finalize configuration.  
- **Contains:**  
  - Confirmed IP address  
  - Subnet mask  
  - Gateway  
  - DNS information  
  - Lease start time and duration  

### Explanation:
The **DHCPACK** message completes the DORA process.  
The client configures its IP address and officially joins the network.

---

# Summary Table

| Step | Message      | Sender | Purpose                   |
|------|--------------|--------|---------------------------|
| 1    | Discover     | Client | Locate DHCP servers       |
| 2    | Offer        | Server | Offer IP address          |
| 3    | Request      | Client | Request chosen IP offer   |
| 4    | Acknowledge  | Server | Confirm IP assignment     |

**DORA = Discover → Offer → Request → Acknowledge**
