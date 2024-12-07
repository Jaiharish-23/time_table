# Ex03 Time Table
# Date:30:9:2024
# AIM
To write a html webpage page to display your slot timetable.

# ALGORITHM
## STEP 1
Create a Django-admin Interface.

## STEP 2
Create a static folder and inert HTML code.

## STEP 3
Create a simple table using <table> tag in html.

## STEP 4
Add header row using <th> tag.

## STEP 5
Add your timetable using <td> tag.

## STEP 6
Execute the program using runserver command.

# PROGRAM
views.py
```
from django.http import HttpResponse

def timetable (request):
    host = request.get_host()
    port = host.split(':')[1]
    print(f'The server is running on the port {port}')
    print('GET request received...')
    html_content = """
          <!DOCTYPE html>
<html lang="en">
    <head>
        <title>TIMETABLE</title>
        <link rel="icon" href="c:\Users\admin\Downloads\time-management-system.png">
        <style>
            body{
                background-repeat: no-repeat;
                background-size:cover;
                background-position: center;
            }
            span{
                writing-mode:vertical-lr;
                text-orientation:upright;
            }
        </style>
    </head>
     <body style="color:WHITE;" background="c:\Users\admin\Downloads\natural.jpg">
        <center>
            <IMG SRC="c:\Users\admin\Downloads\saveetha_logo.png" width="600" height="100" border="4">
            <HR>
            <H1 STYLE="COLOR: WHITE; background-color: rgb(7, 222, 255);">
            <MARQUEE>⊹ ࣪ ﹏𓊝﹏𓂁﹏⊹ ࣪ ˖🗓️TIMETABLE🗓️⊹ ࣪ ﹏𓊝﹏𓂁﹏⊹ ࣪ ˖</MARQUEE></H1>
            <HR>
            <table BORDER="1" WIDTH="1500" HEIGHT="600" STYLE="background-color:rgb(255, 0, 111);">
                <tr bgcolor="AQUA">
                    <td >DAY/TIME</td>
                    <td>8AM-10AM</td>
                    <td>10AM-12PM</td>
                    <td>12PM-1PM</td>
                    <td >1PM-3PM</td>
                    <td>3PM-5PM</td> 
                </tr>
                <tr>
                    <td bgcolor="AQUA">MONDAY</td>
                    <td>FREE SLOT</td> <td>PYT</td>
                    <td rowspan="6"><CENTER><H4><span>LUNCH</span></H4></CENTER></td>
                    <td>WEB</td>
                    <td>FREE SLOT</td>
                </tr>
                <tr>
                    <td bgcolor="AQUA">TUESDAY</td>
                    <td>FREE SLOT</td>
                    <td>FREE SLOT</td>
                    <td>CHEM</td>
                    <td>DIGE</td> 
                </tr>
                <TR>
                    <TD bgcolor="AQUA">WEDNESDAY</TD>
                    <td>PYT</td>
                    <td>CAL</td>
                    <td>MEN</td>
                    <td>FREE SLOT</td> 
                </TR>
                <TR>
                    <TD bgcolor="AQUA">THURSDAY</TD>
                    <td>FREE SLOT</td>
                    <td>FREE SLOT</td>
                    <td>DIGE</td>
                    <td>FREE SLOT</td> 
                </TR>
                <TR>
                    <TD bgcolor="AQUA">FRIDAY</TD>
                    <td>CHEM</td>
                    <td>WEB</td>
                    <td>CAL</td>
                    <td>FREE SLOT</td> 
                </TR>
                <TR>
                   <TD bgcolor="AQUA">SATURDAY</TD>
                    <td>FREE SLOT</td>
                    <td>WEB</td>
                    <td>FREE SLOT</td>
                    <td>FREE SLOT</td> 
                </TR>
            
            </table>
            <TABLE BORDER="1">
                <TR>
                    <TH>S.NO:</TH><TH>COURSE CODE</TH> <TH>COURSE NAME</TH>
                </TR>
                <TR>
                    <TD>1.</TD> <TD>19AI1301</TD>
                    <TD>PYT-PYTHON PROGRAMMING</TD>
                </TR>
                <TR>
                    <TD>2.</TD> <TD>19CY205</TD>
                    <TD>CHEM-PRINCIPLES OF CHEMISTRY IN ENGINEERING</TD>
                </TR>
                <TR>
                    <TD>3.</TD> <TD>19EE404</TD>
                    <TD>DIGE-DIGITAL ELECTRONIC</TD>
                </TR>
                <TR>
                    <TD>4.</TD> <TD>19AI414</TD>
                    <TD>WEB-FUNDAMENTALS OF WEB APPLICATION DEVELOPMENT</TD>
                </TR>
                <TR>
                    <TD>5.</TD> <TD>19MA201</TD>
                    <TD>>CAL-CALCULUS AND MATRIX ALGEBRA</TD>
                </TR>
                <TR>
                    <TD>6.</TD> <TD>ECA-M-SCOFT</TD>
                    <TD>MEN-MENTOR MEET</TD>
                </TR>
            
            </TABLE>
        </CENTER>
        <h1 style="background-color:whEAT;">
        <marquee>ִִֶֶָָ𓂃 ࣪˖ ִֶָ🐇་༘࿐ִֶָ𓂃 ࣪˖ ִֶָ🐇་༘࿐ִֶָ𓂃 ࣪˖ ִֶָ🐇་༘࿐ִֶָ𓂃 ࣪˖ ִֶָ🐇་༘࿐ִֶָ𓂃 ࣪˖ ִֶָ🐇་༘</marquee></h1>
            
        <h1 ALIGN="RIGHT"  STYLE="COLOR: BLACK ;background-color:whitesmoke;">
        <MARQUEE> ࣪ ﹏𓊝﹏𓂁﹏⊹ ࣪ DONE BY:JAI HARISH.R ࣪ ﹏𓊝﹏𓂁﹏⊹ ࣪ </MARQUEE></h1>
    </body>
</htmL>
    """
    response = HttpResponse(html_content, status=200) 
    print(f'Status code {response.status_code}')
    print('HTML response sent successfully.')
    return response
```
urls.py (app)
```
from django.urls import path
from .views import timetable

urlpatterns = [
    path('', timetable, name='timetable'),
]
```
urls.py (project)
```
from django.contrib import admin
from django.urls import path ,include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('timetable/', include('app.urls')),
]
```
# OUTPUT
![screencapture-file-C-Users-admin-Desktop-HTML-STARTING-POINT-timetable-html-2024-11-30-11_02_45](https://github.com/user-attachments/assets/a6ebeb74-a07b-4641-9a94-c5818fa08671)
![{4C73C46E-0F55-4AF5-B92F-332E0F84A851}](https://github.com/user-attachments/assets/ef8ad9a3-826a-42dc-b697-43d89694b4a8)

# RESULT
The program for creating slot timetable using basic HTML tags is executed successfully.
