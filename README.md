# EX01 Developing a Simple Webserver

# Date:26.02.2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Welcome<h1>
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

# OUTPUT:
![Screenshot 2025-03-07 101954](https://github.com/user-attachments/assets/f4d83e09-883d-47ea-9f54-e2af652bd86f)

![Screenshot 2025-03-05 153016](https://github.com/user-attachments/assets/b6011677-850c-4e98-a384-5ff263dc7c30)

# RESULT:
The program for implementing simple webserver is executed successfully.
