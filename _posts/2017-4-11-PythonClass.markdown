---
layout: post
title:  "Python技巧总结--类篇"
date:   2017-04-10 11:49:45 +0200
categories: python
published: true
---
    我们的口号是，不再把Python写成C！

最近把《Python核心编程》这本书又捡起来看了看，觉得受益匪浅，做个总结。

### 0x00 类的属性

##### __doc__

这个与函数的一样，类下的一行字符串。

```python
class myClass(object):
    'Hi! I am the __doc__!'
    pass

if __name__ == '__main__':
    print myClass.__doc__

#Hi! I am the __doc__!
```

##### __dict__

它能得到得到类内变量。

```
class myClass(object):
    'Hi! I am the __doc__!'
    a = 1
    b = 'bbb'
    def foo():pass

if __name__ == '__main__':
    print myClass.__dict__


#{'a': 1, '__module__': '__main__', 'b': 'bbb', '__dict__': <attribute '__dict__' of 'myClass' objects>, 'foo': <function foo at 0x02A888B0>, '__weakref__': <attribute '__weakref__' of 'myClass' objects>, '__doc__': 'Hi! I am the __doc__!'}
```

### 0x01 实例

##### __new__()与 __init__()