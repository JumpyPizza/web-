# Django
## 路由
Django的urls.py中，可以将浏览器输入的url映射到views.py中的函数。path中的参数，'r'后面用正则匹配url，views.函数名映射views中的功能。  
## Views
在views中，浏览器请求的url映射到views中的函数，函数接受（request)，进行操作。  
例如，可以判断请求的方法：request.method == 'POST'。 django自带了验证用户的模块，contrib.auth中的authenticate, login。 authenticate(request, 后面接受想要验证的参数，比如定义request.POST['name']为一个值，如果authenticate验证的值在auth中的user表里面的话，则返回一个user的object，如果不在，返回None。 python中的Null就是None。    
函数还可以返回 render或者redirect。 render是渲染后面参数中的模板，render的第一个参数是request，第二个是模板文件夹下面的html。还可以接受渲染的内容：用字典来表示{'key': 'value'}，然后在要渲染的地方{{key}}。
Django的template下，要新建一个与app名称相同的文件夹，把HTML放到这个文件夹下面。  
## {{% url' '}}
这里对url后面的地址发出get请求，比如{{% url'logout'}}所以即便没有这个.../logout这个html页面，只要在urlpatterns里面定义了logout这个地址，并且映射了相应函数，那么对这个地址请求，就会向那个函数发出请求。
## 验证是否登录  
使用装饰器。 从contrib.auth.decorators里面import login_required，在要访问的view函数前面加上这个装饰器
## 部署
apache logdir: /www/log/apache2/error.log
部署时，应该参考官方文档！ 需要在apache2.conf里面加上WSGIPythonPath！！ 不然会报错package not found和mod_wsgi cannot be loaded as python package。
使用python3时，需要安装的是libapache2-mod-wsgi-py3！如果装了别的可以用sudo pkcg -purge package-name删掉。
总结：在Linux上：  
1. 设置默认使用python3
2. 安装pip
3. 安装 django、libapache2-mod-wsgi-py3
4. 将项目文件上传到/var/www/下
5. 在wsgi.py添加项目路径
6. 配置virtual host、参考官方文档在apache2.conf里面配置PythoPath，不然wsgi执行时不会在项目里面找模块，而是去解释器那里找。
7. 设置刚刚配置的conf为sites-enabled
8. 每次作更改都要sudo service apache2 restart
9. 文件夹与文件的权限设置好
