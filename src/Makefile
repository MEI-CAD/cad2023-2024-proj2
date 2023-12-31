#
# Simplified simulation of high-energy particle storms
#
# Parallel computing (Degree in Computer Engineering)
# 2017/2018
#
# EduHPC 2018: Peachy assignment
#
# (c) 2018 Arturo Gonzalez-Escribano, Eduardo Rodriguez-Gutiez
# Grupo Trasgo, Universidad de Valladolid (Spain)
#
# This work is licensed under a Creative Commons Attribution-ShareAlike 4.0 International License.
# https://creativecommons.org/licenses/by-sa/4.0/
#
#
# The current Parallel Computing course includes contests using:
# OpenMP, MPI, and CUDA.
#

# Compilers
CC=gcc
MPICC=mpicc

# Flags for optimization and libs
FLAGS=-O3
LIBS=-lm

# Targets to build
OBJS=energy_storms_seq energy_storms_mpi

# Rules. By default show help
help:
	@echo
	@echo "Simplified simulation of high-energy particle storms"
	@echo
	@echo "Group Trasgo, Universidad de Valladolid (Spain)"
	@echo "EduHPC 2018: Peachy assignment"
	@echo "DI, FCT NOVA"
	@echo "CAD 2023/2024"
	@echo
	@echo "make energy_storms_seq	Build only the sequential version"
	@echo "make energy_storms_mpi
	@echo
	@echo "make all	Build all versions (Sequential, MPI)"
	@echo "make debug	Build all version with demo output for small arrays (size<=35)"
	@echo "make clean	Remove targets"
	@echo

all: $(OBJS)

energy_storms_seq: energy_storms_seq.c
	$(CC) $(DEBUG) $< $(LIBS) -o $@

energy_storms_mpi: energy_storms_mpi.c
	$(MPICC) $(DEBUG) $< $(LIBS) -o $@

# Remove the target files
clean:
	rm -rf $(OBJS)

# Compile in debug mode
debug:
	make DEBUG=-DDEBUG all
