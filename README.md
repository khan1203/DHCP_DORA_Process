# DHCP_DORA_exchange_messages
Theoritical Explanantion of 4 types of the DHCP exchange messages known as DORA. Described in details specially for the Academic students.

# DHCP Exchange (DORA Process)

## 1. Concept of DHCP

Dynamic Host Configuration Protocol (DHCP) is a network management
protocol used to automatically assign IP addresses and other network
settings (subnet mask, gateway, DNS) to devices on a network.\
It removes the need for manual IP configuration and helps avoid
configuration errors.\
A DHCP server manages a pool of IPs and provides them to clients using a
process called DORA.

# DHCP Message Exchange (DORA)

## 1. DHCP Discover Message

-   The first message sent by the DHCP client.
-   Purpose: To locate available DHCP servers.
-   Sent as a broadcast (255.255.255.255).
-   Contains: client MAC address, request for configuration, etc.

## 2. DHCP Offer Message

-   Sent by the DHCP server.
-   Purpose: To offer an IP lease.
-   Contains: offered IP, subnet mask, gateway, DNS, lease time.

## 3. DHCP Request Message

-   Sent by the client.
-   Purpose: To accept one DHCP offer.
-   Broadcast message selecting one server.

## 4. DHCP Acknowledgement Message

-   Sent by the selected server.
-   Purpose: To confirm the lease and finalize configuration.

# Summary Table

  Step   Message       Sender   Purpose
  ------ ------------- -------- ----------------------
  1      Discover      Client   Find DHCP servers
  2      Offer         Server   Offer IP address
  3      Request       Client   Request chosen offer
  4      Acknowledge   Server   Confirm assignment
