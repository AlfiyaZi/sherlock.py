Sherlock
========

|pypi| |travis-ci| |Code Climate| |Test Coverage| |Open Source Love|

Sherlock은 Python을 shell script로 바꿔주는 컴파일러입니다. **[WIP]**

.. contents::

Motivation
----------

.. figure:: http://i.imgur.com/7blJGwc.jpg
    :alt: map to buried treasure
    :width: 100%
    :align: center

    < Shell script를 작성하는 명탐정의 모습 >

Shell script는 많은 Unix-like 운영체제에서 보편적으로 사용되는 script language입니다. 이 언어는 Unix-like 운영체제에서 동작이 보장되어 많은 사람들이 Install script나 configure 스크립트에 사용됩니다. 하지만 개발된지 오래되어 다양한 `문제가 <http://teaching.idallen.com/cst8207/16w/notes/740_script_problems.html>`_ 있고 유지보수에 문제가 있습니다.

Install
-------

.. code:: sh

    $ pip install sherlock.py

Sherlock은 python버전 2.6 이상, 3.3 이상에서 동작을 보장하고 Linux 계열
운영체제와 macOS에서 동작을 보장합니다. 그 이외의 운영체제 혹은 버전에
대해서 문제가 있으면 issue를 남겨주세요.

Usage
-----

::

    usage: sherlock [-h] [-o output] [-c] [-v] [--version] [file | command]

    Python to bash trans-compiler.

    positional arguments:
      [file | command]  program read from script file

    optional arguments:
      -h, --help        show this help message and exit
      -o output         output file path
      -c, --command     program passed in as string
      -v, --verbose     program run in verbose mode
      --version         show program's version number and exit

다음은 기본적인 사용 예제입니다.

.. code:: sh

    $ sherlock target.py

위 커맨드를 사용하면 target.py를 shell script로 컴파일하고 이를 ``sh``
명령어를 이용하여 실행합니다. 실행 결과를 통해서 내가 작성하고 있는
코드가 shell script로 잘 컴파일 되는지 확인하고 디버깅할 수 있습니다.

.. code:: sh

    $ sherlock target.py -o output.sh

``-o``\ 플래그를 통해 sherlock의 결과물을 파일로 저장할 수 있습니다. 이
경우 유저가 작성한 스크립트가 실행되지 않습니다.

.. code:: sh

    $ sherlock -c "echo 'Hello World.'"

``-c``\ 플래그를 사용하면 입력한 커맨드가 즉시 bash로 컴파일 되고 이를
실행합니다.

License
-------

MIT © `Luavis Kang <https://github.com/Luavis>`__

.. |pypi| image:: https://img.shields.io/pypi/v/sherlock.py.svg?style=flat-square
   :target: https://pypi.python.org/pypi/sherlock.py
.. |travis-ci| image:: https://travis-ci.org/Luavis/sherlock.svg?branch=master
   :target: https://travis-ci.org/Luavis/sherlock
.. |Code Climate| image:: https://codeclimate.com/github/Luavis/sherlock/badges/gpa.svg
   :target: https://codeclimate.com/github/Luavis/sherlock
.. |Test Coverage| image:: https://codeclimate.com/github/Luavis/sherlock/badges/coverage.svg
   :target: https://codeclimate.com/github/Luavis/sherlock/coverage
.. |Open Source Love| image:: https://badges.frapsoft.com/os/mit/mit.svg?v=102
   :target: https://github.com/luavis/sherlock/