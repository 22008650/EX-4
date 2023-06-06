# EX-4 IMPLEMENTATION OF ADDRESS RESOLUTION PROTOCOL (ARP)
## DATE : 30.03.2023
## AIM :
To write a python program for simulating ARP protocols using TCP
## ALGORITHM :
## CLIENT:
### STEP 1: 1.Start the program
### STEP 2: Using socket connection is established between client and server.
### STEP 3: Get the IP address to be converted into MAC address.
### STEP 4: Send this IP address to server.
### STEP 5: Server returns the MAC address to client.
## SERVER:
### STEP 1: Start the program
### STEP 2: Accept the socket which is created by the client.
### STEP 3: Server maintains the table in which IP and corresponding MAC addresses are stored.
### STEP 4: Read the IP address which is send by the client.
### STEP 5: Map the IP address with its MAC address and return the MAC address to client.
## CLIENT PROGRAM :

## Developed : Malarvizhi G
## Reg no : 212222040096
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
## SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
## OUTPUT :
## SERVER OUTPUT :
![ex04 server output](https://github.com/22008650/EX-4/assets/122548204/ba8de1b1-3ce7-41bb-af09-b69d8a80a862)
## CLIENT OUTPUT :
![ex04 client output](https://github.com/22008650/EX-4/assets/122548204/ce34dad7-6d2a-4c85-9ef6-67e9004c0af1)

## RESULT :
Thus, the python program for simulating ARP protocols using TCP was successfully executed.
