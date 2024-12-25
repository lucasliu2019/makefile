CC = gcc # the compiler
CFLAGS = -Wno-implicit-function-declaration -Wall -W -Wextra# compiler flag
objects = main.o hello.o

#possible flag to use: -std=c17

#rule: condition ---- When type 'make', the 1st rule will be executed.
# desired file: dependent file
# if the condition file does not exist, then it will run the rule for final!!.. unitl reach the rule that dependecy is met!!!
# targets: prerequisites
#	command
#	command
#	command
# if the depedency file has newer time stamp, it will regenrate the file ( try use touch command to change the time stamp)

# use wild card
# thing_right := $(wildcard *.o) instead of hing_wrong := *.o

# we can defien variable a:=''''', and use it ${a} / $(a)

# the rule we want to run
# he make tool will stop running a rule (and will propogate back to prerequisites) if a command returns a nonzero exit status. DELETE_ON_ERROR will delete the target of a rule if the rule fails in this manner.
.DELETE_ON_ERROR:
all: final

# special variable: $^: all prerequisites, $? all prerequisite newer $< first prerequistite $@ target name

# $@: $^
final: $(objects)
	@echo "--- Liking and producing the final application"
	$(CC) $(CFLAGS) $^ -Wall -Wextra -o $@

# wildcard % used in a matching mode
# Define a pattern rule that compiles every .c file into a .o file
%.o : %.c
	@echo "--- Special Rule compiles every .c file into a .o file"
	$(CC) -c $(CFLAGS) $(CPPFLAGS) -Wall $< -o $@


# main.o: main.c
# 	@echo "--- Compiling the main file"
# 	$(CC) $(CFLAGS) -c $^

# hello.o: hello.c
# 	@echo "--- Compiling the hello file"
# 	$(CC) $(CFLAGS) -c $^

# this rule never run unless we type make clean! use .PHONY to fix this
# rm main.o hello.o final
# Adding .PHONY to a target will prevent Make from confusing the phony target with a file name. 
.PHONY: clean
clean:
	@echo "--- Removing everything but the source files"
	rm $(wildcard *.o) final