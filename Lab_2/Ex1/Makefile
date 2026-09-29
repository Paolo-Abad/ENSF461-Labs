osName := $(shell uname -s)



ifneq ($(osName), Linux)
.PHONY: all
all:
		@echo "Sorry, I prefer Linux"
else

.PHONY: all
all: gen_numbers.out select_arg.out gen_in_range.out

%.out: %.o utils.o
		gcc -o $@ $^

%.o: %.c utils.h
		gcc -c $^

endif

.PHONY: clean
clean:
		rm -f *.out *.o


.PHONY: test
test: all
		./gen_numbers.out 3
		./select_arg.out sarvesh the great genius human alive
		./gen_in_range.out 100 1000
