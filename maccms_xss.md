maccms Background member information exists xss

version：v10 

Software download address：http://www.maccms.com

Login to the background to enter the user-> member module -> editing function

![image-20200402154009909](/Users/shiqi/Documents/penTestWrite/1.png)

Write payload to the nickname in the edit window (```“><img src=x onerror=alert(1)>```)

![image-20200402154107749](/Users/shiqi/Documents/penTestWrite/2.png)

Click save. Save successfully

![image-20200402154239110](/Users/shiqi/Library/Application Support/typora-user-images/image-20200402154239110.png)

The XSS attack is triggered when the administrator edits the user again

![image-20200402154412474](/Users/shiqi/Library/Application Support/typora-user-images/image-20200402154412474.png)

An XSS attack is also triggered when the user logs in

![image-20200402154506665](/Users/shiqi/Library/Application Support/typora-user-images/image-20200402154506665.png)

in /application/admin/controller/User.php

![image-20200402154712926](/Users/shiqi/Documents/penTestWrite/6.png)

XSS occurs when the data is not filtered while accepting the post data at the time of the saved information

in /application/admin/view/user/info.html

![image-20200402154835909](/Users/shiqi/Documents/penTestWrite/7.png)

Data is also not filtered when user nicknames are returned



