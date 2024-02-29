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
# client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

```
# server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
    

```
## OUTPUT
# clint:
![Screenshot 2024-02-29 204329](https://github.com/23012312/2a_Stop_and_Wait_Protocol/assets/150009714/02bef712-a961-4f3b-a76c-7c480e1df172)

# server:
![Screenshot 2024-02-29 204343](https://github.com/23012312/2a_Stop_and_Wait_Protocol/assets/150009714/bae820c2-58cf-42a5-baa4-b03f1d33e2c3)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
