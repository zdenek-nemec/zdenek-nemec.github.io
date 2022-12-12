# Python Installation

* [Python.org](https://www.python.org/)
* Python 2 (`python`) is no longer supported, use Python 3 unless porting legacy applications.
* Always check which Python version is supported on your operating system.
* When downloading a new major version, avoid `X.Y.0` and wait for it to be patched

---

## Standard Installation on Windows

1. Go to [Python.org](https://www.python.org/)
2. Download preferred version of Python installer for Windows and start it
3. Decide whether to install for all users (`c:\Program Files`) or for current user only (`AppData`)

Notes

* Consider avoiding spaces ` ` in the path to Python install directory, use following or something similar
  * `c:\Python-3.10.8-64`
  * `c:\Programs\Python\Python-3.10.8-64`

---

## Standard Installation on Linux

Example for Python 3.7.

1. Update APT

    ```text
    sudo apt-get update
    ```

2. Install Python 3.7

    ```text
    sudo apt-get install python3.7
    ```

---

## Installation on Linux without Root

If necessary, following approach can be used for deploying Python 2 as well.

1. Make sure the C compiler is present. If not, it must be installed (root needed).

   ```text
   sudo apt-get install gcc
   ```

2. Download preferred Python version

    * Use `wget`

        ```text
        wget https://www.python.org/ftp/python/3.7.8/Python-3.7.8.tgz
        ```

    * Or download it from the [official website](https://www.python.org/) and deliver by other means

3. Decompress Python files in desired directory

    ```text
    tar -zxf Python-3.7.8.tgz
    ```

4. You may need to disable application specific profile (on the Intermediate server prevent profile setup `med_set_environment.sh`) and reload the session in order to have a clean environment

5. Go into directory with Python files and set up the configuration

    ```text
    ./configure --prefix=/appl/mediation/data01/SOFTWARE/Python-3.7.8
    ```

6. Install

    ```text
    make && make install
    ```

7. Enable application profile (`med_set_environment.sh`) if it was disabled for the installation purposes

8. Setup following variables permanently of per session whenever you need to use the Python

    ```text
    PYTHONHOME=/appl/mediation/data01/SOFTWARE/Python-3.7.8
    PYTHONPATH=/appl/mediation/data01/SOFTWARE/Python-3.7.8/lib
    ```

9. Update `PATH` variable if you want to use this Python version as default

---

## Python 2.7 with PIP, No Internet and No Root

Python 2 is no longer supported. If it is necessary to install it due to legacy code, be sure to select module versions from around its release date. For Python 2.7.18 it is 20th of April 2020.

Sources

* [Install Python Packages via Pip without an Internet Connection](https://thilinamad.medium.com/install-python-packages-via-pip-without-an-internet-connection-b3dee83b4c2d)
* [zlib module missing](https://stackoverflow.com/questions/3905615/zlib-module-missing)
* [Offline installation of dependant python modules without PIP](https://stackoverflow.com/questions/56021133/offline-installation-of-dependant-python-modules-without-pip)
* [ImportError: No module named \_ssl](https://stackoverflow.com/questions/5128845/importerror-no-module-named-ssl)

Requirements

* gcc - Compilation
* zlib or zlib1g-dev - For setuptools
* openssl-devel or libssl-dev - For paramiko

```bash
sudo apt-get install gcc
sudo apt-get install zlib1g-dev
sudo apt-get install openssl-devel
```

1. Download [Python 2.7.18](https://www.python.org/downloads/release/python-2718/) or another preferred version from [www.python.org](https://www.python.org)

2. Decompress the python files, configure installation and compile

    ```bash
    cd /appl/blackmed/netmax/Python-2.7.18
    ./configure --prefix=/appl/blackmed/netmax/Python-2.7.18
    make && make install
    ```

    Installation will silently fail for some modules. Resolve the dependencies before configuration/compilation if you need them.

    ```text
    Python build finished, but the necessary bits to build these modules were not found:
    _bsddb             _curses            _curses_panel
    _sqlite3           _tkinter           bsddb185
    bz2                dbm                dl
    gdbm               imageop            nis
    readline           sunaudiodev
    To find the necessary bits, look in setup.py in detect_modules() for the module's name.
    ```

3. Setup the environment (consider updating `.profile`)

    ```bash
    PYTHONHOME=/appl/blackmed/netmax/Python-2.7.18
    PYTHONPATH=/appl/blackmed/netmax/Python-2.7.18/lib
    PATH=/appl/blackmed/netmax/Python-2.7.18/bin:${PATH}
    export PYTHONHOME
    export PYTHONPATH
    export PATH
    ```

4. Download TGZ version of setuptools and pip from [pypi.org](https://pypi.org/) and install them

    ```bash
    cd setuptools-46.2.0
    python setup.py install
    cd ..
    cd pip-20.1
    python setup.py install
    cd ..
    ```

5. Other packages can be installed via PIP through WHL, there might be exceptions like bcrypt

    ```bash
    pip install --no-index --find-link=/appl/blackmed/netmax/python-wheels cffi
    pip install --no-index --find-link=/appl/blackmed/netmax/python-wheels six

    cd bcrypt-3.1.4
    python setup.py install
    cd ..

    pip install --no-index --find-link=/appl/blackmed/netmax/python-wheels paramiko
    ```
