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
### Server :
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

### Client :

```
import socket
s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recieved".encode())

```

## OUTPUT :

### Server :

<img width="1458" height="308" alt="image" src="https://github.com/user-attachments/assets/a72ae5ac-c62e-468a-a4e4-02de272b6e29" />

### Client :

<img width="1804" height="188" alt="image" src="https://github.com/user-attachments/assets/d9d2013b-38dd-4959-bd65-7f381e3d422f" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
