## python 开发环境 ##
1. python2.7
2. pip/easy_install
3. pycharm
4. virtualenv 

### 安装python module###
```
pip install --upgrade pip
pip install pycurl pyyaml PyCrypto ramdon2 Scrapy Cypthon
pip install pycrypto requests lettuce selenium nose lettuce_webdriver
pip install -r requirements.txt
```
####requirements.txt
```
Django==1.5.5
Jinja2==2.6
Pygments==1.5
Sphinx==1.1.3
coverage==3.5.2
cssselect==0.7.1
docutils==0.9.1
fuzzywuzzy==0.1
lxml
mock==1.0b1
mox==0.5.3
python-subunit==0.0.13
sure==1.1.7
tornado==2.3
tox==1.4.2
markment==0.1.6
steadymark==0.4.5
testtools==0.9.34
```

### python 调用 java 类 ###
[使用Pyjnius实现python代码中调用java类](https://github.com/liyi193328/stockAnalysis/wiki/%E4%BD%BF%E7%94%A8Pyjnius%E5%AE%9E%E7%8E%B0python%E4%BB%A3%E7%A0%81%E4%B8%AD%E8%B0%83%E7%94%A8java%E7%B1%BB)
```
pip install Pyjnius

# python code sample
import os
import sys

class myclass:
    def __init__(self, jar_path=None):
        # set java classpath to load 
        if jar_path is None:
            jar_path = "/mnt/d/workspace/example.jar"  
        os.environ['CLASSPATH'] = jar_path

    def dosomething(self, src, key):
        from jnius import autoclass
        # load java class  
        Example = autoclass('com.unknown.Example')
        if src is None or key is None:
            return None
        else:
            value = Example().dosomething(src, key)
        return value


if __name__ == '__main__':
    instance_1 = myclass()
    if  len(sys.argv)>= 2:
        code = instance_1.dosomething(sys.argv[1], sys.argv[2])
    else:
        code = instance_1.dosomething("123test123456", "456")
    print code
```

### BDD lettuce 环境搭建 ###
[python BDD 框架之lettuce](http://www.cnblogs.com/fnng/p/3415609.html)
[教程:BDD with Python (Cucumber/Gherkin for Python)](https://www.udemy.com/bdd-testing-with-python/)
[cucumber in java](http://blog.csdn.net/henni_719/article/details/53608144)