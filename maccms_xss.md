maccms Background member information exists xss

version：v10 

Software download address：http://www.maccms.com

Login to the background to enter the user-> member module -> editing function

![image](https://github.com/Ksharp12138/maccms_userinfo_xss/blob/master/images/1.png)

Write payload to the nickname in the edit window (```“><img src=x onerror=alert(1)>```)

![image](https://github.com/Ksharp12138/maccms_userinfo_xss/blob/master/images/2.png)

Click save. Save successfully

![image](https://github.com/Ksharp12138/maccms_userinfo_xss/blob/master/images/3.png)

The XSS attack is triggered when the administrator edits the user again

![image](https://github.com/Ksharp12138/maccms_userinfo_xss/blob/master/images/4.png)

An XSS attack is also triggered when the user logs in

![image](https://github.com/Ksharp12138/maccms_userinfo_xss/blob/master/images/5.png)

in /application/admin/controller/User.php

![image](https://github.com/Ksharp12138/maccms_userinfo_xss/blob/master/images/6.png)

XSS occurs when the data is not filtered while accepting the post data at the time of the saved information

in /application/admin/view/user/info.html

![image](https://github.com/Ksharp12138/maccms_userinfo_xss/blob/master/images/7.png)

Data is also not filtered when user nicknames are returned
