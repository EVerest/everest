.. detail_pre_setup_ide:

.. _preparedevenv_ide_main:

#####################################
Setup EVerest With Visual Studio Code
#####################################

.. note::

  This guide shows you how to setup an EVerest development environment with
  the IDE Visual Studio Code. As the steps described here include also the
  necessity to compile EVerest as shown in the
  :ref:`Quick Start Guide <quickstartguide_main>`, you will find yourself
  already walk through that one in parallel. So, have a first look at it
  eventually, before diving in!

Prerequisites
=============

Make sure that you have **Visual Studio Code** (VSC) installed.

If not already installed, check the documentation of your operating system
about how to install programs / packages.

Extensions
==========

This tutorial uses the C/C++ extensions from Microsoft.

Make sure that you have at least the 'C/C++' (IntelliSense) extension
installed.

Source code - default includes
==============================

Follow the EVerest tutorial on
:ref:`how to prepare your system environment <preparedevenv_main>`.

Having done that, let's get the EVerest repositories cloned locally.

Let's assume that you use ``~/checkout/everest-workspace`` as workspace.

In order to setup the project with all its files in Visual Studio Code, follow
the next steps:

1. In Visual Studio Code, select **File / Open folder ...**.
2. Navigate to the location of your workspace (in our example
  **~/checkout/everest-workspace**).
3. Press the 'Open' button.
4. Visual Studio Code will parse the directories and will be able to identify
  most of the files. However, there are some includes that VSC will not be
  able to figure out. See next subsection!

Source code - default includes
==============================

In order to make VSC to identify, parse and include those files, you need
first to compile your project.

This is because some files are either generated or downloaded on the fly
during the compilation process.

Make sure that you do that as described in
:ref:`Quick Start Guide <quickstartguide_main>`.

Now that you already have done that, in order to get Visual Studio Code to
identify the missing includes, you have to manually tell IntelliSense where to
check.

In case the file explorer in VSC is not visible, press **Ctrl+Shift+E** to
make it visible.

At the top and in the root folder of your workspace, you can see a folder
called ``.vscode``.

Inside, you might see multiple files but you are interested in the file called
``c_cpp_properties.json``.

This is the file we are going to change and add the additional include paths.

Open the file in the editor.

By default, the file looks similar to this:

.. code-block:: bash

  {
    "configurations": [
      {
        "name": "Linux",
        "includePath": [
          "${workspaceFolder}/**"
        ],
        "defines": [],
        "compilerPath": "/usr/bin/clang-14",
        "cStandard": "c17",
        "cppStandard": "c++14",
        "intelliSenseMode": "linux-clang-x64",
        "configurationProvider": "ms-vscode.cmake-tools"
      }
    ],
    "version": 4
  }

As you can see, by default it will look only at the files located in the root
folder.

We will want to add at least the following locations:

* ``${workspaceFolder}/everest-core/build/**`` (this is the build directory)
* ``${workspaceFolder}/everest-framework/include/**`` (this is the EVerest
  framework)
* ``${workspaceFolder}/liblog/include/**`` (this is the liblog include)

Make sure to adapt the paths above if your project looks a bit different
(use ".."" to go above the workspace folder if needed).

Now, during the build process, EVerest downloads certain dependencies on the
fly and places them in the cache.
You have already defined something like this for the build process
(``export CPM_SOURCE_CACHE=$HOME/.cache/CPM``).

We are interested in files that are located there as part of **nlohmann_json**
and **nlohmann_json_schema_validator**. The problem is that the path might be
different (this is a cache so the path will contain a hash ID).

In my case the paths look like this:

* ``${workspaceFolder}/../../.cache/CPM/nlohmann_json_schema_validator/648e7cc933b58ff9d20a5288445b6172aa5fc67f/nlohmann_json_schema_validator/src/**``
* ``${workspaceFolder}/../../.cache/CPM/nlohmann_json/b3708972f6694fe462e4112e47aa04f10d2390b4/nlohmann_json/include/**``

The hash IDs (648e7cc933b58ff9d20a5288445b6172aa5fc67f and
b3708972f6694fe462e4112e47aa04f10d2390b4) might be different in your case.
Just check the paths in your system with a file explorer.

Before we are finished, just go ahead and change **cppStandard** to **c++17**,
too. Right now, the file called **c_cpp_properties.json** should look very
similar to this:

.. code-block:: bash

  {
    "configurations": [
      {
        "name": "Linux",
        "includePath": [
          "${workspaceFolder}/**",
          "${workspaceFolder}/everest-core/build/**",
          "${workspaceFolder}/liblog/include/**",
          "${workspaceFolder}/everest-framework/include/**",
          "${workspaceFolder}/../../.cache/CPM/nlohmann_json_schema_validator/648e7cc933b58ff9d20a5288445b6172aa5fc67f/nlohmann_json_schema_validator/src/**",
          "${workspaceFolder}/../../.cache/CPM/nlohmann_json/b3708972f6694fe462e4112e47aa04f10d2390b4/nlohmann_json/include/**"
        ],
        "defines": [],
        "compilerPath": "/usr/bin/clang-14",
        "cStandard": "c17",
        "cppStandard": "c++17",
        "intelliSenseMode": "linux-clang-x64",
        "configurationProvider": "ms-vscode.cmake-tools"
      }
    ],
    "version": 4
  }

In case you are using additional packages from the cache, go ahead and add
them as we added **nlohmann_json** and **nlohmann_json_schema_validator**.

You should now have IntelliSense being able to parse the entire project and
you should be able to quickly navigate your project.
