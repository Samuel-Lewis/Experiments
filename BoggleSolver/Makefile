#
# Generic Makefile
#  https://github.com/Samuel-Lewis/lunchbox
#
#  Samuel Lewis
#  5th Dec 2015
#
# COMMANDS TO USE
#  make		makes all
#  make run	makes all and executes the product
#  make debug	makes all with added flag of -DDEBUG (defines DEBUG)
#  make clean	cleans up all .o files and the product
#

# PROJECT NAME
PROJECT = main

# COMPILER
CC = g++
VERSION = -std=c++11
CC_OPTIONS = -pedantic -Wall -Wextra -O2 #-ansi

# Includes and linkers
HEADERS =
LIBS =



#########################
# No need to edit below here

# Sources
SOURCES = $(shell find . -type f -name "*.cpp")
SRC_OBJECTS = $(SOURCES:.cpp=.o)

%.o: %.cpp
	$(CC) -c $(CC_OPTIONS) $(HEADERS) $(VERSION) $^ -o $@

$(PROJECT): $(SRC_OBJECTS)
	$(CC) -o $(PROJECT) $(SRC_OBJECTS) $(LIBS)

# Builds
all: $(PROJECT)

run: $(PROJECT)
	./$(PROJECT)

debug: CC_OPTIONS += -DDEBUG
debug: all

# Clean
.PHONY: clean
clean:
	rm -f $(PROJECT) $(SRC_OBJECTS)
