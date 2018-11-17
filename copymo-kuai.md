在处理列表和字典时，尽管传递引用常常是最方便的方法，但是如果函数修改了传入的列表或字典，我们可能不希望这些变动影响到原来的列表和字典。这时可以采用python中提供的copy模块，copy模块中有copy\(\)和deepcopy\(\)函数。

* copy.copy\(\)函数可以用来复制列表或字典的可变值，只能进行深拷贝父对象（一级目录），子对象（二级目录）不拷贝，还是引用

```
>>> spam = ['a','b','c','d']
>>> cheese = copy.copy(spam)
>>> cheese[1] = 42
>>> cheese
['a', 42, 'c', 'd']
>>> spam
['a', 'b', 'c', 'd']


>>> spam = [1,2,3,[4,5]]
>>> cheese = copy.copy(spam)
>>> cheese[3]
[4, 5]
>>> cheese[3].append(6)
>>> spam
[1, 2, 3, [4, 5, 6]]
```

如果要复制的列表中包含了列表，这时就要使用copy.deepcopy\(\)函数

* copy.deepcopy\(\):完全的深拷贝

```
>>> a = [1,2,3,[4,5]]
>>> b = copy.deepcopy(a)
>>> a
[1, 2, 3, [4, 5]]
>>> b
[1, 2, 3, [4, 5]]

>>> b.append(1)
>>> a
[1, 2, 3, [4, 5]]
>>> b
[1, 2, 3, [4, 5], 1]

>>> b[3].append(6)
>>> a
[1, 2, 3, [4, 5]]
>>> b
[1, 2, 3, [4, 5, 6], 1]
```


