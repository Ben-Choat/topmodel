# define the C compiler to use
CC = gcc

# define any compile-time flags
# for newer compiler, the right hand side is not needed
CFLAGS = -std=c99

INCLUDES = -I../include

LFLAGS =

LIBS = -lm

# define the C source files
SRCS = main.c bmi_topmodel.c topmodel.c

# define the C object files 
OBJS = $(SRCS:.c=.o)

# define the executable file 
MAIN = run_bmi

.PHONY: depend clean

all:    $(MAIN)
	@echo  Simple compiler named mycc has been compiled
	@mv run_bmi ..

$(MAIN): $(OBJS) 
	$(CC) $(CFLAGS) $(INCLUDES) -o $(MAIN) $(OBJS) $(LFLAGS) $(LIBS)

# this is a suffix replacement rule for building .o's from .c's
# it uses automatic variables $<: the name of the prerequisite of
# the rule(a .c file) and $@: the name of the target of the rule (a .o file) 
# (see the gnu make manual section about automatic variables)
.c.o:
	$(CC) $(CFLAGS) $(INCLUDES) -c $<  -o $@

clean:
	$(RM) *.o *~ $(MAIN)

depend: $(SRCS)
	makedepend $(INCLUDES) $^
