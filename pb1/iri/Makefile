
#########################################################################
#
# Makefile for iri code
# Created by:  G. Fenton 5/22/2022
#
#########################################################################

FC = gfortran    
FFLAGS = -std=legacy -fPIC -m64
LFLAGS = -shared -m64
OBJECTS = iritest.o irisub.o irifun.o iritec.o iridreg.o igrf.o cira.o iriflip.o

ECHO   = echo

%.o : %.for
	$(FC) $(FFLAGS) -c $< 

iri.so: $(OBJECTS)
	$(FC) $(LFLAGS) $(OBJECTS) -o iri.so 

#-- clean up the compile directory and binaries
clean :
	@$(ECHO)
	@$(ECHO) "Cleaning Up Object code "
	@$(ECHO) "------------------------"
	/bin/rm -f core *.o *.so *.exe
	@$(ECHO)

test.exe: irirtam.o irirtam-test.o
	$(FC) irirtam.o irirtam-test.o -o test.exe

