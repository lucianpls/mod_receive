TARGET=../mod_receive.so

C_SRC = mod_receive.cpp

FILES = $(C_SRC)

include ../Makefile.lcl

default	: $(TARGET)

# Make it do c++
$(TARGET)	:	$(FILES)
	libtool --silent --mode=compile g++ -prefer-pic -O2 -Wall  -DLINUX -D_REENTRANT -D_GNU_SOURCE -pthread -I/home/agsonline/include -c -o mod_receive.lo $(C_SRC) && touch mod_receive.slo
	libtool --silent --mode=link g++ -o ../mod_receive.la -rpath /home/agsonline/modules -module -avoid-version mod_receive.lo


clean	:
	rm -rf .libs *.{o,lo,slo,la}

