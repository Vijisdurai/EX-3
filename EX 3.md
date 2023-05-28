# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## DATE : 23-03-2023

## AIM :
    To implement socket programming date and time display from client to 
	server using TCP Sockets
    
## ALGORITHM :
## SERVER:
```
    1. Create a server socket and bind it to port.
    2. Listen for new connection and when a connection arrives, accept it.
    3. Send server‟s date and time to the client.
    4. Read client‟s IP address sent by the client.
    5. Display the client details.
    6. Repeat steps 2-5 until the server is terminated.
    7. Close all streams.
    8. Close the server socket.
    9. Stop.
```
## CLIENT:
 ```
	1. Create a client socket and connect it to the server‟s port number.
    2. Retrieve its own IP address using built-in function.
    3. Send its address to the server.
    4. Display the date & time sent by the server.
    5. Close the input and output streams.
    6. Close the client socket.
    7. Stop.
```
## PROGRAM :

## CLIENT:
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
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```
## OUTPUT:

## CLIENT :
![client output](https://github.com/Vijisdurai/EX-3/assets/118343184/d235a1f9-e967-4c4c-b423-07628a988978)

## SERVER:
![server](https://github.com/Vijisdurai/EX-3/assets/118343184/b3ab8676-8514-4e88-82c9-ddf0708b9e06)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.




