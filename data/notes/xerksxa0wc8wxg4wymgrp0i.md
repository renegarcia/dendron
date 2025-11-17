

# How to specify cli scripts in a pyproject file

## Using poetry

If you use poetry, assuming your project is organized as in this example 

```toml
[tool.poetry]
name = "packagename"
version = "0.1.0"
description = ""
authors = ["finswimmer <finswimmer@example.org>"]

[tool.poetry.scripts]
cli-script = "packagename.cli:main"

[tool.poetry.dependencies]
python = "^3.6"

[tool.poetry.dev-dependencies]
pytest = "^5.2"

[build-system]
requires = ["poetry>=1.0"]
build-backend = "poetry.masonry.api"
```
Simply call 

```sh
poetry install --only-root
```

Where your project should be organized as 

```
packagename
├── packagename
│   ├── __init__.py
│   └── cli.py
├── tests
│   ├── __init__.py
│   └── test_packagename.py
└── pyproject.toml
```

And the content of the script should resemble this:

```python
#!/usr/bin/env python

def main():
  print("Hello world")

if __name__ == '__main__':
  main()
```

---

**Source**: [https://stackoverflow.com/questions/62572961/how-to-organize-a-python-project-with-poetry-for-a-command-line-script](https://stackoverflow.com/questions/62572961/how-to-organize-a-python-project-with-poetry-for-a-command-line-script)

## With setup tools

If your project is simple, for example like this,
```
yourprojectdir/
    setup.py
    scripts/
        myscript.sh
```

you may only need to create or append to your `setup.py` the following:

```python
from setuptools import setup
# you may need setuptools instead of distutils

setup(
    scripts = [
        'scripts/myscript.sh'
    ]
)
```

Then in the shell type

```sh
python setup.py install
```

---

**Source:** [https://stackoverflow.com/questions/874521/python-install-script-to-system](https://stackoverflow.com/questions/874521/python-install-script-to-system)

# References

* [Specifying Command Line Scripts In Pyproject Toml](https://stackoverflow.com/questions/63326840/specifying-command-line-scripts-in-pyproject-toml).

* [How To Organize A Python Project With Poetry For A Command Line Script](https://stackoverflow.com/questions/62572961/how-to-organize-a-python-project-with-poetry-for-a-command-line-script).

* [Python install script to system](https://stackoverflow.com/questions/874521/python-install-script-to-system).

* [Poetry Cheatsheet](https://www.yippeecode.com/topics/python-poetry-cheat-sheet/#:~:text=Installing%20all%20dependencies%2C%20but%20not%20the%20project%20itself.,install%20all%20dependencies%20excluding%20the%20ones%20for%20Development.)