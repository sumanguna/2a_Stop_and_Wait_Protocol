# 2a_Stop_and_Wait_Protocol

### Name: Suman G
### Reg.NO: 212223240163
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
### CLIENT
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
### SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### CLIENT

<img width="936" alt="Screenshot 2024-04-09 at 11 50 59 AM" src="https://github.com/aaron-h-2k5/2a_Stop_and_Wait_Protocol/assets/144250957/906643c0-d47f-4347-998a-355c24101b8a">


### SERVER
<img width="936" alt="Screenshot 2024-04-09 at 11 51 03 AM" src="https://github.com/aaron-h-2k5/2a_Stop_and_Wait_Protocol/assets/144250957/89e34688-6baa-453c-ac09-5b8d7413e433">

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
