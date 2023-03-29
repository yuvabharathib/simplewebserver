# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation

### Step 2:
Design of webserver workflow

### Step 3:
Implementation using Python code

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1><u>Languages used iun Web Development</u><h1>
<ul>
<li>HTML</li>
<li>CSS</li>
<li>JavaScript</li>
<li>Bootstrap</li>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![out1](https://user-images.githubusercontent.com/113497404/228559828-2c6abdda-4be3-476a-9ae0-973f9989935f.png)

![out2](https://user-images.githubusercontent.com/113497404/228559964-f9ca9660-11b1-477e-ba7e-3a49c48384ec.png)



## RESULT:
The program for implementing simple webserver is executed successfully.
