.. detail_pre_setup:

.. _preparedevenv_main:

####################################
Prepare Your Development Environment
####################################

Minimum Requirements for EVerest
================================

Hardware that shall run a typical EVerest configuration should meet the
following requirements:

* Linux
* CPU recommendation:
  * Single core ARM 1 GHz for ISO 15118
  * resp. dual/quad core for display
* RAM: 1 GB (2 GB recommended)
* Flash: 4-8 GB eMMC or similar
* Ethernet port for cable network connection
* WiFi and Bluetooth module
* Public station: 4G/5G module?
* CAN or RS485 for power board connection
* PLC GreenPhy
* RFID

.. note::

  EVerest can also run on much lower hardware specifications, if needed.
  The reason for this is that the module configuration is very much defining
  the RAM requirements. About 128 MB flash / RAM should be seen as a minimum
  requirement.

A Word on System Environments
=============================

For a native build, EVerest requires a Linux based system. One reason for that
is for example Linux socket header files we use for networking.

To get building done on a Windows or Mac system, you can use WSL2 (Windows) or
Docker / Podman (Mac).

For Mac, see the :ref:`How-to for MAC setup <tutorial_mac_main>`.

Required Packages
=================

To get EVerest running properly, you will mainly need the following packages:

* Python (greater than 3.6)
* Jinja2
* PyYAML
* Compiler:

  * GCC 9 (lower versions could work with some tweaking but are not
    recommended)
  * Clang (starting with version 12) has been used with EVerest but is not
    officially supported.
  * See also :ref:`the FAQ entry about GNU compilers <faq_gnu_compilers>`!

Make sure you have the Python packages pip, setuptools and wheel available,
which are needed for the EVerest dependency manager:

.. code-block:: bash

  python3 -m pip install --upgrade pip setuptools wheel

.. note::

  Depending on the programming language that you will use for implementing
  custom modules, you might need additional tools for compilation and similar
  use cases. If you stumble over some trouble that is caused by EVerest -
  especially when using other languages than C++ -, drop us a line or consider
  creating a GitHub issue.

A complete list of libraries to be installed is given by the following best
practices which setup a development environment on a number of operating
systems.

Tested Environments
===================

While EVerest is designed to run on Linux-based systems, we only have tested
it on a few distributions.
Here is a list of tested environments:

Debian
------
This is the Linux distribution that is recommended for productive setups.

Tested with Debian 12.

Here is a list of required packages to get EVerest running on Debian:

.. note::

  We are currently working on containers to provide a robust setup to test and
  develop EVerest.
  Until then, you can have a look at the packages listed for the other Linux
  distributions below and manually install the required packages on your
  Debian system.

OpenSUSE
--------
Use `zypper` to get your needed libraries installed:

.. code-block:: bash

  zypper update && zypper install -y sudo shadow
  zypper install -y --type pattern devel_basis
  zypper install -y git rsync wget cmake doxygen graphviz clang-tools cppcheck boost-devel libboost_filesystem-devel libboost_log-devel libboost_program_options-devel libboost_system-devel libboost_thread-devel java-17-openjdk java-17-openjdk-devel nodejs nodejs-devel npm python3-pip gcc-c++ libopenssl-devel sqlite3-devel libpcap-dev libevent-devel libcap-devel

Fedora
------
Tested with Fedora 38, 39 and 40. Here is how to get your needed libraries with
`dnf`.

.. code-block:: bash

  sudo dnf update
  sudo dnf install make automake gcc gcc-c++ kernel-devel python3-pip python3-devel git rsync wget cmake doxygen graphviz clang-tools-extra cppcheck java-17-openjdk java-17-openjdk-devel boost-devel nodejs nodejs-devel npm openssl openssl-devel libsqlite3x-devel curl rfkill libpcap-devel libevent-devel libcap-devel

Now, it's time to continue with the
:ref:`Quick Start Guide to install EVerest <quickstartguide_main>`.

Troubleshooting
===============

Some common problems during setting up your environment are collected here.

Maven dependency
----------------
For EVerest releases older than 2023.9.0 (released October 2nd 2023),
Maven is required for EVerest to run. Should you need to run one of those
versions, make sure you install the `maven` package with the package manager
of your choice.

Java dependency
---------------
Java is not required for running the core of EVerest. However, it is required
if you want to install certificates for ISO 15118 communication as currently
the Java Keytool is used. Also the EXI (Efficient XML Interchange) part of
Josev requires Java.

Python versions with pyenv
--------------------------
If you use `pyenv` for running multiple Python version in parallel on your
system, you probably will see `cmake` not using the Python version activated
by `pyenv`.

One solution to this is to run `cmake` with the `PYTHON_EXECUTABLE` flag. See
`cmake` documentation for more information on this.
