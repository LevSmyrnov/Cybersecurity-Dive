# MITRE Framework
MITRE ATT&CK and Shield framework describes different techniques, procedures and goals of attacker and active defender in cybersecurity context.<br></br>
## MITRE PRE-ATT&CK
Getting accustomed with possible instruments for carrying out pre-attack tactics of mitre framework.
1. ```Scapy``` is a library designed for working with network traffic. It can view, edit and build packets.<p></p><img width="273" height="505" alt="image" src="https://github.com/user-attachments/assets/16b42fb7-3c6c-4144-990b-46c189450faa" /><p></p>
2. ```Scapy``` command ```sr``` can handle sending packets and receiving response.<p>```ans, unans = sr(IP(dst=<TARGET_IP>)/TCP(port=<TARGET_PORT>(can be a collection of ports),flags=<FLAG>(e.g "S" for SYN to perform port scanning)),timeout=2,verbose=0)```</p>May require administrator permissions to use sockets.
