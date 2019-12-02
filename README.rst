###### Please only use this branch for Vitaefiying and Vilightifying Text. Sometimes copy and replace will be used for changing text which can break things. So assume this branch will not compile as is. Please remove this line before commiting to master or develop. This branch will squashed and deleted once finished. 



ViLight - Lightweight Vitae client (an Electron-Cash fork,based on DeLight from DeVault)
=====================================

::

  Licence: MIT Licence
  Author: The Vitae Developers
  Language: Python
  Homepage: https://vitae.cc/


Getting started
===============

*Note: If running from source, Python 3.6 or above is required to run ViLight. If your system lacks Python 3.6, 
you have other options, such as the* `binary releases <https://github.com/VitaeTeam/ViLight/releases/>`_.

ViLight is a pure python application forked from Electrum. If you want to use the Qt interface, install the Qt dependencies::

    sudo apt-get install python3-pyqt5 python3-pyqt5.qtsvg

If you downloaded the official package (tar.gz), you can run
ViLight from its root directory (called Electrum), without installing it on your
system; all the python dependencies are included in the 'packages'
directory. To run ViLight from its root directory, just do::

    ./vilight

You can also install ViLight on your system, by running this command::

    sudo apt-get install python3-setuptools
    python3 setup.py install

This will download and install the Python dependencies used by
ViLight, instead of using the 'packages' directory.

If you cloned the git repository, you need to compile extra files
before you can run ViLight. Read the next section, "Development
Version".

Hardware Wallet - Ledger Nano S
-------------------------------

ViLight natively support Ledger Nano S hardware wallet. If you plan to use
you need an additional dependency, namely btchip. To install it run this command::

    sudo pip3 install btchip-python

If you still have problems connecting to your Nano S please have a look at this
`troubleshooting <https://support.ledger.com/hc/en-us/articles/115005165269-Fix-connection-issues>`_ section on Ledger website.


Development version
===================

Check out the code from Github::

    git clone https://github.com/VitaeTeam/ViLight
    cd ViLight

Run install (this should install dependencies)::

    python3 setup.py install

or for Debian based systems ( tested on Debian v9 Stretch )::

    sudo apt update
    sudo apt install python3-dnspython python3-pyaes libsecp256k1-0 python3-protobuf python3-jsonrpclib-pelix python3-ecdsa python3-qrcode python3-pyqt5 python3-socks

Then

Compile the protobuf description file::

    sudo apt-get install protobuf-compiler
    protoc --proto_path=lib/ --python_out=lib/ lib/paymentrequest.proto

Create translations (optional)::

    sudo apt-get install python-requests gettext
    ./contrib/make_locale

Compile libsecp256k1 (optional, yet highly recommended)::

    ./contrib/make_secp

For plugin development, see the `plugin documentation <plugins/README.rst>`_.

Running unit tests::

    pip install tox
    tox

Tox will take care of building a faux installation environment, and ensure that
the mapped import paths work correctly.

Creating Binaries
=================

Linux AppImage & Source Tarball
--------------

See `contrib/build-linux/README.md <contrib/build-linux/README.md>`_.

Mac OS X / macOS
--------

See `contrib/osx/ <contrib/osx/>`_.

Windows
-------

See `contrib/build-wine/ <contrib/build-wine>`_.

Android
-------

See `android/ <android/>`_.

iOS
-------

See `ios/ <ios/>`_.
