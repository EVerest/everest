.. detail_pre_setup:

.. _preparedevenv_main:

####################################
Prepare Your Development Environment
####################################

.. note::

  This page is about setting up your system environment in the sense of
  preparing your operating system and some required dependencies.

  For a short example how to setup an IDE to work on EVerest development,
  see :ref:`the EVerest IDE setup page <preparedevenv_ide_main>`.

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

Ubuntu
------

.. warning::

  Ubuntu 20.04 is not supported anymore. Please use Ubuntu 22.04 or newer.

Tested with Ubuntu 22.04.

Use `apt` to get your needed libraries installed:

.. code-block:: bash

  sudo apt update
  sudo apt install -y python3-pip git rsync wget cmake doxygen graphviz build-essential clang-tidy cppcheck openjdk-17-jdk npm docker docker-compose libboost-all-dev nodejs libssl-dev libsqlite3-dev clang-format curl rfkill libpcap-dev libevent-dev pkg-config libcap-dev

Please make sure to have `nodejs` installed with minimum version 10.20 for `node_api` version 6+. For updating to a supported version, please follow the install procedure here: `<https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions>`_.

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
