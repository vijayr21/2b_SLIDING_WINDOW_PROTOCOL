# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM:
To implement the sliding window protocal using Python.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
client:
```
VIJAY R
212223240178
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
   while(i<len(l)):
    st+=s
    c.send(str(l[i:st]).encode())
    ack=c.recv(1024).decode()
    if ack:
       print(ack)
       i+=s
```
server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
## OUPUT
client
![Screenshot 2024-05-11 162741](https://github.com/vijayr21/2b_SLIDING_WINDOW_PROTOCOL/assets/149347607/b0d21258-bb86-4a50-808c-0dd47ee91a14)
server
![Screenshot 2024-05-11 162748](https://github.com/vijayr21/2b_SLIDING_WINDOW_PROTOCOL/assets/149347607/38b71bda-5b4f-4792-9096-9958547c9cc1)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
