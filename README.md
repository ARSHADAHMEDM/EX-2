# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

## DATE:16-03-2023

# AIM :
### To write a python program to perform stop and wait protocol



# ALGORITHM :

### 1. Start the program.
### 2. Get the frame size from the user
### 3. To create the frame based on the user request.
### 4. To send frames to server from the client side.
### 5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
### 6. Stop the program


# SERVER PROGRAM :
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
# CLIENT PROGRAM:
```py
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

# SERVER OUTPUT :
![2s](https://github.com/ARSHADAHMEDM/EX-2/assets/128116503/218b9528-8012-4d2d-a1ff-6990bc2bb5ef)

# CLIENT OUTPUT:
![2c](https://github.com/ARSHADAHMEDM/EX-2/assets/128116503/33c3f313-06cd-49eb-b4b8-6a3eac62113f)





# RESULT :
### Thus, python program to perform stop and wait protocol was successfully executed.


