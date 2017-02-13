# $Id: GNUmakefile,v 1.1 1999/01/07 16:05:42 gunter Exp $
# --------------------------------------------------------------
# GNUmakefile for examples module.  Gabriele Cosmo, 06/04/98.
# --------------------------------------------------------------

name := simutesting
G4TARGET := $(name)
G4EXLIB := true

#G4INSTALL := ${SIMHOME}/builds/geant4-install/share/Geant4-9.5.1/geant4make
G4INSTALL :=  /home/branden/builds/geant4-install/share/Geant4-9.5.1/geant4make


ifndef G4INSTALL
  G4INSTALL = ../../..
endif

.PHONY: all
all: lib bin

#EXTRALIBS += $(shell $(ROOTSYS)/bin/root-config --glibs)
#CPPFLAGS += $(shell $(ROOTSYS)/bin/root-config --cflags)

#BS, Without these next two lines I can't compoile, check on their purpose
#ROOTINC = -I${HOME}/simulation/builds/root/include
ROOTINC = -I/home/branden/builds/root/include
CPPFLAGS += $(ROOTINC)

# Add ROOT options for compilation
CPPFLAGS += `root-config --cflags`
CPPFLAGS += -I/home/branden/builds/CLHEP-install/include/CLHEP
LDFLAGS += `root-config --libs`
LDFLAGS += -L$(G4LIB)/$(G4SYSTEM)
LDFLAGS += -L/home/branden/builds/CLHEP-install/lib

# Add FMSSRC headers
CPPFLAGS += -I$(FMSSRC)
EXTRALIBS := $(FMSSRC)/Fpdchan.so
G4DEBUG = 1

#BS. NOT SURE HOW TO HAVE THE MAKEFILE COMPILE THE CLASS WITHOUT THIS. NEED TO FIX LATER
#EXTRALIBS += ${SIMHOME}/geant/fmsu/myRootClass/libG4QT.so
EXTRALIBS += /home/branden/simulations/geant/fmsu/myRootClass/libG4QT.so
include $(G4INSTALL)/config/binmake.gmk
