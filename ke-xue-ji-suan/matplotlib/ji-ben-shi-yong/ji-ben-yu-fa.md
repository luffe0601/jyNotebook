## 基础应用 {#基础应用}

使用`import`导入模块`matplotlib.pyplot`，并简写成`plt`使用`import`导入模块`numpy`，并简写成`np`

```
import matplotlib.pyplot as plt
import numpy as np
```

使用`np.linspace`定义x：范围是\(-1,1\);个数是50. 仿真一维数据组\(`x`,`y`\)表示曲线1.

```
x = np.linspace(-1, 1, 50)
y = 2*x + 1
```

使用`plt.figure`定义一个图像窗口. 使用`plt.plot`画\(`x`,`y`\)曲线. 使用`plt.show`显示图像.

```
plt.figure()
plt.plot(x, y)
plt.show()
```

![](/assets/1.8.3.2.1-1.png)

