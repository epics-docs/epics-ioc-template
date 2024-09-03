# EPICS Base IOC template

## IOC Dependency

* EPICS base (Channel Access)

## Requirements

* `APPNAME`: any name can be, it is sometime called as a repository name.
* `IOCNAME`: IOCNAME, it shall not contain `ioc` string

## How To

Here we use `APPNAME` as `EPICSSoftIOC`, and `IOCNAME` as `example`.

```
$ git clone https://github.com/epics-docs/epics-ioc-template.git
$ mkdir -p EPICSSoftIOC
$ cd EPICSSoftIOC/

EPICSSOftIOC$ export EPICS_MBA_TEMPLATE_TOP=${PWD}/../epics-ioc-template/base-template
EPICSSoftIOC$ ls $EPICS_MBA_TEMPLATE_TOP
EPICSSoftIOC$ makeBaseApp.pl -t ioc EPICSSoftIOC
EPICSSoftIOC$ makeBaseApp.pl -i -t ioc -p EPICSSoftIOC example
EPICSSoftIOC$ echo "EPICS_BASE=/home/jeonglee/epics/1.1.0/debian-12/7.0.7/base" > configure/RELEASE.local
EPICSSoftIOC$ make
EPICSSoftIOC$ ./bin/linux-x86_64/EPICSSoftIOC 
```
