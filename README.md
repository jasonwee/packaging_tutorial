# Example Package

This is a simple example package. You can use
[GitHub-flavored Markdown](https://guides.github.com/features/mastering-markdown/)
to write your content.


# Setup
```
$ mkdir packaging_tutorial
$ cd packaging_tutorial/
$ python3 -m venv proj_env 
$ source proj_env/bin/activate
$ python3 -m pip install --upgrade pip
$ mkdir src
$ cd src/
$ mkdir example_package_jasonwee
$ cd example_package_jasonwee
$ touch __init__.py example.py
```

# build
```
python3 -m pip install --upgrade build
python3 -m build
$ ls dist/
total 8.0K
-rw-r--r-- 1 jason jason 2.0K Jan 19 13:31 example_package_jasonwee-0.0.1.tar.gz
-rw-r--r-- 1 jason jason 2.6K Jan 19 13:31 example_package_jasonwee-0.0.1-py3-none-any.whl
```

# upload to pypi
```
python3 -m pip install --upgrade twine
python3 -m twine upload --repository testpypi dist/*
```

# install
```
python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps example-package-jasonwee
```

# usage
```
>>> from example_package_jasonwee import example
>>> example.add_one(2)
3
```
