# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program:

PING COMMAND:

CLIENT:
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

SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

TRACEROUTE COMMAND:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

## Output :
PING COMMAND:

CLIENT:

![318469112-7d14097a-a1d9-485d-be13-94b157c271d6](https://github.com/HEMAKESHG/4.Execution_of_NetworkCommends/assets/144870552/b49d3430-85fd-46a1-b5ff-64329e0703c8)


SERVER:

![318469168-55491c3f-2427-4ee9-a0fb-530c80b5cd29](https://github.com/HEMAKESHG/4.Execution_of_NetworkCommends/assets/144870552/9171174c-aa51-409d-a745-43d8f3098fda)


TRACEROUTE COMMAND:

![318469246-1f5d8901-9514-44f9-a3fa-f700c40303f4](https://github.com/HEMAKESHG/4.Execution_of_NetworkCommends/assets/144870552/f6b094b9-06f9-42d5-88e8-a4f9093f1a71)



## Result
Thus Execution of Network commands Performed.
