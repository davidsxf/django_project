python manage.py startapp pages

# django_project/settings.py
INSTALLED_APPS = [

    "pages",  # new
]


(.venv) $ git init
(.venv) $ git status


(.venv) > git status
(.venv) > git add -A
(.venv) > git commit -m "initial commit"


(.venv) $ git remote add origin https://github.com/davidsxf/django_project.git
(.venv) $ git branch -M main
(.venv) $ git push -u origin main


https://djangoforbeginners.com/message-board/


单个位置会更加高效。如果您查看现有文件的底部附近django_project/settings.py，您会发现已经有一个STATIC_URL的配置，它指的是生产中所有静态文件的URL 位置。换句话说，如果我们的网站有 URL example.com，则所有静态文件都可以在example.com/static.

# django_project/settings.py
STATIC_URL = "static/"
内置管理命令collectstatic执行将所有静态文件编译到文件系统上的一个位置的任务。文件系统中静态文件的位置是通过STATIC_ROOT设置的。虽然我们可以灵活地将这个新目录命名为任何我们想要的名称，但传统上，它被称为staticfiles.以下是在我们的项目中进行设置的方法：

# django_project/settings.py
STATIC_URL = "static/"
STATIC_ROOT = BASE_DIR / "staticfiles"  # new
现在python manage.py collectstatic在命令行上运行，并将项目的所有静态文件编译到一个名为 的新根级目录中staticfiles。

(.venv) $ python manage.py collectstatic