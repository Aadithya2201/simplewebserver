# EX01 Developing a Simple Webserver
## Date:26.02.24

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
        <title>My webserver</title>
    </head>
    <body>
        <table border="2" cellspacing="5" cellpading="" width="100" height="50">
            <br>
            <br>

            
            <caption>
            HCL Tech Q1FY24 estimates
            </caption>
            <tr>
                <th align="center" bgcolor= "red" style="color:white;">Brokerage</th>
                <th align="center" bgcolor= "red" style="color:white;">Revenue</th>
                <th align="center" bgcolor= "red" style="color:white;">PAT</th>
                <th align="center" bgcolor= "red" style="color:white;">Ebit margin</th>
                
            </tr>
                <td align="center" bgcolor="orange">HSBC</td>
                <td align="center" bgcolor= "black" style="color:white;">26,987</td>
                <td align="center" bgcolor= "black" style="color:white;">3,776</td>
                <td align="center" bgcolor= "black" style="color:white;">17.5</td>
            </tr>
            <tr>
                <td align="center" bgcolor="orange">Jefferies</td>
                <td align="center" bgcolor= "black" style="color:white;">26,891</td>
                <td align="center" bgcolor= "black" style="color:white;">3,785</td>
                <td align="center" bgcolor= "black" style="color:white;">18</td>
            </tr>
            <tr>
                <td align="center" bgcolor="orange">HDFC Research</td>
                <td align="center" bgcolor= "black" style="color:white;">26,963</td>
                <td align="center" bgcolor= "black" style="color:white;">3,773</td>
                <td align="center" bgcolor= "black" style="color:white;">18</td>                </tr>
            <tr>
                <td align="center" bgcolor="orange">PhillipCapital</td>
                <td align="center" bgcolor= "black" style="color:white;">26,806</td>
                <td align="center" bgcolor= "black" style="color:white;">3,821</td>
                <td align="center" bgcolor= "black" style="color:white;">18.2</td>
            </tr>
            <tr>
                <td align="center" bgcolor="orange">Motilal Oswal</td>
                <td align="center" bgcolor= "black" style="color:white;">26,700</td>
                <td align="center" bgcolor= "black" style="color:white;">3,900</td>
                <td align="center" bgcolor= "black" style="color:white;">18.4</td>
            </tr>
            <tr>
                <td align="center" bgcolor="orange">BoB Capital</td>
                <td align="center" bgcolor= "black" style="color:white;">26,978</td>
                <td align="center" bgcolor= "black" style="color:white;">3,877</td>
                <td align="center" bgcolor= "black" style="color:white;">17.9</td>
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

![alt text](<Screenshot (6).png>)
![alt text](<Screenshot (7).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
