# EX01 Developing a Simple Webserver
## Date:07-10-2025

## AIM:
To develop a simple webserver to serve html pages and display the Device Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
Html:

<!doctype html>
<python html>
<head>
<title> My Web Server</title>
</head>
<body>
<table align="center" border="1" bgcolor="cyan" cellpadding="10">
  <caption>LIST OF PROTOCOL IN TCP/IP PROTOCOLSUITE </caption>
  <tr> <th bgcolor="brown">S.No.</th><th bgcolor="brown">Name of the layers</th><th bgcolor="brown"> Name of the protocol</th></tr>
  <tr><td bgcolor="red">1</td><td bgcolor="red"> Application layer </td><td bgcolor="red">HTTP,FTP,DNS,Telnet & SS b </td></tr>
  <tr><td bgcolor="pink">2</td><td bgcolor="pink"> Transport Layer </td><td bgcolor="pink">TCP & UDP <br> ( std )</td></tr>
  <tr><td bgcolor="red">3</td><td bgcolor="red"> Network Layer </td><td bgcolor="red"> IP4/IPv6 </td></tr>
  <tr><td bgcolor="pink">4</td><td bgcolor="pink">Link Layer </td><td bgcolor="pink">Ethernets </td></tr>
</table>
</body>
</html>

```

python
```
from http.server import HTTPServer, BaseHTTPRequestHandler

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        with open("simplewebserver.html", "r") as f:
            content = f.read()
            self.wfile.write(content.encode())

print("This is my webserver")
server_address = ('', 8000)
httpd = HTTPServer(server_address, MyServer)
httpd.serve_forever()
```

## OUTPUT:

<img width="1904" height="951" alt="image" src="https://github.com/user-attachments/assets/e4af05d7-2ef7-4763-822a-405f56945308" />

## RESULT:
The program for implementing simple webserver is executed successfully.
