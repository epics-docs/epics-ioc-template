# EPICS Base IOC template

## IOC Dependency

* EPICS base (Channel Access)
* Sequencer `SNCSEQ`

## Requirements

* `APPNAME`: any name can be, it is sometime called as a repository name.
* `IOCNAME`: IOCNAME, it shall not contain `ioc` string

## How To

Here we use `APPNAME` as `seq-ioc`, and `IOCNAME` as `example`.

```
$ git clone https://github.com/epics-docs/epics-ioc-template.git
$ mkdir seq-ioc
$ cd seq-ioc/

$ mkdir seq-ioc
$ cd seq-ioc


seq-ioc$ export EPICS_MBA_TEMPLATE_TOP=${PWD}/../epics-ioc-template/sncseq-template/
seq-ioc$ ls $EPICS_MBA_TEMPLATE_TOP
seq-ioc$ makeBaseApp.pl -t ioc seq-ioc
seq-ioc$ makeBaseApp.pl -i -t ioc -p seq-ioc example
seq-ioc$ echo "EPICS_BASE=/home/jeonglee/epics/1.1.0/debian-12/7.0.7/base" > configure/RELEASE.local
seq-ioc$ echo "CHECK_RELEASE=NO" > configure/CONFIG_SITE.local
seq-ioc$ make
seq-ioc$ cd iocBoot/iocexample/
iocexample$ chmod +x st.cmd
iocexample$ ./st.cmd
```
