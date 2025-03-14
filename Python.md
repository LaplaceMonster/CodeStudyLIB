# Python

* Python基础：https://liaoxuefeng.com/books/python/introduction/index.html
* Python科学计算（推荐）：https://docs.huihoo.com/scipy/scipy-zh-cn/index.html
* 莫烦Python（实用案例）：https://mofanpy.com

## 修改pip的源地址（加速安装第三方包）

```
#清华大学镜像站
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```



## 迭代器（Iterator）VS可迭代对象（Iterable）

### **迭代器 vs 可迭代对象**

| **类别**                   | **存储数据**         | **能否多次遍历** | **是否实现 `__next__()`** |
| -------------------------- | -------------------- | ---------------- | ------------------------- |
| **可迭代对象（Iterable）** | ✅ 是的，存储所有元素 | ✅ 可以多次遍历   | ❌ 不能直接 `next()`       |
| **迭代器（Iterator）**     | ❌ 不是，按需生成元素 | ❌ 只能遍历一次   | ✅ 需要 `next()` 获取      |

**总结：**

* 迭代器：本质上就是一个表达式，对象内并没有存储具体的元素，所以在遍历一次后记录就是一个元素的信息，所以无法再次遍历，而且需要使用next去获取下一个元素。

* 可迭代对象：内部存储了具体的元素，所以可以多次遍历。

