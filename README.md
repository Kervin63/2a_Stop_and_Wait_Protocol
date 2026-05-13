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
Developed by : KERVIN.S Reg No : 212225220051
## Server Program
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for connection...")
conn, addr = s.accept()
print("Connected to", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print("Frame received:", data)
    conn.send("ACK".encode())

conn.close()

```

## Client Program
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

n = int(input("Enter number of frames: "))

for i in range(n):
    msg = input("Enter frame: ")
    s.send(msg.encode())

    ack = s.recv(1024).decode()
    print("Received:", ack)

s.close()
```
## OUTPUT

## Server
<img width="1920" height="1080" alt="Screenshot 2026-05-13 083304" src="https://github.com/user-attachments/assets/3a095cea-f29a-4522-ae86-7a226300e733" />

## Client
<img width="1920" height="1080" alt="Screenshot 2026-05-13 083246" src="https://github.com/user-attachments/assets/8cb9a2fc-1264-4665-853c-7a887e472129" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
