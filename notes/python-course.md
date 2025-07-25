# MITRE Framework
MITRE ATT&CK and Shield framework describes different techniques, procedures and goals of attacker and active defender in cybersecurity context.<br></br>
## MITRE PRE-ATT&CK
Getting accustomed with available instruments and weaknesses for carrying out pre-attack tactics of mitre framework.
1. ```Scapy``` is a library designed for working with network traffic. It can view, edit and build packets.<p></p><img width="273" height="505" alt="image" src="https://github.com/user-attachments/assets/16b42fb7-3c6c-4144-990b-46c189450faa" /><p></p>
2. ```Scapy``` command ```sr``` can handle sending packets and receiving response.<p>```ans, unans = sr(IP(dst=<TARGET_IP>)/TCP(port=<TARGET_PORT>(can be a collection of ports),flags=<FLAG>(e.g "S" for SYN to perform port scanning)),timeout=2,verbose=0)```</p>May require administrator permissions to use sockets.
## MITRE ATT&CK
### Initial Access Tactic
#### Valid accounts. Default account discovery.
Getting access to target's accounts.
1. ```paramiko``` is a library for working with SSH. It allows to try to open SSH connection with username/password via method ```set_missing_host_key_policy(paramiko.AutoAddPolicy()).
2. ```telnetlib``` is a library for working with Telnet protocol. Sign of successful login can be <b>Last Login</b> message.
#### Replication through removable media.
Attack vector via autorun script on removable media, e.g usb drive.
1. ```PyInstaller.__main__``` can be used to create self-contained python executable.
2. An ```autorun.inf``` file is a text file that can be used by the <b>AutoRun</b> and <b>AutoPlay</b> components of old <b>Microsoft Windows</b> operating systems. For the file to be discovered and used by these component, it must be located in the root directory of a volume.
