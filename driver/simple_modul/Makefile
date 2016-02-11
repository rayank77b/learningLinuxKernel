ifneq ($(KERNELRELEASE),) 
obj-m	:= mod1.o

else
KDIR	:= /lib/modules/$(shell uname -r)/build
PWD	:= $(shell pwd)

all:
	$(MAKE)	-C $(KDIR) SUBDIRS=$(PWD) modules
endif
