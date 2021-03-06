# 自连接 {#自连接}

* 对于地区信息，属于一对多关系，使用一张表，存储所有的信息
* 类似的表结构还应用于分类信息，可以实现无限级分类
* 新建模型AreaInfo，生成迁移

```
class AreaInfo(models.Model):
    atitle = models.CharField(max_length=20)
    aParent = models.ForeignKey('self', null=True, blank=True)
```

* 访问关联对象

```
上级对象：area.aParent
下级对象：area.areainfo_set.all()
```

* 在booktest/views.py中定义视图area

```
from models import AreaInfo
def area(request):
    area = AreaInfo.objects.get(pk=130100)
    return render(request, 'booktest/area.html', {'area': area})
```

* 定义模板area.html

```
<!DOCTYPE html>
<html>
<head>
    <title>地区</title>
</head>
<body>
当前地区：{{area.atitle}}
<hr/>
上级地区：{{area.aParent.atitle}}
<hr/>
下级地区：
<ul>
    { %for a in area.areainfo_set.all%}
    <li>{{a.atitle}}</li>
    { %endfor%}
</ul>
</body>
</html>
```

* 在booktest/urls.py中配置一个新的urlconf

```
urlpatterns = [
    url(r'^area/$', views.area, name='area')
]
```



