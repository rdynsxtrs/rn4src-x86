# rnx4src-x86

This repository contains the source code of updates packages for the old
ReadyNAS systems running RAIDiator 4.x (ideally 4.2.31).

## Directory structure

The repos is organized into different directories. Each directory represents
a package and holds the files needed to build that package.
To save on disk space only the `debian` directory with the build information
as well as the original source archive are stored in the rpository.
Additionally a README.md file in the directory of a package may give hints
on special prerequisites needed to build the package.

## Prerequisites

To make use of this repo a working installation of Debian 4.0 "Etch" is
needed. This can be achieved by installing into a VirtualBox or 
similar environment using the installers from http:archive.debian.org.
Debootstrapping is discouraged since that will result in using a newer
kernel than the one installed on the ReadyNAS which may break things - 
especially for gcc and libc6!

In addition make sure to have
* at least kernel 2.6.26 installed
* the following packages present:
  * build-essential
  * devscripts

## Building packages

To build a package 

* change to the package's directory
* unpack the original source archive to someplace **outside** the repository
* **copy** the `debian` directory into the folder with the unpacked source
* change to the directory with the unpacked source
* [optional] make your changes to the files in the `debian` directory
* run `debuild -sa`
