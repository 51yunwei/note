# django路由学习

## 获取前端传递参数的几种方式

### 1、url参数获取
**怎么将路由（url）的参数传到view？**

使用正则传递参数，传递的时候可以用位置参数传也可以用关键字参数传递


```python
# 路由设置 -- 位置参数，既([a-z])为第一个接受的参数，(\d{4})是第二个接受的参数，必须要用（）括起来
url(r"get_url_param/([a-z])/(\d{4})",view.get_url_param),

# view设置获取,对于位置参数变量名可以随便写都能获取到，这里的city获取到的就是([a-z])
def get_url_param(request,city,year):
    print(city,year)

# 路由设置 -- 关键字参数，?P指定这个正则的参数名字，view配置的接收参数名必须和这个一样，位置可以不一样
url(r"get_url_param/(?P<city>[a-z])/(?P<year>\d{4})",view.get_url_param),

# view配置
def get_url_param(request,city,year):
    print(city,year)
```