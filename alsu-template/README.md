# ALS-U EPICS IOC template

## IOC Dependency

* EPICS base (Channel Access)
* Various Modules (Disable by default)
	* Please look at `configure/RELEASE` and `App/src/Makefile`

## Requirements

* `APPNAME`: any name can be, it is sometime called as a repository name.
* `IOCNAME`: IOCNAME, it shall not contain `ioc` string

## How To

Here we use `APPNAME` as `alsu-ioc`, and `IOCNAME` as `example`.

```
$ git clone git@github.com:jeonghanlee/epics-ioc-template.git
$ mkdir -p alsu-ioc
$ cd alsu-ioc

alsu-ioc$ export EPICS_MBA_TEMPLATE_TOP=${PWD}/../epics-ioc-template/alsu-template
alsu-ioc$ ls $EPICS_MBA_TEMPLATE_TOP
alsu-ioc$ makeBaseApp.pl -t ioc alsu-ioc
alsu-ioc$ makeBaseApp.pl -i -t ioc -p alsu-ioc example
alsu-ioc$ echo "EPICS_BASE=/home/jeonglee/epics/1.1.0/debian-12/7.0.7/base" > configure/RELEASE.local
alsu-ioc$ make
alsu-ioc$ ./bin/linux-x86_64/alsu-ioc 
```
