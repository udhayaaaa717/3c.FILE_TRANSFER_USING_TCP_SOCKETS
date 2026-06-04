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
SERVER:
```
import socket 
# Create socket 
server = socket.socket() 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
# Listen for client 
server.listen(1) 
print("Server waiting for connection...") 
# Accept client 
client, addr = server.accept() 
print("Connected to:", addr) 
# Ask filename 
filename = input("Enter file name to send: ") 
# Open and send file 
with open(filename, "rb") as file: 
    data = file.read() 
client.send(data) 
print("File sent successfully") 
# Close connections 
client.close() 
server.close()
```
CLIENT:
```
import socket 
# Create socket 
client = socket.socket() 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
# Save file name 
save_name = input("Enter name to save file: ") 
# Receive data 
data = client.recv(1000000) 
# Save file 
with open(save_name, "wb") as file: 
    file.write(data) 
print("File received successfully") 
# Close connection 
client.close()
```
## OUPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/810418b1-1664-4d42-9815-567347a27ec2" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d0240c4f-1b9a-4419-a7fd-27eb61a7c2ad" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c8290c97-20d0-46a3-b4fb-e78d867cdb46" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d6c3f5bc-0995-454b-ad06-9a37cbd25f03" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
