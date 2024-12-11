1\. **Choke Firewall:**

- **Design**: A choke firewall is typically a device placed between a trusted internal network and an untrusted external network (like the internet).
- **Function**: It acts as a bottleneck through which all incoming and outgoing traffic must pass, allowing it to inspect and control all communications.
- **Key Feature**: Filters traffic based on predefined rules at a single point of connection between networks.
- **Granularity**: Can be more focused on packet filtering at lower layers (OSI layers 3 and 4).
- **Advantages**: Simple and easy to manage.
- **Disadvantages**: May become a single point of failure or bottleneck if not configured or scaled properly.

2\. **Screening Firewall (Packet-Filtering Firewall):**

- **Design**: Screening firewalls examine incoming and outgoing packets and decide whether to allow or block them based on packet header information (source/destination IP, port number, etc.).
- **Function**: Typically operates on Layer 3 (Network Layer) and Layer 4 (Transport Layer) of the OSI model to filter traffic.
- **Key Feature**: Uses access control lists (ACLs) to determine what traffic to allow or deny. It doesn’t inspect the contents of the packet but just the headers.
- **Granularity**: Can allow or deny traffic based on IP addresses, protocols, or port numbers.
- **Advantages**: Fast, lightweight, and can handle large volumes of traffic with low overhead.
- **Disadvantages**: Lacks the ability to inspect the actual content of the packet (no deep packet inspection), making it vulnerable to certain attacks (like those embedded in allowed traffic).

&nbsp;

<img src="../_resources/24fed06e1309238ed86332aee6fe8b43.png" alt="24fed06e1309238ed86332aee6fe8b43.png" width="660" height="416" class="jop-noMdConv">

&nbsp;

## A perimeter network can also be established using one router/firewall appliance with three network interfaces, referred to as triple homed. One interface is the public one, another is the perimeter subnet, and the third connects to the LAN. Routing and filtering rules determine what forwarding is allowed between these interfaces. This can achieve the same sort of configuration as a screened subnet.

&nbsp;

<img src="../_resources/46defda26d5812d3d774f7c612aa0daa.png" alt="46defda26d5812d3d774f7c612aa0daa.png" width="621" height="392" class="jop-noMdConv">

&nbsp;

&nbsp;

# Stateful vs Stateless Firewalls - Summary Table

| Feature | Stateful Firewall | Stateless Firewall |
| --- | --- | --- |
| **Connection Tracking** | Yes | No  |
| **Performance** | Slower (more resource-intensive) | Faster (less resource-intensive) |
| **Rule Complexity** | Complex (context-aware) | Simple (static rules only) |
| **Use Cases** | Corporate networks, complex environments | Home networks, simple setups |
| **Security Features** | More effective against session attacks | Limited effectiveness against complex threats |

&nbsp;

Choke and screened firewalls generally fall into the category of stateless firewalls.

To explain further:

1.  Stateless firewalls:
    - Make decisions based on individual packets without considering the context of the connection.
    - Use predefined rules to allow or block traffic based on information in the packet header.
    - Are typically faster and use less memory than stateful firewalls.
    - Examples include packet-filtering firewalls, which choke and screened firewalls are types of.
2.  Stateful firewalls:
    - Keep track of the state of network connections.
    - Make decisions based on the context of the traffic, considering both individual packets and the entire connection.
    - Can provide more sophisticated protection but may use more resources.

Choke firewalls and screened firewalls are considered stateless because:

- Choke firewalls: These are essentially packet filters placed between an internal and external network. They examine each packet individually based on predefined rules without maintaining state information.
- Screened firewalls: These typically consist of a packet-filtering router (screening router) that filters traffic before it reaches the internal network. The screening is done on a packet-by-packet basis without maintaining connection state.