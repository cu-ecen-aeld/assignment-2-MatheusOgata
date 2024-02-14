GCC=gcc
SRC=$(wildcard *.c)
DEP=$(SRC:.c=.o)

ifneq ($(CROSS_COMPILE),)
        CC=$(addprefix $(CROSS_COMPILE), $(GCC))
else
        CC=$(GCC)
endif


all: $(DEP) writer

%: %.o
	$(CC) -o $@ $(DEP)


%.o: %.c %.h
	$(CC) -c $< -o $@


clean:
	rm *.o
	rm writer
