### 语法

```
str.split(sep = None，maxsplit = -1 )
```

### 作用

使用sep作为分隔符字符串，返回字符串中单词的列表。如果给出maxsplit，则最多完成maxsplit拆分（因此，列表将具有最多maxsplit+1元素）。如果未指定maxsplit-1，则对分割数量没有限制（进行所有可能的分割）。

### 参数

* sep: 分隔符，默认为所有的空字符，包括空格、换行\(\n\)、制表符\(\t\)等
* maxsplit:分割次数，默认分割全部

### 实例

```
>>> '1,2,3'.split(',')
['1', '2', '3']
>>> '1,2,3'.split(',', maxsplit=1)
['1', '2,3']
>>> '1,2,,3,'.split(',')
['1', '2', '', '3', '']
```


