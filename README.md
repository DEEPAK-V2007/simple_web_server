# EX01 Developing a Simple Webserver

# Date:19-09-25
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
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laptop Specification</title>
    <style>
    ol li{
        color: blue;
        font-family: Times New Roman, Serif;
    }
    body
    {
    background-color:lavender;
    }

    </style>
</head>
<body>
<h1 align='center'><u>Laptop Specifications</u></h1><br>
<p>
<h2><u>Device specification</u></h2>
<ol Type='1' start='1'>
<h3><li>Device name: TMP215-75-G2</h3></li>
<h3><li>Processor: Intel(R)Core(TM) Ultra 5 125H (1.20 GHz)</h3></li>
<h3><li>Installed RAM: 16.0 GB (15.5 GB usable)</h3></li>
<h3><li>Device ID: E3F06795-1915-4187-8C56-F3F3634559FF</h3></li>
<h3><li>Product ID: 00342-42784-08509-AAOEM</h3></li>
<h3><li>System type: 64-bit operating system, x64-based processor</h3></li>
<h3><li>Pen and touch: No pen or touch input is available for this display</h3></li>
</ol><br>
<h2><u>Windows Specification</u></h2>
<ol Type='1' start='1'>
<h3><li>Edition: Windows 11 Home Single Language</h3></li>
<h3><li>Version: 24Hz</h3></li>
<h3><li>Installed on: 01-09-2025</h3></li>
<h3><li>OS build: 26100.6584</h3></li>
<h3><li>Experience: Windows Feature Experience Pack 1000.26100.234.0</h3></li>
</ol>
</p>
</body>
</html>'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my Webserver")
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
# OUTPUT:

![alt text](<Screenshot 2025-09-19 120130.png>)

![alt text](<Screenshot 2025-09-29 083428.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
