# Makefile for compiling a the idraw
CC=mpicc
LD=mpicc
RM=rm -f
#Production flags
CFLAGS= -std=c99 -fopenmp -O2
LDFLAGS= -std=c99 -fopenmp -lm -O2
UBUNTUFLAGS=-lm $(LDFLAGS)  
OPENSUSEFLAGS=-lm $(LDFLAGS) 
DEBUG=-O2
OBJS:=main.o Matrix.o MyRand.o Ant_Colony.o 
MAIN=Ejecutable
all:$(MAIN)
ubuntu:
	$(MAKE) "OPENSUSEFLAGS="
opensuse:
	$(MAKE) "UBUNTUFLAGS="
$(MAIN):$(OBJS)
	$(LD) $(DEBUG) $(OPENSUSEFLAGS) $(OBJS) -o $(MAIN) $(UBUNTUFLAGS)
%.o: %.cpp %.hpp
	$(CC) $(CFLAGS) $(DEBUG) -c $<
%.o: %.c %.h
	$(CC) $(CFLAGS) $(DEBUG) -c $<	
%.o: %.c
	$(CC) $(CFLAGS) $(DEBUG) -c $<	
%.o: %.cpp 
	$(CC) $(CFLAGS) $(DEBUG) -c $<	
debug:
	$(MAKE) "DEBUG=-g"
clean:
	$(RM) $(OBJS) *.*~
cleanall:
	$(RM) $(OBJS) $(MAIN) *.*~
	
