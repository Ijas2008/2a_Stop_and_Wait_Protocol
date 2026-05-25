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

Client.py :
```
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
Server.py :
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived frome the server".encode())
```
## OUTPUT
Client.py :

<img width="615" height="264" alt="Screenshot 2026-05-21 133450" src="https://github.com/user-attachments/assets/c37b1960-587c-4e2b-bd38-e5a2bd88b63f" />

Server.py :

<img width="643" height="143" alt="Screenshot 2026-05-21 133504" src="https://github.com/user-attachments/assets/85361f70-724f-47c8-876f-86e372044a57" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
