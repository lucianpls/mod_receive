TARGET=.libs/mod_receive.so

C_SRC = mod_receive.cpp

FILES = $(C_SRC) receive_context.h

# Create a file Makefile.lcl. It should define INCLUDES and MOD_PATH
# For example on how to create Makefile.lcl see Makefile.example.lcl

include Makefile.lcl

default	: $(TARGET)

# Make it do c++
$(TARGET)	:	$(FILES)
	$(LIBTOOL) --silent --mode=compile g++ -prefer-pic -O2 -Wall  -DLINUX -D_REENTRANT -D_GNU_SOURCE -pthread $(INCLUDES) -c -o mod_receive.lo $(C_SRC) && touch mod_receive.slo
	$(LIBTOOL) --silent --mode=link g++ -o mod_receive.la -rpath $(DEST) -module -avoid-version mod_receive.lo

install	:	$(TARGET)
	$(SUDO)	cp $(TARGET)	$(DEST)
	$(SUDO)	cp receive_context.h	$(HTTPD_INCLUDES_PATH)


clean	:
	rm -rf .libs *.{o,lo,slo,la}

