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

# _APPNAME_.dbd will be made up from these files:i
Common_DBDs += base.dbd
Common_DBDs += system.dbd

Common_SRCs +=
Common_LIBs +=

ifneq ($(SNCSEQ),)
sncExample_SNCFLAGS += +r
Common_DBDs += sncExample.dbd
# A .stt sequence program is *not* pre-processed:
Common_SRCs += sncExample.stt
Common_LIBs += seq pv
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

# Add support from base/src/vxWorks if needed
#_APPNAME__OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
_APPNAME__LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

