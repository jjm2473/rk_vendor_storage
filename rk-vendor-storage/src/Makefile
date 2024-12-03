CC = gcc
CFLAGS = -Wall
OBJS = rk_vendor_storage.o

all: rk_vendor_storage

%.o: %.c
	$(CC) $(CFLAGS) -c -o $@ $<

rk_vendor_storage: $(OBJS)
	$(CC) -o $@ $(OBJS)

clean:
	rm -f rk_vendor_storage *.o
