# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
```
client
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))
s.send("Hello Server".encode())
file = open("received_file.txt", "wb")
print("Receiving file...")
while True:
    data = s.recv(1024)
    if not data:
        break
    file.write(data)
print("File received successfully")
file.close()
s.close()
server
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.bind((host, port))
s.listen(1)
print("Server listening...")
c, addr = s.accept()
print("Connected with", addr)
msg = c.recv(1024).decode()
print("Client says:", msg)
filename = "C:/Users/vidhya shree/Desktop/New folder/sample.txt"
file = open(filename, "rb")
data = file.read(1024)
while data:
    c.send(data)
    data = file.read(1024)
print("File sent successfully")
file.close()
c.close()
s.close()
```
## OUTPUT
client
<img width="1846" height="963" alt="Screenshot 2026-05-28 214057" src="https://github.com/user-attachments/assets/52014b96-b95d-4020-8ed1-67e3f5d18c70" />
server
<img width="1850" height="969" alt="Screenshot 2026-05-28 214040" src="https://github.com/user-attachments/assets/f18ee0b8-40f6-4d0b-a567-e3f6b886105a" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
