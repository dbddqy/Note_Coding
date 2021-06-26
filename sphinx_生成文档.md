# sphinx 生成文档

先安装： 

```
 pip3 install -U Sphinx
```

别的各种软件包：

```
 pip3 install sphinx-autobuild
 pip3 install sphinx_rtd_theme
 pip3 install recommonmark
 pip3 install sphinx_markdown_tables
```

先创建doc目录，cd进去，然后：

 ```
 sphinx-quickstart
 ```

生成了一堆东西，进去找到 source/conf.py，修改：

 ```python
 # ...
 import os
 import sys
 sys.path.insert(0, os.path.abspath('../../visual-kinematics'))#指向代码目录
 # ...
 extensions = ['sphinx.ext.autodoc']
 html_theme = 'sphinx_rtd_theme'
 # ...
 ```

切换到doc目录下，执行

```
sphinx-apidoc -o source ../visual-kinematics/
make clean
make html
```

生成结果在 build/html/index.html

