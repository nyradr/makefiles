#output name
NAME=prog
#basic directories
INC=./include
SRC=./src
OBJ=./obj
BIN=./bin
#c files list in src
CFILES=$(patsubst $(SRC)/%.c, %.o, $(shell find $(SRC) -name '*.c'))
#compiler options
CC=gcc
CFLAGS=-Wall -I$(INC)

all: predef prog

# link .o files in program
prog: $(CFILES)
	$(CC) -o $(BIN)/$(NAME) $(CFLAGS) $(addprefix obj/, $^)

# create obj and bin directory if not exist
predef:
	@if [ ! -d "$(OBJ)" ]; then mkdir $(OBJ); fi
	@if [ ! -d "$(BIN)" ]; then mkdir $(BIN); fi

# compile c files
%.o : $(SRC)/%.c
	$(CC) $(CFLAGS) -c -o $(OBJ)/$@ $^


clean:
	rm -rf $(BIN) $(OBJ)
