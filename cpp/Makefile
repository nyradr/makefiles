#output name
NAME=prog
#basic directories
INC=./include
SRC=./src
OBJ=./obj
BIN=./bin
#c files list in src
CPPFILES=$(patsubst $(SRC)/%.cpp, %.o, $(shell find $(SRC) -name '*.cpp'))
#compiler options
CPP=g++
CPPFLAGS=-Wall -I$(INC)

all: predef prog

# link .o files in program
prog: $(CPPFILES)
	$(CPP) -o $(BIN)/$(NAME) $(CPPFLAGS) $(addprefix obj/, $^)

# create obj and bin directory if not exist
predef:
	@if [ ! -d "$(OBJ)" ]; then mkdir $(OBJ); fi
	@if [ ! -d "$(BIN)" ]; then mkdir $(BIN); fi

# compile c files
%.o : $(SRC)/%.c
	$(CPP) $(CPPFLAGS) -c -o $(OBJ)/$@ $^


clean:
	rm -rf $(BIN) $(OBJ)
