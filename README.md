# EX01 Developing a Simple Webserver
## Date:28-02-2024

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
<title>My list Of companies</title>
</head>
<body>
<table border="5" cellspacing="7" cellpadding="7" width="40" height="50" bgcolor="yellow">c
<tr>
<th>Name of the Company</th>
<th>Period</th>
<th>Avg.Growth in sales</th>
<th>Avg.D/e</th>
<th>Avg.ROE</th>
</tr>
<tr>
<td>Cognizant Tech.</td>
<td>2004-10</td>
<td>50%</td>
<td>0.00</td>
<td>39%</td>
</tr>
<tr>
<td>Infosys</td>
<td>2001-06</td>
<td>50%</td>
<td>0.00</td>
<td>45%</td>
</tr>
<tr>
<td>L&T Infotech</td>
<td>2004-08</td>
<td>46%</td>
<td>0.69</td>
<td>43%</td>
</tr>
<tr>
<td>Mindtree</td>
<td>2004-09</td>
<td>54%</td>
<td>0.30</td>
<td>29%</td>
</tr>
<tr>
<td>Oracle India</td>
<td>2007-12</td>
<td>25%</td>
<td>0.00</td>
<td>66%</td>
</tr>
</table></body></html>
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

![alt text](<Screenshot (56).png>)

![alt text](<web Table.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
