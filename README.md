# EX01 Developing a Simple Webserver

# Date: 25/03/2025
# Name: Mohamed Zabir Khan A
# Register No: 24900623

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
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TCP/IP PROTOCOLS</title>
    <style>
        
        
        
        *{
            background: linear-gradient(rgba(214, 223, 159, 0.605),rgba(162, 209, 162, 0.7)),url(busustand.jpg);
            background-size: cover  ;
            background-position: center;
            
        }
        table {
            width: 50%;
            border-collapse: collapse;
            margin: 80px 0;
            align-items: center;
           
        }
        th, td {
            border: 1px solid #1c211f;
            padding: 8px;
            text-align: center;
            font-size: 30px;
        }
        th {
            background-color: #5e645e;
        }
        .head{
            text-align: center;
            font-size: 50px;
            
        }

           
            
        
        
    </style>
</head> 
<body>
    <div class="head">
        <b>TCP/IP PROTOCOLS SUITE.</b>
    </div>
    <center>
    <table style="border: 5px;">
        <tr>
            <th>LAYER NAMES</th>
            <td>PROTOCOLS</td>
        </tr>
        <tr>
            <th>APPLICATION LAYER</th>
            <td>HTTP,FTP,POP3,SMTP,SNMP</td>
        </tr>
        <tr>
            <th>TRANSPORT LAYER</th>
            <td>TCP,UDP</td>
        </tr>
        <tr>
            <th>NETWORKING LAYER</th>
            <td>IP,ICMP</td>
        </tr>
        <tr>
            <th>DATALINK LAYER</th>
            <td>ETHERNET, ARP</td>
        </tr>                        
    </table>
</center>

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
# OUTPUT:

![alt text](<Screenshot 2025-03-25 094221.png>)

![alt text](<Screenshot 2025-03-25 094253.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
