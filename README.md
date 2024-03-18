# EX01 Developing a Simple Webserver

## Date : 18/03/2024

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:

```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
      <head> 
            <title>Top Software Companies Revenue</title>
      </head>
      <body>
      <table border="4" cellspacing="5" width="40" heigth="50"
        <caption> REVENUE </caption>
        <tr>
             <th>RANK</th>
             <th>VENDOR</th>
             <th>COUNTRY HQ</th>
             <th>REVENUE</th>
        </tr>
        <tr>
             <td>1</td>
             <td>Microsoft</td>
             <td>USA</td>
             <td>62,014</td>
        </tr>
        <tr>
             <td>2</td>
             <td>Oracle</td>
             <td>USA</td>
             <td>29,881</td>
        </tr>
        <tr>
             <td>3</td>
             <td>IBM</td>
             <td>USA</td>
             <td>29,286</td>
        </tr>
        <tr>
             <td>4</td>
             <td>SAP</td>
             <td>GERMANY</td>
             <td>18,777</td>
        </tr>
        <tr>
             <td>5</td>
             <td>SYMANTEC</td>
             <td>USA</td>
             <td>6,138</td>  
        </tr>
        </table>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:

![alt text](<company revenue.png>)

![alt text](<server running terminal screenshot.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
