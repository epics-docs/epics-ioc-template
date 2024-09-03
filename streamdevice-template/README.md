# EPICS IOC template with StreamDevice

## IOC Dependency

* EPICS base (Channel Access)
* Asyn
* StreamDevice 

## Requirements

* Each template folder will have its requirement in its `README`
* `APPNAME`: any name can be, it is sometime called as a repository name.
* `IOCNAME`: IOCNAME, it shall not contain `ioc` string

## How To

```
$ git clone https://github.com/epics-docs/epics-ioc-template.git
$ mkdir -p StreamDeviceIOC
$ cd StreamDeviceIOC

StreamDeviceIOC$ export EPICS_MBA_TEMPLATE_TOP=${PWD}/../epics-ioc-template/streamdevice-template/
StreamDeviceIOC$ ls $EPICS_MBA_TEMPLATE_TOP
StreamDeviceIOC$ makeBaseApp.pl -t ioc StreamDeviceIOC
StreamDeviceIOC$ makeBaseApp.pl -i -t ioc -p StreamDeviceIOC example
StreamDeviceIOC$ echo "EPICS_BASE=/Users/JeongLee/epics/macOS-13.5.2/7.0.7/base" > configure/RELEASE.local
StreamDeviceIOC$ echo "ASYN=${EPICS_BASE}/../modules/asyn"                      >> configure/RELEASE.local
StreamDeviceIOC$ echo "STREAM=${EPICS_BASE}/../modules/StreamDevice"            >> configure/RELEASE.local
StreamDeviceIOC$ echo "CHECK_RELEASE=NO"                                        > configure/CONFIG_SITE.local
StreamDeviceIOC$ make
```
