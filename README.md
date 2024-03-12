# EX01 Developing a Simple Webserver
## Date: 14.02.2024

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
<title>SOFTWARE COMPANIES</title>
</head>
<body bgcolor="pink" align="center">
<h1> < TOP FIVE REVENUE GENERATING SOFTWARE COMPANIES >  </h1>
<table align="center" border="20" cellspacing="10" cellpadding="5">
<tr>
<th>RANK</th>
<th>COMPANY NAME</th>
<th>REVENUE(in $000s)</th>
</tr>
<tr>
<td>1</td>
<td>APPLE</td>
<td>1,859</td>
</tr>
<tr>
<td>2</td>
<td>FACEBOOK</td>
<td>1,621</td>
</tr>
<tr>
<td>3</td>
<td>ALPHABET</td>
<td>1,253</td>
</tr>
<tr>
<td>4</td>
<td>VERISIGN</td>
<td>1,154</td>
</tr>
<tr>
<td>5</td>
<td>VISA</td>
<td>1,062</td>
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
![EX-01 WEB OUTPUT](https://github.com/Oviya24032K6/simplewebserver/assets/147139999/ee864305-e718-45fb-9e89-9c5c3fdef758)
![EX-01 WEB terminal](https://github.com/Oviya24032K6/simplewebserver/assets/147139999/ffaa3d5f-f7e8-42f5-9278-286fb4c512be)

## RESULT:
The program for implementing simple webserver is executed successfully.
