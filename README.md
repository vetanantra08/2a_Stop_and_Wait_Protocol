# 2a_Stop_and_Wait_Protocol
## Name:vetanantra.r.s
## Reg no:212225040486
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
server.py
~~~
import socket

s = socket.socket()
s.bind(('localhost',8000))
s.listen(1)

print("Server is listening...")

conn, addr = s.accept()
print("Connected with", addr)

while True:
    data = conn.recv(1024).decode()
    print("Client:", data)

    conn.send("Acknowledgement Received".encode())

    if data.lower() == "exit":
        break

conn.close()
~~~
client
~~~
import socket

s = socket.socket()
s.connect(('localhost',8000))

while True:
    msg = input("Enter message: ")
    s.send(msg.encode())

    print("Server:", s.recv(1024).decode())

    if msg.lower() == "exit":
        break

s.close()
~~~

## OUTPUT
<img width="944" height="194" alt="Screenshot 2026-03-12 090257" src="https://github.com/user-attachments/assets/97c4abe0-bc38-445c-8949-56827d6a9765" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
