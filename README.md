### Portscanner.pem

#### Creating a personalized port scanner for scanning the open ports available on a particular Ip Address. The portscanner allows scanner multiple Ip addresses and the amount of ports specified to scan.
---
### Tools
- Python programming Language.
- A system you have authorization to scan (Preferably a virtual machine or in real world cases your router).
- Kali linux.
---

### Steps Imployed

#### 1. Create a directory

```bash
mkdir tool && cd tool
```
---
#### 2. Create a python file and write your script. There is an option of writing the script on Vs code 

```bash
vim roro.py
```
Then insert your python script

```python

import socket
import termcolor 


def scan (target, ports):
         for port in range (1, ports):
                  scan_port(target,port)



def scan_port(ipaddress, port):

        try:

                sock = socket.socket()
                sock.connect((ipaddress, port))
                print("[+] Port Opened " + str(port))
                sock.close()

        except:
               print("[-] Port Closed " + str(port))




targets = input("[*] Enter Targets To Scan(split them by ,): ")
ports = int(input ("[*] Enter How Many Ports To Scan: "))

if ',' in targets:
       print ("[*] Scanning Multiple Targets")
       for ip_addr in targets.split(','):
                scan (ip_addr.strip(' '), ports)


else:

           scan(targets,ports)
```
---
#### 3. Start your scan and fill in the Ip address or addresses and the number of ports you intend scanning.

```bash
python3 roro.py
```
---
#### 4. There's also an option of cloning the python script to make some adjustment that can suite your immediate needs or run it directly.

```bash
git clone https://github.com/Caelestibus/Portscanner.pem.git
```
#### _Open file and access roro.py_
---
