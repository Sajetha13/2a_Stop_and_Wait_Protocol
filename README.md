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
## Program:

#### Developed By: S Sajetha
#### Register Number: 212223100049

### Client:

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

### Server:

```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("Acknowledgement Recived".encode())
```

## Output:

### Client:

![image](https://github.com/user-attachments/assets/f7690111-e558-481f-b6f2-88a099439cf0)

### Server:

![image](https://github.com/user-attachments/assets/999dda3c-2d5f-4d3a-88a1-b14d783e90bd)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
