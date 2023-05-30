# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE :

## AIM :
To write a python program to perform client server model.


## ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program




## CLIENT PROGRAM :
## Developed By : Kalpana S
## Reg No : 212222040069
import socket

s=socket.socket()

s.bind(('localhost',8080))

s.listen(5)

c,addr=s.accept()

while True:

	i=input("ENter a data:")
	
	c.send(i.encode())
	
	ack=c.recv(1024).decode()
	
	if ack:
	
		print(ack)
		
		continue
		
	else:
	
		c.close()
		
		break
		

## SERVER PROGRAM :
import socket

s=socket.socket()

s.connect(('localhost',8080))

while True:
	
	print(s.recv(1024).decode())
	
	s.send("Recieved".encode())



## OUTPUT:
## SERVER OUTPUT:
![server output](https://github.com/Kalpanareshma/19CS406-EX-1/assets/122040453/73247d2a-81e7-45d5-b455-6cdcb5e1d22b)
## CLIENT OUTPUT:
![CLIENT OUTPUT](https://github.com/Kalpanareshma/19CS406-EX-1/assets/122040453/15b717be-4ee9-4dd5-a21d-2481e46af17b)





## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.


