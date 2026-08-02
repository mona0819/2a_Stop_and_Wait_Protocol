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
client.py
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
server.py
```python
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived frome the server".encode())
```
## OUTPUT
client.py
<img width="930" height="216" alt="image" src="https://github.com/user-attachments/assets/a1822596-f32d-4607-ad63-5958d5cb2a76" />
server.py
<img width="985" height="181" alt="image" src="https://github.com/user-attachments/assets/ceb3275a-e807-418a-8140-09c43662a9dc" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
