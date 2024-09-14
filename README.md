# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Client 
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
   print(ack)
   continue
 else:
   c.close()
   break
```
### Server 
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```

## OUTPUT
### Client 

![{64E2A46B-F59D-4B7C-A52C-F9AC3B1B1B1D}](https://github.com/user-attachments/assets/e23b7edd-1b7d-4614-9a56-125acfb6f37d)

### server

![{29554CE8-3ECF-40E3-8275-860BE9B88328}](https://github.com/user-attachments/assets/5c7d2547-5e53-4d11-8385-2f1cde49bb7a)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
