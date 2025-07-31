## OSI Model
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
## Network Topologies
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
## Network Cabling
### Copper Cabling
1. Twisted pair copper cabling. 4 pairs of twisted cables (transmit+/transmit- or recieve+/recieve-). Twist is used to reduce noise/interference (compare on recieving end and restore). Cabling standards ISE/IEC 11801. T568-A, T568-B define two types of twisted pair cables and they must use terminators of the same type.
2. Coaxial cable. Two or more forms share a common axis.
3. Twinaxial cable. Two inner conductors.
