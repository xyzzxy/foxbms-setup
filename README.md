# foxBMS

foxBMS is a free, open and flexible development environment to design battery management systems. It is the first modular open source BMS development platform.

## foxBMS Project Setup
The foxBMS project consists of several repositories.

The foxConda environment. This environment provides all the tools necessary to generate the documentation, compile the code for the MCUs and flash the generated binaries on the MCUs (e.g., Python, git, GCC).

The starting point to get foxBMS is the foxBMS-setup repository (https://github.com/foxBMS/foxbms-setup), which contains the general setup files for the foxBMS project. It includes a setup script (bootstrap.py) which clones all the other needed repositories. The needed documentation will be generated automatically after these repositories have been cloned. The generated documentation is found in the directory ./build. After the bootstrap step, the top project directory (foxBMS-setup) structure looks like this:

 - foxbms-setup <dir>
  - .git <dir> *
  - build <dir>
  - documentation <dir>
  - embedded-software
   - mcu-primary <dir>
   - mcu-secondary <dir>
   - mcu-common <dir>
   - mcu-freertos <dir>
  - hal <dir>
  - tools <dir>
  - .gitignore <file> *
  - .config.yaml <file> *
  - bootstrap.py <file>
  - build.py <file>
  - CHANGELOG.md <file>
  - LICENSE.md <file>
  - README.md <file>
  - wscript <file>

* Directories and files with starting full stop are hidden in Windows in default configuration. 

There is a help available by running "python bootstrap.py -h".

## foxBMS Repositories

The foxbms-setup repositories have already been described.

foxBMS is made out of two Microcontroller Units (MCU), named primary and secondary. The C code for the primary MCU is found in the repository foxBMS-primary (https://github.com/foxBMS/mcu-primary). The C code for the secondary MCU is found in the repository foxBMS-secondary (https://github.com/foxBMS/mcu-secondary). The C code common to the primary and secondary MCU is found in the repository mcu-common (https://github.com/foxBMS/mcu-common).The Doxygen documentation is generated from these sources into ./build/primary/doxygen/html and ./build/secondary/doxygen/html respectively. The main file is in both cases index.html.

The layout and schematic files for the foxBMS hardware are found in the foxBMS-hardware repository (https://github.com/foxBMS/hardware).

The Hardware Abstraction Layer (hal) for foxBMS is found in the hal-repository (https://github.com/foxBMS/mcu-hal). The real time operating system (FreeRTOS) for foxBMS is found in the FreeRTOS-repository (https://github.com/foxBMS/mcu-freertos).

The tools needed for foxBMS are in the foxBMS-tools-repository (https://github.com/foxBMS/tools.)

The general documentation files for the foxBMS project are found in the foxBMS-documentation repository (https://github.com/foxBMS/documentation). The sphinx documentation is found in foxBMS-documentation/doc/sphinx while the Doxygen documentation configuration is found in foxBMS-documentation/doc/doxygen. The Doxygen documentation itself is found in the software sources of the primary and secondary microcontroller. The general documentation, rendered from the sphinx sources is found in ./build/sphinx/foxBMS-documentation/doc/sphinx/html. The main file is index.html

A generated version of the Sphinx documentation can be found at http://foxbms.readthedocs.io/. It explains the structure of the foxBMS hardware, how to install the foxConda environment and how to use foxConda to compile and flash the sources.

## Building the Sources
For building the software, open a shell and type "python build.py -h". All available build options will be displayed. The top build directory is ./build.

## Cleaning the ./build-Directory
For cleaning instructions open a shell and type "python clean.py -h". All available cleaning options will be displayed.