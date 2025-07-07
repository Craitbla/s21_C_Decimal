CC = gcc -Wall -Werror -Wextra -std=c11
OS := $(shell uname -s)

# Упрощаем флаги для Linux (Alpine)
ifeq ($(OS),Linux)
    Flags = -lcheck -lm -lpthread
else
    Flags = -lcheck -lm -lpthread
endif

all: clean s21_decimal.a
 
s21_decimal.a:
	$(CC) -c *.c
	ar rcs s21_decimal.a *.o
	ranlib s21_decimal.a
	rm -f *.o

test: clean
	$(CC) --coverage *.c tests/*.c -o test $(Flags)
	./test

gcov_report: test
	lcov -t "result" -o res.info -c -d .
	genhtml -o report res.info
	open report/index.html || xdg-open report/index.html

clang:
	clang-format -style=Google -n *.c *.h

clean:
	rm -rf test s21_decimal.a *.gcno *.info *.gcda report *.dSYM