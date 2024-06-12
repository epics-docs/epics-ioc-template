# epics-ioc-template


## Target Audiance

## Goal

* This repository collects multiple ***ioc*** application templates to provide a clear guideline.

## Requirements


* Each template folder will have its requirement in its `README`
* `APPNAME`: any name can be, it is sometime called as a repository name.
* `IOCNAME`: IOCNAME, it shall not contain `ioc` string

## How To

```
$ git clone git@github.com:jeonghanlee/epics-ioc-template.git
$ mkdir -p APPNAME
$ cd APPNAME

APPNAME$ export EPICS_MBA_TEMPLATE_TOP=${PWD}/../epics-ioc-template/alsu-template/
APPNAME$ makeBaseApp.pl -t ioc APPNAME
APPNAME$ makeBaseApp.pl -i -t ioc -p APPNAME test
APPNAME$ tree -L 2 --charset=ascii
[JeongLee  224]  .
|-- [JeongLee  160]  APPNAMEApp
|   |-- [JeongLee   96]  Db
|   |-- [JeongLee  419]  Makefile
|   `-- [JeongLee  128]  src
|-- [JeongLee  900]  Makefile
|-- [JeongLee  320]  configure
|   |-- [JeongLee 1.2K]  CONFIG
|   |-- [JeongLee 1.6K]  CONFIG_SITE
|   |-- [JeongLee  157]  Makefile
|   |-- [JeongLee 1.6K]  RELEASE
|   |-- [JeongLee  120]  RULES
|   |-- [JeongLee   39]  RULES.ioc
|   |-- [JeongLee   41]  RULES_DIRS
|   `-- [JeongLee   40]  RULES_TOP
`-- [JeongLee  128]  iocBoot
    |-- [JeongLee  121]  Makefile
    `-- [JeongLee  128]  ioctest
APPNAME$ echo "EPICS_BASE=/Users/JeongLee/epics/macOS-13.5.2/7.0.7/base" > configure/RELEASE.local
APPNAME$ make
```
