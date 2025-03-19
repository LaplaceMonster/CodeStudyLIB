# Python

* **Python基础：https://liaoxuefeng.com/books/python/introduction/index.html**
* **Python科学计算（推荐）：https://docs.huihoo.com/scipy/scipy-zh-cn/index.html**

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

## OS模块

**OS模块是Python内置的与操作系统交互的功能模块，主要包括文件和目录管理，进程管理，环境变量的访问等等。非常适合于脚本程序。**

* **常用函数：https://www.runoob.com/python3/python3-os-file-methods.html**

### path属性

以下是 `os.path` 模块常用方法的总结表格：

| 方法                             | 作用                         | 示例                                                         |
| -------------------------------- | ---------------------------- | ------------------------------------------------------------ |
| `os.path.abspath(path)`          | 获取绝对路径                 | `os.path.abspath("test.txt")` → `/Users/user/test.txt`       |
| `os.path.basename(path)`         | 获取文件名                   | `os.path.basename("/usr/local/bin/test.txt")` → `test.txt`   |
| `os.path.dirname(path)`          | 获取目录名                   | `os.path.dirname("/usr/local/bin/test.txt")` → `/usr/local/bin` |
| `os.path.exists(path)`           | 判断路径是否存在             | `os.path.exists("/usr/local/bin/test.txt")`                  |
| `os.path.isfile(path)`           | 判断是否为文件               | `os.path.isfile("/usr/local/bin/test.txt")`                  |
| `os.path.isdir(path)`            | 判断是否为目录               | `os.path.isdir("/usr/local/bin/")`                           |
| `os.path.join(path, *paths)`     | 连接多个路径                 | `os.path.join("/usr", "local", "bin", "test.txt")` → `/usr/local/bin/test.txt` |
| `os.path.split(path)`            | 分割路径，返回(目录, 文件名) | `os.path.split("/usr/local/bin/test.txt")` → `('/usr/local/bin', 'test.txt')` |
| `os.path.splitext(path)`         | 分割文件名和扩展名           | `os.path.splitext("test.txt")` → `('test', '.txt')`          |
| `os.path.getsize(path)`          | 获取文件大小（字节）         | `os.path.getsize("test.txt")`                                |
| `os.path.getctime(path)`         | 获取文件创建时间             | `time.ctime(os.path.getctime("test.txt"))`                   |
| `os.path.getmtime(path)`         | 获取文件修改时间             | `time.ctime(os.path.getmtime("test.txt"))`                   |
| `os.path.getatime(path)`         | 获取文件访问时间             | `time.ctime(os.path.getatime("test.txt"))`                   |
| `os.path.normpath(path)`         | 规范化路径                   | `os.path.normpath("/usr//local/./bin/../test.txt")` → `/usr/local/test.txt` |
| `os.path.relpath(path, start)`   | 获取相对路径                 | `os.path.relpath("/usr/local/bin/test.txt", "/usr")` → `local/bin/test.txt` |
| `os.path.samefile(path1, path2)` | 判断是否指向同一文件         | `os.path.samefile("/usr/local/bin/test.txt", "/usr/local/bin/../bin/test.txt")` |

