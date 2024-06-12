# EPICS Base IOC templatei

## IOC Dependency

* EPICS base (CA)

## Requirements

* Each template folder will have its requirement in its `README`
* `APPNAME`: any name can be, it is sometime called as a repository name.
* `IOCNAME`: IOCNAME, it shall not contain `ioc` string

## How To

```
$ git clone git@github.com:jeonghanlee/epics-ioc-template.git
$ mkdir -p APPNAME
$ cd APPNAME

APPNAME$ export EPICS_MBA_TEMPLATE_TOP=${PWD}/../epics-ioc-template/alsu-tempalte/
APPNAME$ makeBaseApp.pl -t ioc APPNAME
APPNAME$ makeBaseApp.pl -i -t ioc -p APPNAME test
APPNAME$ echo "EPICS_BASE=/Users/JeongLee/epics/macOS-13.5.2/7.0.7/base" > configure/RELEASE.local
APPNAME$ make
```
