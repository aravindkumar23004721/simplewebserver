# EX01 Developing a Simple Webserver
## Date:
12-03-2024

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
<!DOCTYPE html>
<html>
<head>
<title>Top 5 Software Companies With Revenue</title>
</head>
<body bgcolor="cyan">
<table border="3" cellspacing="4" cellpadding="6" align="center" bgcolor="pink">
<caption>TOP FIVE REVENUE GENERATING SOFTWARE COMPANIES </caption>
             <tr>
               <th>Sno</th>
               <th>Company Name</th>
               <th>Revenue</th>
               <th>todays</th>
               <th>country</th>
          </tr>
           <tr>
               <td>01</td>
               <td>Microsoft</td>
               <td>$161 billion</td>
               <td>-1.18%</td>
               <td>USA</td>
          </tr>
          <tr>
               <td>02</td>
               <td>Oracle</td>
               <td>$48 billion</td>
               <td>-1.94%</td>
               <td>USA</td>
          </tr>
          <tr>
               <td>03</td>
               <td>Adobe</td>
               <td>$16 billion</td>
               <td>-1.54%</td>
               <td>USA</td>

          </tr>
          <tr>
               <td>04</td>
               <td>Salesforce</td>
               <td>$14 billion</td>
               <td>-1.86%</td>
               <td>USA</td>

          </tr>
          <tr>
               <td>05</td>
               <td>SAP</td>
               <td>$12 billion</td>
               <td>-1.46%</td>
               <td>USA</td>

          </tr>
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
![Screenshot (2)](https://github.com/aravindkumar23004721/simplewebserver/assets/148962674/85859548-7f5c-477f-93dd-e3eaacaf1453)
![Screenshot 2024-03-12 113322](https://github.com/aravindkumar23004721/simplewebserver/assets/148962674/6d1b4b78-c602-4c4c-a7ec-d31206fada6e)
## RESULT:
The program for implementing simple webserver is executed successfully.
