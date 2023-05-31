# IMPLEMENTATION OF ADDRESS RESOLUTION PROTOCOL(ARP)
# EXP: 4
# DATE:29-03-2023
# AIM:
To write a python program for implementing Address Resolution Protocol(ARP).
# ALGORITHM:
# Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
# Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
# PROGRAM:
# CLIENT:
```python3
import socket
s=socket.socket()
s.bind(('localhost',8000))
@@ -35,14 +36,17 @@ try:
  c.send(address[ip].encode())
except KeyError:
  c.send("Not Found".encode())
  ```
# SERVER:
```python3
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   ip=input("Enter logical Address : ")
   s.send(ip.encode())
   print("MAC Address",s.recv(1024).decode())
```

# CLIENT OUTPUT : 
![image](https://github.com/arun1111j/cn-ex04/assets/128461833/e0530a94-1571-4cf8-b878-74cfd57d6f1f)

# SERVER OUTPUT :
![image](https://github.com/arun1111j/cn-ex04/assets/128461833/dffe3784-5f34-4d94-be60-a98419e7ece7)

# RESULT:
Thus, the python program for simulating ARP protocols using TCP was successfully
executed.
