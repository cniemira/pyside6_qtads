# pyside6_qtads
PySide6 wrapper for Qt Advanced Docking System

This module is currently little more than a proof-of-concept.

Uses [cmake-build-extension](https://github.com/diegoferigo/cmake-build-extension) to evoke [Shiboken](https://doc.qt.io/qtforpython/shiboken6/) to build a Python wrapper for [Qt-Advanced-Docking-System](https://github.com/githubuser0xFFFF/Qt-Advanced-Docking-System) for [Qt6](https://www.qt.io/).

PySide6 and Shiboken6 can be installed from pypi.org, but shiboken_generator cannot:

```sh
pip install --index-url=http://download.qt.io/official_releases/QtForPython/ --trusted-host download.qt.io shiboken6 pyside6 shiboken6_generator
```

This module is then build like so:

```sh
python setup.py {bdist_wheel|install} build_ext -D"CMAKE_PREFIX_PATH:PATH=/path/to/Qt/6.x.x/..."
```

or

```sh
pip {wheel|install} --global-option="build_ext" --global-option="-DCMAKE_PREFIX_PATH:PATH=/path/to/Qt/6.x.x/..." .
```

Any CMake flags needed to compile the Qt extension will need to be provided. This is likely at least CMAKE_PREFIX_PATH, as shown above.
