TARGET=.libs/mod_receive.so

C_SRC = mod_receive.cpp

FILES = $(C_SRC)

# Should define INCLUDES and MOD_PATH
include Makefile.lcl

default	: $(TARGET)

# Make it do c++
$(TARGET)	:	$(FILES)
	libtool --silent --mode=compile g++ -prefer-pic -O2 -Wall  -DLINUX -D_REENTRANT -D_GNU_SOURCE -pthread $(INCLUDES) -c -o mod_receive.lo $(C_SRC) && touch mod_receive.slo
	libtool --silent --mode=link g++ -o mod_receive.la -rpath $(MOD_PATH) -module -avoid-version mod_receive.lo

install	:	$(TARGET)
	sudo	cp $(TARGET)	$(MOD_PATH)


clean	:
	rm -rf .libs *.{o,lo,slo,la}

