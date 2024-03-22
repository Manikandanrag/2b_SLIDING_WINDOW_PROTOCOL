# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
To write a python program to perform sliding window protocol
## ALGORITHM:
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
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s

```
### SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
REG NO:
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())

```
## OUPUT
![Screenshot 2024-03-08 143703](https://github.com/Manikandanrag/2b_SLIDING_WINDOW_PROTOCOL/assets/138849491/918b15d0-50af-44b6-b7d9-40aa32af47c0)
![Screenshot 2024-03-08 143717](https://github.com/Manikandanrag/2b_SLIDING_WINDOW_PROTOCOL/assets/138849491/a7a6a43c-9cb5-4bab-b844-678eecaf5b83)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
