CC = gcc

OS = $(shell uname -s)

.PHONY: all clean test


ifeq ($(OS),Linux)
all: gen_numbers.out select_arg.out gen_in_range.out
else
all:
	@echo "Sorry, I prefer Linux"
endif


%.out: %.c
	$(CC) -o $@ $<

gen_numbers.out select_arg.out: %.out: %.c utils.c utils.h
	$(CC) -o $@ $< utils.c

clean:
	rm -f *.out



test: all
	./gen_numbers.out 5
	./select_arg.out apple banana orange
	./gen_in_range.out 1 100
