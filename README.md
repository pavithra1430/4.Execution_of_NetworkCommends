# PAVITHRA S
# 212223220072
# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
All commands related to Network configuration which includes how to switch to privilege mode
and normal mode and how to configure router interface and how to save this configuration to
flash memory or permanent memory
This commands includes
• Configuring the Router commands
• General Commands to configure network
• Privileged Mode commands of a router 
• Router Processes & Statistics
• IP Commands
• Other IP Commands e.g. show ip route etc.
## program ping command
## client
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
## sever
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
## tranceroute command
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
## client
![image](https://github.com/pavithra1430/4.Execution_of_NetworkCommends/assets/168256810/dff3dd7e-1558-416c-8522-a23ee0c35f4d)
## sever
![image](https://github.com/pavithra1430/4.Execution_of_NetworkCommends/assets/168256810/3cce689b-805e-40f0-874b-0b8463e3b670)
## tranceroute command
![image](https://github.com/pavithra1430/4.Execution_of_NetworkCommends/assets/168256810/19b0c160-08ef-4991-a548-c65023ad9dd6)
## Result
Thus Execution of Network commands Performed 
