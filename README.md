# Roastero
A coffee roasting application to control the Fresh Roast SR700.

## Setup a Development Environment
### Mac

    git clone git@yeso.201.io:roastero/roastero.git
    cd Roastero
    brew install Python3
    pip install virtualenv
    virtualenv env -p Python3
    source env/bin/activate
    pip install matplotlib pyserial
    brew install PyQt5 qt5
    cp -r /usr/local/Cellar/pyqt5/5.4/lib/python3.4/site-packages/PyQt5 env/lib/python3.4/site-packages/
    cp /usr/local/lib/python3.4/site-packages/sip* env/lib/python3.4/site-packages/

#### Patching PySerial for Mac
While developing the application we found a bug in the PySerial library.
We tried to contact the developers but with no luck as of 2-1-15(v2.7).
For this reason you will have to manually patch Pyserial. It's not
that hard though. It's simply copying a file over.

    cp PySerial\ Patched\ Files/list_ports_osx.py env/lib/python3.4/site-packages/serial/tools/list_ports_osx.py

This should fix PySerial for now.

### Windows
The best way to create a development environment on windows is to use a package manager like chocolatey. This will simplify the whole process of finding packages and downloading/installing them. To install choco I'd recomend you take a look at their website [here](https://chocolatey.org/). On you have choco all setup you can run the following commands.

    choco install python pip
    pip install python-dateutil pyserial

In order to install matplotlib on Windows you will have to download and install it manually. You can grab an installation package from [here](http://matplotlib.org/downloads.html).

A requirement for matplotlib is also numpy which can be installed with package from [here](http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy). You can install this newly downloaded WHL file by doing the following command.

    pip install PackageName.whl

The same goes for pyqt5. You will have to download it from [here](http://www.riverbankcomputing.com/software/pyqt/download5) and install it yourself.

### Linux
