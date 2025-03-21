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
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

server.py
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT
CLIENT:

![Screenshot 2025-03-21 143142](https://github.com/user-attachments/assets/ccf47455-d8d7-42f4-b04a-e93137c10f6b)

SERVER:

![Screenshot 2025-03-21 140056](https://github.com/user-attachments/assets/b42865ac-cdb6-4e94-9ebe-3fc33336c34c)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
