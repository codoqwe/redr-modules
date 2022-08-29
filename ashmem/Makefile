ccflags-y += -I$(src)
obj-m := ashmem_linux.o
ashmem_linux-y := ashmem.o deps.o

KDIR ?= /lib/modules/4.15.18-4-pve/build

all:
	$(MAKE) -C $(KDIR) M=$$PWD

install: all
	insmod ashmem_linux.ko

modules_install:
	$(MAKE) -C $(KDIR) M=$$PWD modules_install

uninstall:
	rmmod ashmem_linux

clean:
	$(MAKE) -C $(KDIR) M=$$PWD clean

