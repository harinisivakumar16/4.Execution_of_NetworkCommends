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

##TRACE
import os

host = input("Enter the host name or IP address: ")

print("Tracing route to", host)
print("--------------------------------")

os.system("tracert " + host)

##OUTPUT:

<img width="1291" height="285" alt="Screenshot 2026-03-12 092435" src="https://github.com/user-attachments/assets/c8419729-9aa5-4cdc-8b27-6bb0df6b6f79" />

##NESTAT

<img width="894" height="671" alt="image" src="https://github.com/user-attachments/assets/eb32184d-21be-4167-ba22-cd829a5c385a" />

##ipconfig

<img width="969" height="272" alt="image" src="https://github.com/user-attachments/assets/ca8c9b70-d3a5-48f5-889c-f3674df1036c" />

##ping

<img width="940" height="172" alt="image" src="https://github.com/user-attachments/assets/926f6987-9808-49ff-907f-655e17726f1e" />

##tracet

<img width="826" height="142" alt="image" src="https://github.com/user-attachments/assets/7e6a9a1e-b8e4-4aac-b6a5-9cd5feea05cf" />

##nslookup

<img width="534" height="103" alt="image" src="https://github.com/user-attachments/assets/1a445265-b56a-479e-a05d-da6d4484abe0" />

##getmac

<img width="973" height="153" alt="image" src="https://github.com/user-attachments/assets/74339798-2002-4a04-9928-6818bcde8ebe" />

##hostname

<img width="543" height="77" alt="image" src="https://github.com/user-attachments/assets/d32ac471-9ab5-414f-bf5d-d2d699eb3a42" />

##nbtstat

<img width="1037" height="576" alt="image" src="https://github.com/user-attachments/assets/ca66d840-d354-46de-8707-8009007d8352" />

##arp

<img width="1112" height="648" alt="image" src="https://github.com/user-attachments/assets/91ba87be-66c8-401b-8f24-e914444b5501" />

##systeminfo

<img width="1341" height="678" alt="image" src="https://github.com/user-attachments/assets/c849431b-4c16-4181-8736-1012c9f8d86a" />


## Result
Thus Execution of Network commands Performed 
