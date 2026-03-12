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

##Client.py

import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

client.connect(("localhost", 5000))

website = input("Enter website to ping: ")

client.send(website.encode())

result = client.recv(4096).decode()

print("Ping Result:\n")
print(result)

client.close()



## Output

<img width="1306" height="271" alt="Screenshot 2026-03-12 090127" src="https://github.com/user-attachments/assets/3292ad1d-90fe-40ae-885b-b6fee74b86b7" />


##Server.py
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(("localhost", 5000))
server.listen(1)

print("Server is waiting for connection...")

conn, addr = server.accept()
print("Connected by", addr)

website = conn.recv(1024).decode()

print("Client requested to ping:", website)

import os
result = os.popen("ping " + website).read()

conn.send(result.encode())

conn.close()
server.close()
##Output

<img width="1302" height="171" alt="Screenshot 2026-03-12 090303" src="https://github.com/user-attachments/assets/77ebaad6-5c6a-4e3d-8bee-7e211885f16e" />


## Result
Thus Execution of Network commands Performed 
