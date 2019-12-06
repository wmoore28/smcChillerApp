TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = chiller
# chiller.dbd will be created and installed
DBD += chiller.dbd

# chiller.dbd will be made up from these files:
chiller_DBD += base.dbd
chiller_DBD += drvAsynIPPort.dbd
chiller_DBD += modbusSupport.dbd
chiller_DBD += asyn.dbd

# Add all the support libraries needed by this IOC
chiller_LIBS += modbus
chiller_LIBS += asyn

# chiller_registerRecordDeviceDriver.cpp derives from chiller.dbd
chiller_SRCS += chiller_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
chiller_SRCS_DEFAULT += chillerMain.cpp
chiller_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#chiller_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
chiller_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

