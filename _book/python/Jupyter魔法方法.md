# Jupyter Notebook 常用魔法命令



# [magic commands](https://ipython.readthedocs.io/en/stable/interactive/magics.html#line-magics)

- 行魔法（Line magic）前缀为%
- 单元魔法(Cell magic) 前缀为%%



### %lsmagic 打印当前可以用的魔法命令

当我们想使用一个魔法命令，而不知怎么拼写函数名时，可以使用%lsmagic来查询；

```
%lsmagic
```

### 魔法命令+？显示魔法命令的说明 Docstring

```
%timeit?
```

### %timeit %time

为代码执行计时

```
import time
```

```
%timeit time.sleep(1)
```

```
# 1 s ± 143 µs per loop (mean ± std. dev. of 7 runs, 1 loop each)
```

```
%%timeit 
time.sleep(1)
time.sleep(1)
```

```
%%time
start_time = time.time()
time.sleep(1)
end_time = time.time()
time_length = end_time-start_time
print('time: '+ str(time_length))

```

### %%writefile

后面紧接着一个file_name.py,表示在jupyter notebook里面创建一个py文件，后面cell里面的内容为py文件内容

```
%%writefile test.py
for i in range(3):
    print(i)
```

```
%%writefile -a test.py
for i in range(4):
    print(i)
```



### %load 加载一个文件里面的内容

```
for i in range(4):
    print(i)
```

### %run

后面紧接着一个相对地址的file_name.py，表示运行一个py文件

```
%run test.py
```

### %pwd 查找当前目录

```
%pwd
```

```
# 'C:\\Users\\hfjy'
```

### %cd 更改当前目录

```
%cd ../
```

```
%cd hfjy
```

### %%markdown

Render the cell as Markdown text block

```
%%markdown
# 哈
## 哈哈
### 哈哈哈
```

### %whos 查看当前变量,类型，信息

```
%whos

Variable      Type      Data/Info
---------------------------------
end_time      float     1564487790.1758876
i             int       3
np            module    <module 'numpy' from 'e:\<...>ges\\numpy\\__init__.py'>
plt           module    <module 'matplotlib.pyplo<...>\\matplotlib\\pyplot.py'>
start_time    float     1564487789.1758306
time          module    <module 'time' (built-in)>
time_length   float     1.0000569820404053
```

### %reset 清除变量

```
%reset 

Once deleted, variables cannot be recovered. Proceed (y/[n])? y
```

