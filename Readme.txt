第十八章
一：建立项目
1.Use Python3
2.Create虚拟环境：python -m venv ll_env
3.activate虚拟环境：ll_env\Scripts\activate
4.安装Django: pip install Django
5.新建一个项目：ll_env\Scripts\django-admin.exe startproject learning_log .
6.创建数据库：python manage.py migrate
7.查看项目：python manage.py runserver

二：创建应用程序
1.runserver运行的情况下，再打开一个终端，进入manage.py目录，激活虚拟环境
2.执行startapp：python manage.py startapp learning_logs

3.定义模型：在learning_log\learning_logs\models.py中定义Topic模型
4.激活模型：在learning_log\learning_log\settings.py中激活模型
5.需要让Django修改数据库，使其能够存储与模型Topic相关的信息:
	python manage.py makemigrations learning_logs
6.Django修改数据库：python manage.py migrate

7.Django管理网站：
	1)创建超级用户：python manage.py createsuperuser (ll_admin, root123456)
	2.向管理网站注册模型：打开learning_log\learning_logs\admin.py，修改文件内容

8.定义模型：在models.py中定义Entry模型
9.迁移模型：python manage.py makemigrations learning_logs
10.终端输入：python manage.py migrate

11.向管理网站注册Entry：修改admin.py

12.通过交互式终端查看数据：
	1)启动python解释器：python manage.py shell
	2)from learning_logs.models import Topic
	3)Topic.objects.all()
	4)...
	
三：创建网页
1.映射URL：learning_log\urls.py中，导入include模块，增加url
2.在learning_logs中创建urls.py， Django2.x版本中写上：app_name = 'learning_logs'
3.编写视图：修改learning_logs\views.py文件
4.编写模板：递归创建learning_logs\templates\learning_logs\index.html，编写代码

5.创建其他网页：
	1)创建base.html父模板
	2)修改index.html，使其继承base.html
	3)修改learning_logs\urls.py
	4)修改views.py
	5)新建topics.html，编写代码
	6)修改base.html
	
6.显示特定主题的页面：
	1)修改learning_logs/urls.py文件
	2)在views.py中定义topic函数
	3)新建topic.html文件
	4)修改topics.html文件
	
第十九章
一：用户能够输入数据
1.添加新主题：
	1)添加主题表单：在models.py文件夹中创建forms.py文件
	2)修改learning_logs/urls
	3)修改views.py
	4)创建new_bopic.html
	5)修改topics.html
	
2.添加新条目：
	1)修改forms.py
	2)修改urls.py
	3)修改views.py
	4)新建new_entry.html
	5)修改topic.html
	
3.编辑条目：
	1)修改urls.py
	2)修改views.py
	3)新建edit_entry.html
	4)修改topic.html
	
二：创建用户账户
1.应用程序users
	1)创建users
	2)修改settings.py
	3)修改根目录中的urls.py
	
2.登录页面：
	1)在users/目录下，新建urls.py文件
	2)递归创建users/templates/users/login.html
	3)修改base.html
	
3.注销：
	1)修改users/urls.py
	2)修改users/views.py
	3)修改base.html
	
4.注册页面：
	1)修改users/urls.py
	2)修改users/views.py
	3)创建register.html
	4)修改base.html
	
三：让用户拥有自己的数据
1.使用@login_required限制访问
	1)修改learning_logs/views.py
	2)修改settings.py
	3)修改learning_logs/views.py
	
2.将数据关联到用户
	1)修改models.py
	2)启动Django shell对话框，查询用户id
	3)迁移数据库
	
3.只允许用户访问自己的主题：
	1)修改learning_logs/views.py
	
4.保护用户的主题：
	1)修改learning_logs/views.py
	
5.保护页面edit_entry:
	1)修改learning_logs/views.py
	
6.将新主题关联到当前用户
	1)修改learning_logs/views.py
	
第二十章
一：设置项目"学习笔记"的样式
1.应用程序django-bootstrap3
	1)安装django-bootstrap3
	2)修改settings.py
	
2.使用Bootstrap来设置项目"学习笔记"的样式
3.修改base.html
4.使用jumbotron设置主页的样式:修改index.html
5.设置登录页面的样式：修改login.html
6.设置new_topic页面的样式：修改new_topic.html
7.设置topics页面的样式：修改topics.html
8.设置topic页面中条目的样式：修改topic.html

二：部署"学习笔记"



































