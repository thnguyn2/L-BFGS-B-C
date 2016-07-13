# Feb 17 2015, converted fortran to C
# Stephen Becker, stephen.becker@colorado.edu


CFLAGS = -g -pg #Moderate optimization, -O0: no optimization, -O3: maximum optimizationi
LDFLAGS = -lm
CC = g++
INCLUDES = -I/usr/local/include -I./


SRC = lbfgsb.c linesearch.c subalgorithms.c print.c linpack.c miniCBLAS.c timer.c
default: all test_1
all :  lbfgsb_77_1 lbfgsb_77_2 lbfgsb_77_3

lbfgsb_77_1 : driver1.c $(SRC)
	$(CC) $(CFLAGS) driver1.c $(SRC) -o driver1

lbfgsb_77_2 : driver2.c $(LBFGSB) $(LINPACK) $(BLAS) $(TIMER)
	$(CC) $(CFLAGS) driver2.c $(SRC) -o driver2

lbfgsb_77_3 : driver3.c $(LBFGSB) $(LINPACK) $(BLAS) $(TIMER)
	$(CC) $(CFLAGS) driver3.c $(SRC) -o driver3

test_1 : driver1
	./driver1
