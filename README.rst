LabelImg
========
此版本为默认打包汉化版本 修复了一些小bug
========

.. image:: https://img.shields.io/pypi/v/labelimg.svg
        :target: https://pypi.python.org/pypi/labelimg

.. image:: https://img.shields.io/github/workflow/status/tzutalin/labelImg/Package?style=for-the-badge   :alt: GitHub Workflow Status

.. image:: https://img.shields.io/badge/lang-en-blue.svg
        :target: https://github.com/tzutalin/labelImg

.. image:: https://img.shields.io/badge/lang-zh-green.svg
        :target: https://github.com/tzutalin/labelImg/blob/master/readme/README.zh.rst

.. image:: https://img.shields.io/badge/lang-jp-green.svg
        :target: https://github.com/tzutalin/labelImg/blob/master/readme/README.jp.rst

.. image:: /resources/icons/app.png
    :width: 200px
    :align: center

LabelImg 是图像标注工具，它是用python 和 QT 写成的.

支持的存储格式包括PASCAL VOC format, YOLO, createML.

.. image:: https://raw.githubusercontent.com/tzutalin/labelImg/master/demo/demo3.jpg
     :alt: Demo Image

.. image:: https://raw.githubusercontent.com/tzutalin/labelImg/master/demo/demo.jpg
     :alt: Demo Image

`展示影片 <https://youtu.be/p0nR2YsCY_U>`__

安装
------------------


通过源码编译
~~~~~~~~~~~~~~~~~

Linux/Ubuntu/Mac 需要 Python 和 `PyQt <https://pypi.org/project/PyQt5/>`__

Ubuntu Linux
^^^^^^^^^^^^

Python 3 + Qt5

.. code:: shell

    sudo apt-get install pyqt5-dev-tools
    sudo pip3 install -r requirements/requirements-linux-python3.txt
    make qt5py3
    python3 labelImg.py
    python3 labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

macOS
^^^^^

Python 3 + Qt5

.. code:: shell

    brew install qt  # Install qt-5.x.x by Homebrew
    brew install libxml2

    or using pip

    pip3 install pyqt5 lxml # Install qt and lxml by pip

    make qt5py3
    python3 labelImg.py
    python3 labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]


Python 3 Virtualenv (推荐)

Virtualenv 可以避免版本和依赖问题

.. code:: shell

    brew install python3
    pip3 install pipenv
    pipenv run pip install pyqt5==5.15.2 lxml
    pipenv run make qt5py3
    pipenv run python3 labelImg.py
    [Optional] rm -rf build dist; python setup.py py2app -A;mv "dist/labelImg.app" /Applications


Windows
^^^^^^^

安装 `Python <https://www.python.org/downloads/windows/>`__,
`PyQt5 <https://www.riverbankcomputing.com/software/pyqt/download5>`__
和 `install lxml <http://lxml.de/installation.html>`__.

安装并到 `labelImg <#labelimg>`__ 目录

.. code:: shell

    pyrcc4 -o libs/resources.py resources.qrc
    For pyqt5, pyrcc5 -o libs/resources.py resources.qrc

    python labelImg.py
    python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

Windows + Anaconda
^^^^^^^^^^^^^^^^^^

下载并安装 `Anaconda <https://www.anaconda.com/download/#download>`__ (Python 3+)

打开 Anaconda Prompt 然后到 `labelImg <#labelimg>`__ 目录

.. code:: shell

    conda install pyqt=5
    conda install -c anaconda lxml
    pyrcc5 -o libs/resources.py resources.qrc
    python labelImg.py
    python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

Get from PyPI but only python3.0 or above
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: shell

    pip3 install labelImg
    labelImg
    labelImg [IMAGE_PATH] [PRE-DEFINED CLASS FILE]


Use Docker
~~~~~~~~~~~~~~~~~
.. code:: shell

    docker run -it \
    --user $(id -u) \
    -e DISPLAY=unix$DISPLAY \
    --workdir=$(pwd) \
    --volume="/home/$USER:/home/$USER" \
    --volume="/etc/group:/etc/group:ro" \
    --volume="/etc/passwd:/etc/passwd:ro" \
    --volume="/etc/shadow:/etc/shadow:ro" \
    --volume="/etc/sudoers.d:/etc/sudoers.d:ro" \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    tzutalin/py2qt4

    make qt4py2;./labelImg.py

`你可以参考影片  <https://youtu.be/nw1GexJzbCI>`__


使用方法
-----

你可以先创建标签
~~~~~~~~~~~~~~~~~~~~~~~~~~

修改这个档案
`data/predefined\_classes.txt <https://github.com/tzutalin/labelImg/blob/master/data/predefined_classes.txt>`__

快捷键
~~~~~~~

+--------------------+--------------------------------------------+
| Ctrl + u           | 从每个目录读取所有图片                     |
+--------------------+--------------------------------------------+
| Ctrl + r           | 改变标识结果的存档目录                     |
+--------------------+--------------------------------------------+
| Ctrl + s           | 存档                                       |
+--------------------+--------------------------------------------+
| Ctrl + d           | 复制目前的标签和物件的区块                 |
+--------------------+--------------------------------------------+
| Ctrl + Shift + d   | 删除目前图片                               |
+--------------------+--------------------------------------------+
| Space              | 标识目前照片已经处理过                     |
+--------------------+--------------------------------------------+
| w                  | 产生新的物件区块                           |
+--------------------+--------------------------------------------+
| d                  | 下张图片                                   |
+--------------------+--------------------------------------------+
| a                  | 上张图片                                   |
+--------------------+--------------------------------------------+
| del                | 删除所选的物体区块                         |
+--------------------+--------------------------------------------+
| Ctrl++             | 放大图片                                   |
+--------------------+--------------------------------------------+
| Ctrl--             | 缩小图片                                   |
+--------------------+--------------------------------------------+
| ↑→↓←               | 移动所选的物体区块                         |
+--------------------+--------------------------------------------+

如何贡献
~~~~~~~~~~~~~~~~~

欢迎上传源码直接贡献
