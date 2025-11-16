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
```python
import socket
s=socket.socket()
s.bind(('localhost', 8001))
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
```python
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived frome the server".encode())
```
## OUTPUT
Refer to the screenshot below to see the program's output.
## Server

<img width="725" height="138" alt="image" src="https://github.com/user-attachments/assets/c98c878e-d2d2-4942-a240-5308c6e953cf" />

## Client

<img width="700" height="137" alt="image" src="https://github.com/user-attachments/assets/b9d8e5b7-9db5-48e0-a534-111c1fe33389" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
