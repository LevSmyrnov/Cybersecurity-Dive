# Table of Contents
- [OSI Model](#osi-model)
- [Network Topologies](#network-topologies)
- [Network Cabling](#network-cabling)
- [IPv4 and IPv6](#ipv4-and-ipv6)
- [IP](#ip)
## [OSI Model](#table-of-contents)
1. Layers (**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing):
    <ul>
      <li>Application(observable browser data, e.g HTTPS or SSH or DNS)</li>
      <li>Presentation(encoding, encryption (SSL or TLS))</li>
      <li>Session(e.g control protocols and tunneling protocols)</li>
      <li>Transport(ports, e.g TCP or UDP)</li>
      <li>Network(routing, e.g IP addresses)</li>
      <li>Data Link(switching, e.g MAC address)</li>
      <li>Physical(signaling, e.g optic fibre cables)</li>
    </ul>
    OSI *model* is a guide. OSI *protocols*/*protocol suites* are implementations.
3. Layers have data related to them. Data is preceded by *header*, which contains information (control flags) on how to process data.
4. On Ethernet, maximum IP packet size is 1500 bytes. If the IP packet size is bigger than **M**aximum **T**ransmission **U**nit size, the IP packet undergoes IP fragmentation into multiple packets. *During tunneling, MTU may be smaller than on local Ethernet part of network.
<br></br>
## [Network Topologies](#table-of-contents)
1. Star (hub and spoke). All devices are connected to central node. e.g Switched Ethernet networks.
2. Ring. Higher fault tolerance.
3. Coax (bus network). Simple, but prone to errors.
4. Mesh. Multiple links to same place.
5. Hybrid. More than 1 topology types together.
6. Wireless. Access through access points. Access through ad hoc. Multiple ad hoc devices can create mesh wireless networks.
### Network types
1. Peer-to-peer. Everyone talks to everyone.
2. Client-server. Responsibilities are split.
3. LAN. One building. Uses Ethernet or 802.11 wireless.
4. Wireless LAN. Mobile inside limited area. Uses 802.11 technologies.
5. WAN. Spanning the globe. Uses cables or satelites.
6. NAS shared storage device available across network with file-level access (whole file changes even if part was changed). Storage Area Network block-level access. May use an isolated network, because requires a lot of bandwidth.
7. Multiprotocol Label Switching - packets through WAN have labels. Any protocol, any transport medium. Uses label's pushing and popping when changing networks.
8. SD-WAN. Software defined WAN. Used in cloud-based applications.
### WAN Termination
Demarcation point (demarc) - point where ISP WAN is connected to Customer Premises (CPE) LAN. Network Interface Unit - device of demarc (usually).
### Virtual Networks
Network Function Virtualisation (NFV) happens when multiple physical network devices are replaced with virtual versions. Managed by hypervisor - Virtual Machine Manager (VMM). VMM manages CPU, Networking, Security (can use orchestration for automation). Network is connected with vSwitch. vNIC are attached to servers.
### Provider Links
1. Satellite networking.
2. Copper coax or twisted pair. Asymmetric Digital Subscriber Line (uses telephone lines). Cable Broadband (multiple frequencies/bandwidths on cable network).
3. Fiber optics (SONET, WDM).
4. Metro Ethernet (MAN).
<br></br>
## [Network Cabling](#table-of-contents)
### Copper Cabling
1. Twisted pair copper cabling. 4 pairs of twisted cables (transmit+/transmit- or recieve+/recieve-). Twist is used to reduce noise/interference (compare on recieving end and restore). Cabling standards ISE/IEC 11801. T568-A, T568-B define two types of twisted pair cables and they must use terminators of the same type. Uses Registered Jack 45 (8 position, 8 conductor).
2. Coaxial cable. Two or more forms share a common axis. Uses F-connector (DOCSIS) and RG-6 cable.
3. Twinaxial cable. Two inner conductors.
### Optical Fiber
Uses an LED or a laser to create light. Highly reflective core, low reflecting cladding, protective coating. Multi-mode fiber (used for short-range, with LED) - core of fiber is larger than light's wavelength. Single-mode fiber (used for up to 100 km, with laser).
Fiber optic connectors:
<ul>
    <li>Local Connector</li>
    <li>Straight Tip</li>
    <li>Subscriber Connector</li>
    <li>Mechanical Transfer Registered Jack</li>
</ul>

UPC connectors meet with 0 degree angle and have higher return loss. APC connectors meet with 8 degree angle and have higher insertion loss.
### Network Transceivers
Media converter (OSI Layer 1 - physical signal conversion).
Transceiver - modular interface to plug in required connection. e.g Small Form-factor Pluggable (SFP, 1 Gbit/s fiber or 1 Gbit/s RJ45), Enhanced (SFP+) (up to 16 Gbit/s), Quad (QSFP), Enhanced Quad (QSFP+), BiDi QSFP+. 
<ul>
    <li>Duplex transceiver - one fiber to transmit, another to receive</li>
    <li>Bi-Directional transceiver - trafic in both directions via single fiber (uses two different wavelengths).</li>
</ul>

### Ethernet Standards
<ul>
<li>Baseband connection - single frequency over medium.</li>
<li>Broadband connection - many frequencies over medium.</li>
</ul>

1. 1000BASE-T: 4 pair balance twisted cable with baseband and 1 Gigabit Ethernet, 125 MHz. Uses Category 5e cable or better for 100 meters maximum.
2. 10GBASE-T: 4 pair balance twisted cable with baseband and 10 Gigabit Ethernet, 500 MHz. Uses Category 6 cable or better for 55(unshielded)/100(shielded) meters maximum.
3. 1000BASE-SX: optics 1 Gigabit Ethernet, short wavelength laser (shorter distance 220-550 meters).
4. 10GBASE-SR: optics 10 Gigabit Ethernet, Short Range (26-400 meters).
Wavelength-Division Multiplexing - bidirectional communication (different "colours"). Requires multiplexer on both ends of fiber.
<br></br>
## [IPv4 and IPv6](#table-of-contents)
### IPv4
32 bit addresses. Requires three addresses for networking:
<ul>
    <li>IP Address for device identification on network.</li>
    <li>Subnet Mask for device to determine what IP subnet they are on.</li>
    <li>Default Gateway for device to send traffic for external subnets to.</li>
</ul>
Special IP addresses:
<ul>
    <li>Loopback address - references itself (in range 127.0.0.1 - 127.255.255.254).</li>
    <li>Reserved addresses (class E) (in range 240.0.0.1 - 254.255.255.254).</li>
    <li>Virtual IP address - not associated with physical network adapter. Assigned to logical network adapter (router, virtual machine).</li>
</ul>
Address resolving:
<ul>
    <li>DHCP (Dynamic Host Configuration Protocol) provides automatic address and IP configuration for almost all devices (with DHCP server).</li>
    <li>APIPA (Automatic Private IP Addressing) provides a link-local IP address - no connection to external network (in range 169.254.1.0 - 169.254.254.255). Assigned when DHCP server not available.</li>
</ul>

#### Network Address Translation
IPv4 public address range is exhausted. RFC 1918 requests private IP addresses (10.0.0.0-10.255.255.255, 172.16.0.0-172.31.255.255, 192.168.0.0-192.168.255.255). 
Usually router provides NAT functionality: send requests contains private IP address as Source, then router translates it to Public IP (and in reverse). Source NAT/NAT overload/PAT (Port Address Translation) is used in case multiple devices have to connect to the same server: port numbers are added to Source.
#### Network communication
1. Unicast - one to one device. Used with IPv4 and IPv6.
2. Broadcast - one to all devices. Limited scope of broadcast domain. Used with IPv4.
3. Multicast - one to interested devices. Very specialised. Used with IPv6 mostly and with IPv4.
4. Anycast - one to single device of many options. Used with IPv4 and IPv6. Used for anycast DNS.
#### Classful Subnetting
1. In the beginning (until 1993) there were 3 subnet classes (A, B, C), that were configured based on IP address.
2. Today Variable Length Subnet Masks are used, manually configured. Fast subnetting methods: magic number subnetting, seven second subnetting.  
Construction of subnet (e.g 10.74.222.11 - class A, so subnet mask 255.0.0.0):
    <ul>
        <li>Network address - set all host bits to 0 decimal (10.0.0.0)</li>
        <li>First usable host address - one number higher than Network address (10.0.0.1)</li>
        <li>Network Broadcast address - all host bits to 255 decimal (10.255.255.255)</li>
        <li>Last usable host address - one number lower than Network Broadcast address (10.255.255.254)</li>
    </ul>
Subnet mask deliniates network and host parts of IP address (11111111.11111111.00000000.00000000 <=> 255.255.0.0 <=> /16 (CIDR notation) <=> 16 bits network 16 bits host).

### IPv6
128 bit addresses. Written in hexes in 16bit<=>2bytes<=>2octates groups. Groups of zeros can be abbreaviated with ::. Leading zeros in a group can be removed.
Assignment process:
1. Global routing prefix (48 bits): Internet Assigned Numbers Authority provides address blocks to Regional Internet Registries => RIRs assign blocks to ISPs => ISPs assign a /48 subnet to customers.
2. Subnet (16 bits).
3. Host address can be:
    <ul>
        <li>assigned by DHCP</li>
        <li>assigned by SLAAC - statically assigned via MAC address (EUI64 method). Ethernet Media Access Control address can be described as "physical" address of network adapter (EUI48). To convert EUI48 => EUI64, split 48 bits in half, put 0xFFFE in the middle + invert 7th bit <=> U/L <=> universal/local bit.</li>
    </ul>

Usually IPv6 is associated with first half of subnet mask. Trailed with first 3-bytes of MAC, 0xFFFE, last 3-bytes of MAC.
#### Implementing IPv6 Network
To deploy IPv6:
1. Tunnel IPv6 based on IPv4 (requires specific routers). No support for NAT.
2. Teredo => tunnel IPv6 through NATed IPv4. Temporary use before IPv6 native networks.
3. Dual-stack routing. Run both IPv6 and IPv4 at the same time.
4. Uses NDP (Neighbour Discovery Protocol):
   <ul>
    <li>IPv6 does not have ARP (provided by broadcast) to find out MAC-address of a device.</li>
    <li>No broadcast. Operates using multicast with ICMPv6.</li>
    <li>Stateless Address Autoconfiguration (SLAAC) to configure IP addresses without DHCP server.</li>
    <li>Duplicate Address Detection (DAD).</li>
    <li>Discovers routers.</li>
   </ul>

## [IP protocols](#table-of-contents)
TCP (Transmition Control Protocol) - connection oriented, after every send there is ACKnowledgement back that information was received correctly, there are sequence numbers in headers, packets can be retransmitted, receiver can control how much data is sent.  
UDP (User Datagram Protocol) - connectionless, no acknowledgement, no reordering, no retransimition, no flow control.  
Socket is IP address, protocol and port number (0-65535) combination. TCP ports and UDP ports are different, not interchangeable.
### Common Ports
1. Telnet - tcp/23 - Telecommunication Network. Login to devices remotely. No encryption (in-the-clear).
2. SSH - tcp/22 - Secure Shell. Login to devices remotely. Encrypted.
3. DNS - udp/53; tcp/53 - Domain Name System. Tranlates names to IP addresses.
4. SMTP - tcp/25 in-the-clear; tcp/587 encrypted over TLS - Simple Mail Transfer Protocol. Server to server email transfer. Also used to send from device to server.
5. POP3 - tcp/110 in-the-clear; tcp/995 encrypted over TLS - Post Office Protocol version 3. Basic mail transfer functionality, e.g receive the email.
6. IMAP4 - tcp/143 in-the-clear; tcp/993 encrypted over TLS - Internet Message Access Protocol version 4. Basic mail transfer functionality and management of mailbox.
7. SFTP - tcp/22 - Secure File Transfer Protocol. Provides file system functionality. Uses SSH with added file transfer.
8. FTP - tcp/20 (active mode data (transferring)); tcp/21 (control (what file to send)) File Transfer Protocol. Transfer files. Authentication with username and password. Full feature functionality.
9. TFTP - udp/69 - Trivial File Transfer Protocol. Very simple file transfer operations. No authentication.
10. DHCP - udp/67; udp/68 - Dynamic Host Configuration Protocol. Automatic IP configuration of device, including IP address, subnet mask, default gateway, DNS settings. Pool of IP addresses are leased for 24 hours. DHCP reservations is possible by associating MAC address with IP address.
11. HTTP/HTTPS - tcp/80; tcp/443 (encrypted (SSL before, TLS now)) - Hypertext Transfer Protocol. Communication in the browser.
12. SNMP - udp/161; udp/162 (alert messaging (SNMP trap)) - Simple Network Management Protocol. Gather statistics from network devices.
13. Syslog - udp/514 - standard for message logging usually in central log collector SIEM (Security Information and Event Manager).
14. RDP - tcp/3389 - Remote Desktop Protocol. Shared desktop (single app) view of Windows.
15. NTP - udp/123 - Network Time Protocol. Synchronising date and time on every device.
16. SIP - tcp/5060; tcp/5061 - Session Initiation Protocol. Voice over IP signaling (management).
17. SMB - tcp/445(NetBIOS-less) - Server Message Block (Common Internet File System). Used by Windows for file or printer sharing.
18. LDAP/LDAPS - tcp/389; tcp/636(Secure version over SSL) - Lightweight Directory Access Protocol. Centralised database access.
19. Microsoft SQL Server - tcp/1433.
20. Oracle SQL Net - tcp/1521.
21. MySQL - tcp/3306.
### IP protocols other than TCP/UDP
1. ICMP - Internet Control Message Protocol. "Text messaging" for network devices, e.g ping, something went wrong, time to live expired.
2. GRE - Generic Routing Encapsulation. Encapsulate traffic inside of IP. No built-in encryption.
3. VPN - Virtual Private Network. Encrypted data traversing public network. VPN concentrator (hardware or software).
4. IPSec - Internet Protocol Security. Security for OSI Layer 3. Provides confidentiality and integrity/anti-replay through encryption and packet signing via e.g Authentication Header (hash signing) or Encapsulation Security Payload (data and header encryption + integrity check) protocols. Has transport mode (original IP header in-the-clear) and tunnel mode (original IP header encrypted along with the data).
