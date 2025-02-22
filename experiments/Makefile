#******************************************************************************
# Copyright (C) 2017 by Alex Fosdick - University of Colorado
#
# Redistribution, modification or use of this software in source or binary
# forms is permitted as long as the files maintain this copyright. Users are 
# permitted to modify this and use it to learn about the field of embedded
# software. Alex Fosdick and the University of Colorado are not liable for any
# misuse of this material. 
#
#*****************************************************************************

#------------------------------------------------------------------------------
# Simple makefile for the cortex-M0+ build system
#
# Use: make [TARGET] [OVERRIDES]
#
# Build Targets:
#      <FILE>.o - Builds <FILE>.o object file
#      build - Builds and links all source files
#      all - Same as build
#      clean - removes all generated files
#
# Overrides:
#      CPU - ARM Cortex Architecture (cortex-m0plus, cortex-m4)
#      ARCH - ARM Architecture (arm, thumb)
#      SPECS - Specs file to give the linker (nosys.specs, nano.specs)
#
#
#------------------------------------------------------------------------------
$(Program): build_msg $(OBJECTS) $(BUILTINS_DEP) $(LIBDEP)
	$(RM) $@
	$(CC) $(LDFLAGS) -o $(Program) $(OBJECTS) $(LIBS)
	ls -l $(Program)
	size $(Program)
.PHONY: build_msg
build_msg:
	@printf "#\n# Building $(Program)\n#\n"
