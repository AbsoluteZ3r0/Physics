OBJS = main.o particles.o constants.o newtonian.o elements.o electric.o
CC = gcc
DEBUG = -g
CFLAGS = -Wall -O3 -c -march=native $(DEBUG)
LFLAGS = -Wall -lpthread -lGL -LGLU -lglut -lm $(DEBUG)

physics : $(OBJS)
	$(CC) $(LFLAGS) $(OBJS) -o physics

main.o : main.c particles.h constants.h
	$(CC) $(CFLAGS) main.c

particles.o : particles.h particles.c constants.h newtonian.h electric.h
	$(CC) $(CFLAGS) particles.c

constants.o : constants.h constants.c
	$(CC) $(CFLAGS) constants.c

newtonian.o : newtonian.h newtonian.c
	$(CC) $(CFLAGS) newtonian.c

elements.o : elements.h elements.c
	$(CC) $(CFLAGS) elements.c

electric.o : electric.h electric.c constants.h
	$(CC) $(CFLAGS) electric.c
	
clean :
	\rm *.o physics
