# EX01 Developing a Simple Webserver
## Date:26.10.2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
'''
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
    <head>
        <title>
            MY SERVER
        </title>
    </head>
    <body>
        <table border="2" bgcolor="Cyan" cellpadding="20">
            <caption>
                LAPTOP CONFIGURATION
            </caption>
            <tr>
                <th>S.NO</th>
                <th>SPECIFICATIONS</th>
                <th>DETAILS</th>
            </tr>
            <tr>
                <td>1.</td>
                <td>Device Name</td>
                <td>Sangeetha</td>
            </tr>
            <tr>
                <td>2.</td>
                <td>Processor</td>
                <td>13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</td>
            </tr>
            <tr>
                <td>3.</td>
                <td>RAM</td>
                <td>16.0 GB (15.7 GB usable)</td>
            </tr>
            <tr>
                <td>4.</td>
                <td>Device ID</td>
                <td>15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
            </tr>
            <tr>
                <td>5.</td>
                <td>Product ID</td>
                <td>00342-42708-33488-AAOEM</td>
            </tr>
            <tr>
                <td>6.</td>
                <td>Version</td>
                <td>Windows 11</td>
            </tr>
            <tr>
                <td>7.</td>
                <td>System type</td>
                <td>64-bit operating system, x64-based processor</td>
            </tr>

            
        </table>  
    </body>
</html>
'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
'''

## OUTPUT:
![alt text](<Screenshot (4).png>)

![alt text](<Screenshot 2024-10-26 133208.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
