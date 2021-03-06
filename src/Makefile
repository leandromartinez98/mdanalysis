#
# Makefile for mdanalysis
#
# This make file will try to compile packmol with gfortran
# For doing this, just type
#
#          make 
#
# If you want to compile with some specific fortran compiler, you 
# must change the line below to the path of your fortran compiler. 
#
# Version 19.340
#
FORTRAN = gfortran
#FORTRAN = ifort
#
# Change "AUTO" to the fortran command you want.
#
# Change the flags of the compilation if you want:
#
FLAGS = -O3 -ffast-math -frecord-marker=4
GENCANFLAGS = -O3 -ffast-math
#
ifeq ($(MAKECMDGOALS),devel)
  FLAGS = -Wall -fcheck=bounds
endif
#
# Source files:
SRC=.
# Object files:
OBJ=../obj
# Executable files
BIN=../bin
# Source scripts
SCR=../scripts

# Base directory of instalation (do not change this)
IDIR=$(shell dirname `pwd`)

devel : all

all : $(BIN) \
      $(OBJ) \
      $(BIN)/energy \
      $(BIN)/align \
      $(BIN)/distance \
      $(BIN)/solvation \
      $(BIN)/gmd \
      $(BIN)/gmd2 \
      $(BIN)/angles \
      $(BIN)/hbonds \
      $(BIN)/globalstructure \
      $(BIN)/jarzynski \
      $(BIN)/tcf \
      $(BIN)/fitexp \
      $(BIN)/histogram \
      $(BIN)/perresidueavg \
      $(BIN)/lifetime \
      $(BIN)/data_average \
      warning

#
# energy module
#

$(BIN)/energy : $(OBJ)/common.o $(OBJ)/energy.o $(BIN)/energy.sh
	$(FORTRAN) $(FLAGS) -o $(BIN)/energy $(OBJ)/energy.o $(OBJ)/common.o

$(OBJ)/energy.o : $(SRC)/energy.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/energy.o $(SRC)/energy.f90

$(BIN)/energy.sh : $(SCR)/energy-base.sh
	sed 's!PWD!$(IDIR)!' $(SCR)/energy-base.sh > $(BIN)/energy.sh
	chmod +x $(BIN)/energy.sh


#
# align module
#

$(BIN)/align : $(OBJ)/common.o $(OBJ)/align.o $(BIN)/align.sh
	$(FORTRAN) $(FLAGS) -o $(BIN)/align $(OBJ)/align.o $(OBJ)/common.o -llapack

$(OBJ)/align.o : $(SRC)/align.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/align.o $(SRC)/align.f90

$(BIN)/align.sh : $(SCR)/align-base.sh
	sed 's!PWD!$(IDIR)!' $(SCR)/align-base.sh > $(BIN)/align.sh
	chmod +x $(BIN)/align.sh


#
# distance module
#

$(BIN)/distance : $(OBJ)/common.o $(OBJ)/distance.o $(BIN)/distance.sh
	$(FORTRAN) $(FLAGS) -o $(BIN)/distance $(OBJ)/distance.o $(OBJ)/common.o

$(OBJ)/distance.o : $(SRC)/distance.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/distance.o $(SRC)/distance.f90

$(BIN)/distance.sh : $(SCR)/distance-base.sh
	sed 's!PWD!$(IDIR)!' $(SCR)/distance-base.sh > $(BIN)/distance.sh
	chmod +x $(BIN)/distance.sh

#
# solvation module
#

$(BIN)/solvation : $(OBJ)/common.o $(OBJ)/solvation.o $(BIN)/solvation.sh
	$(FORTRAN) $(FLAGS) -o $(BIN)/solvation $(OBJ)/solvation.o $(OBJ)/common.o

$(OBJ)/solvation.o : $(SRC)/solvation.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/solvation.o $(SRC)/solvation.f90

$(BIN)/solvation.sh : $(SCR)/solvation-base.sh
	sed 's!PWD!$(IDIR)!' $(SCR)/solvation-base.sh > $(BIN)/solvation.sh
	chmod +x $(BIN)/solvation.sh

#
# gmd module
#

$(BIN)/gmd : $(OBJ)/smalldistances.o $(OBJ)/common.o $(OBJ)/gmd.o $(BIN)/gmd.sh
	$(FORTRAN) $(FLAGS) -o $(BIN)/gmd $(OBJ)/gmd.o $(OBJ)/common.o $(OBJ)/smalldistances.o

$(OBJ)/gmd.o : $(SRC)/gmd.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/gmd.o $(SRC)/gmd.f90

$(BIN)/gmd.sh : $(SCR)/gmd-base.sh
	sed 's!PWD!$(IDIR)!' $(SCR)/gmd-base.sh > $(BIN)/gmd.sh
	chmod +x $(BIN)/gmd.sh

$(OBJ)/smalldistances.o : $(SRC)/smalldistances.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/smalldistances.o $(SRC)/smalldistances.f90

#
# gmd2 module
#

$(BIN)/gmd2 : $(OBJ)/smalldistances.o $(OBJ)/common.o $(OBJ)/gmd2.o $(BIN)/gmd2.sh
	$(FORTRAN) $(FLAGS) -o $(BIN)/gmd2 $(OBJ)/gmd2.o $(OBJ)/common.o $(OBJ)/smalldistances.o

$(OBJ)/gmd2.o : $(SRC)/gmd2.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/gmd2.o $(SRC)/gmd2.f90

$(BIN)/gmd2.sh : $(SCR)/gmd2-base.sh
	sed 's!PWD!$(IDIR)!' $(SCR)/gmd2-base.sh > $(BIN)/gmd2.sh
	chmod +x $(BIN)/gmd2.sh


