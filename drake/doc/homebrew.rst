*********************************************
OS X (using Homebrew -- recommended for OS X)
*********************************************

We assume that you have already installed:

* `Xcode <https://developer.apple.com/xcode/download/>`_ and the Command Line Tools (``xcode-select --install``)
* `XQuartz <http://www.xquartz.org/releases/>`_
* `Java SE Development Kit <http://www.oracle.com/technetwork/java/javase/downloads/>`_
* `Homebrew <http://brew.sh/>`_

Install the prerequisites::

    brew tap homebrew/python
    brew tap homebrew/science
    brew update
    brew upgrade
    brew install autoconf automake ccache cmake doxygen gcc glib graphviz gtk+ \
      jpeg libpng libtool mpfr mpich2 numpy python qt swig valgrind wget
    brew install vtk5 --with-qt
    pip install -U cpplint Sphinx

Add the line::

    export PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/opt/X11/lib/pkgconfig

to your ``.bash_profile`` or ``.bashrc``.

Download the external dependencies::

    cd drake-distro
    make options  # use the GUI to choose which externals you want, then press 'c' to configure, then 'g' to generate makefiles and exit
    make download-all

When you are done with these platform-specific steps, return to :doc:`from_source` to complete and test your installation.
