# Development Environment Setup

- [Development Environment Setup](#development-environment-setup)
  - [clang and clang++](#clang-and-clang)
    - [install clang-11 (with lldb and lld):](#install-clang-11-with-lldb-and-lld)
    - [compile single cpp file:](#compile-single-cpp-file)
    - [build a project containing multiple libraries/modules:](#build-a-project-containing-multiple-librariesmodules)
  - [java](#java)
    - [install openjdk](#install-openjdk)
    - [switch jdk version](#switch-jdk-version)
  - [python](#python)
    - [install python](#install-python)
    - [manage virtual env](#manage-virtual-env)

## clang and clang++

### install clang-11 (with lldb and lld):

```bash
# To retrieve the archive signature:
wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add -
# Fingerprint: 6084 F3CF 814B 57C1 CF12 EFD5 15CF 4D18 AF4F 7421

# To install just clang, lld and lldb (11 release):
apt-get install clang-11 lldb-11 lld-11
```

ref: https://apt.llvm.org/

### compile single cpp file:

```bash
clang++ -Wall -std=c++17 test.cc -o test
```

### build a project containing multiple libraries/modules:

CMake is recommended for building: [My CMake Notes](https://github.com/prowiki/cpp-bootstrap/tree/main/cmake-bootstrap)


## java

### install openjdk

For Ubuntu, it's relatively simple: `sudo apt install openjdk-<version>-jdk`, e.g. `sudo apt install openjdk-11-jdk`.

For other linux distributions, refer [How to download and install prebuilt OpenJDK packages](https://openjdk.java.net/install/).

### switch jdk version

On Ubuntu, we can install multiple JDK versions using the command above and switch the default JDK version easily.

- To list all availbale JDKs: `update-java-alternatives --list`;
- To switch JDK: e.g. `sudo update-java-alternatives --set /usr/lib/jvm/java-1.11.0-openjdk-amd64`.


## python

### install python

Though we have default python with linux installed, it's recommend to install `conda`(`miniconda`) which contains some commonly used pyton packages and can help manage separate python environments.

See [Miniconda](https://docs.conda.io/en/latest/miniconda.html) for how to install.

### manage virtual env

By default, you will be using `base` python virtual environment after you install miniconda.

- To create a new virtual env: e.g. `conda create --name py36 python=3.6`;
- To activate a virtual env: e.g. `source activate py36`.

For more conda usage, see [Conda Cheatsheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf).