#
# angles module
#

$(BIN)/angles : $(OBJ)/common.o $(OBJ)/angles.o $(BIN)/angles.sh
	$(FORTRAN) $(FLAGS) -o $(BIN)/angles $(OBJ)/angles.o $(OBJ)/common.o

$(OBJ)/angles.o : $(SRC)/angles.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/angles.o $(SRC)/angles.f90

$(BIN)/angles.sh : $(SCR)/angles-base.sh
	sed 's!PWD!$(IDIR)!' $(SCR)/angles-base.sh > $(BIN)/angles.sh
	chmod +x $(BIN)/angles.sh


#
# hbonds module
#

$(BIN)/hbonds : $(OBJ)/common.o $(OBJ)/hbonds.o $(BIN)/hbonds.sh
	$(FORTRAN) $(FLAGS) -o $(BIN)/hbonds $(OBJ)/hbonds.o $(OBJ)/common.o

$(OBJ)/hbonds.o : $(SRC)/hbonds.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/hbonds.o $(SRC)/hbonds.f90

$(BIN)/hbonds.sh : $(SCR)/hbonds-base.sh
	sed 's!PWD!$(IDIR)!' $(SCR)/hbonds-base.sh > $(BIN)/hbonds.sh
	chmod +x $(BIN)/hbonds.sh

#
# globalstructure module
#

$(BIN)/globalstructure : $(OBJ)/globalstructure.o $(OBJ)/common.o
	$(FORTRAN) $(FLAGS) -o $(BIN)/globalstructure $(OBJ)/globalstructure.o $(OBJ)/common.o -llapack

$(OBJ)/globalstructure.o : $(SRC)/globalstructure.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/globalstructure.o $(SRC)/globalstructure.f90

#
# jarzynski module
#

$(BIN)/jarzynski : $(OBJ)/common.o $(OBJ)/jarzynski.o
	$(FORTRAN) $(FLAGS) -o $(BIN)/jarzynski $(OBJ)/jarzynski.o $(OBJ)/common.o

$(OBJ)/jarzynski.o : $(SRC)/jarzynski.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/jarzynski.o $(SRC)/jarzynski.f90

#
# time correlation function module
#

$(BIN)/tcf : $(OBJ)/common.o $(OBJ)/tcf.o
	$(FORTRAN) $(FLAGS) -o $(BIN)/tcf $(OBJ)/tcf.o $(OBJ)/common.o

$(OBJ)/tcf.o : $(SRC)/tcf.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/tcf.o $(SRC)/tcf.f90


#
# fitexp module
#

$(BIN)/fitexp : $(OBJ)/common.o $(OBJ)/fitexp.o $(OBJ)/algencan-pocket.o
	$(FORTRAN) $(GENCANFLAGS) -o $(BIN)/fitexp $(OBJ)/fitexp.o \
                                                $(OBJ)/common.o \
                                                $(OBJ)/algencan-pocket.o

$(OBJ)/fitexp.o : $(SRC)/fitexp.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/fitexp.o $(SRC)/fitexp.f90

$(OBJ)/algencan-pocket.o : $(SRC)/algencan-pocket.f
	$(FORTRAN) $(GENCANFLAGS) -c -o $(OBJ)/algencan-pocket.o $(SRC)/algencan-pocket.f

#
# histogram program
#

$(BIN)/histogram : $(OBJ)/histogram.o
	$(FORTRAN) $(FLAGS) -o $(BIN)/histogram $(OBJ)/histogram.o $(OBJ)/common.o

$(OBJ)/histogram.o : $(SRC)/histogram.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/histogram.o $(SRC)/histogram.f90

#
# perresideavg program
#

$(BIN)/perresidueavg : $(OBJ)/perresidueavg.o
	$(FORTRAN) $(FLAGS) -o $(BIN)/perresidueavg $(OBJ)/perresidueavg.o

$(OBJ)/perresidueavg.o : $(SRC)/perresidueavg.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/perresidueavg.o $(SRC)/perresidueavg.f90

#
# lifetime program
#

$(BIN)/lifetime : $(OBJ)/lifetime.o
	$(FORTRAN) $(FLAGS) -o $(BIN)/lifetime $(OBJ)/lifetime.o

$(OBJ)/lifetime.o : $(SRC)/lifetime.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/lifetime.o $(SRC)/lifetime.f90


#
# data_average program
# 

$(BIN)/data_average : $(OBJ)/data_average.o $(OBJ)/common.o
	$(FORTRAN) $(FLAGS) -o $(BIN)/data_average $(OBJ)/data_average.o $(OBJ)/common.o

$(OBJ)/data_average.o : $(SRC)/data_average.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/data_average.o $(SRC)/data_average.f90

#
# This is common for all packages
#

$(OBJ)/common.o : $(SRC)/common.f90
	$(FORTRAN) $(FLAGS) -c -o $(OBJ)/common.o $(SRC)/common.f90


$(OBJ) : 
	mkdir -p ../obj
$(BIN) : 
	mkdir -p ../bin

warning : 

	@echo " ------------------------------------------------------ " 
	@echo " Compilation finished successfully. "
	@echo " IMPORTANT: If the programs won't run in the mdanalysi/bin "
	@echo " directory, change the paths in each .sh script or"
	@echo " remake all in the actual running directory."
	@echo " ------------------------------------------------------ " 


clean :
	\rm -rf $(OBJ)
	\rm -rf $(BIN)
	\rm -f ./*.mod


