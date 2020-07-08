# python 打包pkg

需要一个setup.py文件，例如：

```python
import setuptools

with open("README.md", "r") as fh:
    long_description = fh.read()

setuptools.setup(
    name="visual_kinematics",
    version="0.0.5",
    author="Yue QI",
    author_email="dbddqy@gmail.com",
    description="A package for calculating robot kinematics and visualizing trajectory in just a few lines of code",
    long_description=long_description,
    long_description_content_type="text/markdown",
    url="https://github.com/dbddqy/visual_kinematics",
    packages=setuptools.find_packages(),
    keywords = ['robotics', ' kinematics', 'inverse kinematics', 'trajectory planning', 'visualization'],
    install_requires=[
        'numpy',
        'scipy',
        'matplotlib',
    ],
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires='>=3.5',
)
```

需要安装setuptools和wheel：

```
python3 -m pip install --user --upgrade setuptools wheel
```

然后跑这个setup . py：

```
python3 setup.py sdist bdist_wheel
```

要上传Pypi的话，需要安装twine：

```
python3 -m pip install --user --upgrade twine
```

上传：

```
twine upload dist/*
```
