TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = _APPNAME_
# _APPNAME_.dbd will be created and installed
DBD += _APPNAME_.dbd

Common_DBDs += base.dbd

Common_SRCs +=

ifneq ($(ASYN),)
Common_DBDs += asyn.dbd
Common_DBDs += drvAsynIPPort.dbd
Common_DBDs += drvAsynSerialPort.dbd
Common_LIBs += asyn
endif

ifneq ($(STREAM),)
Common_DBDs += stream.dbd
Common_LIBs += stream
endif

# Include dbd files from all support applications:
_APPNAME__DBD  += $(Common_DBDs)
_APPNAME__LIBS += $(Common_LIBs)
_APPNAME__SRCS += $(Common_SRCs)
_APPNAME__SRCS += _APPNAME__registerRecordDeviceDriver.cpp

# System Libraries
_APPNAME__SYS_LIBS +=
_APPNAME__SYS_LIBS_Linux +=

# Build the main IOC entry point on workstation OSs.
_APPNAME__SRCS_DEFAULT += _APPNAME_Main.cpp
_APPNAME__SRCS_vxWorks += -nil-

_APPNAME__OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary
_APPNAME__LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

