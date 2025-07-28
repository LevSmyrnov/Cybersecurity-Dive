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
