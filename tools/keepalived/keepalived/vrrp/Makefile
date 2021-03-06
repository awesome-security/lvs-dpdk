# Makefile
#
# Keepalived OpenSource project.
#
# Copyright (C) 2001-2011 Alexandre Cassen, <acassen@linux-vs.org>

CC	 = gcc
INCLUDES = -I../include -I../../lib
CFLAGS	 = -g -O2  -I/usr/src/linux/include $(INCLUDES) \
	   -Wall -Wunused -Wstrict-prototypes
DEFS	 = -D_KRNL_2_6_ -D_WITH_LVS_ -D_HAVE_IPVS_SYNCD_ 
COMPILE	 = $(CC) $(CFLAGS) $(DEFS)

OBJS = 	vrrp_daemon.o vrrp_data.o vrrp_parser.o \
	vrrp.o vrrp_notify.o vrrp_scheduler.o vrrp_sync.o vrrp_index.o \
	vrrp_netlink.o vrrp_arp.o vrrp_if.o vrrp_track.o vrrp_ipaddress.o \
	vrrp_iproute.o vrrp_ipsecah.o vrrp_ndisc.o
HEADERS = $(OBJS:.o=.h)

.c.o:
	$(COMPILE) -c $<

all:	$(OBJS)

clean:
	rm -f *.a *.o *~

distclean: clean
	rm -f Makefile

vrrp_daemon.o: vrrp_daemon.c ../include/vrrp_daemon.h ../include/vrrp_scheduler.h \
  ../include/vrrp_if.h ../include/vrrp_arp.h ../include/vrrp_netlink.h ../include/vrrp_iproute.h \
  ../include/vrrp_iproute.h ../include/vrrp_parser.h ../include/vrrp_data.h \
  ../include/vrrp.h ../include/global_data.h ../include/pidfile.h ../include/daemon.h \
  ../include/ipvswrapper.h ../../lib/list.h ../../lib/memory.h ../../lib/parser.h \
  ../../lib/signals.h
vrrp_data.o: vrrp_data.c ../include/vrrp_data.h \
  ../include/vrrp_sync.h ../include/vrrp_if.h ../include/vrrp_index.h \
  ../include/vrrp.h ../../lib/memory.h ../../lib/utils.h ../../lib/notify.h
vrrp_parser.o: vrrp_parser.c ../include/vrrp_parser.h \
  ../include/vrrp_data.h ../include/vrrp_sync.h ../include/vrrp_index.h \
  ../include/vrrp.h ../include/global_data.h ../include/global_parser.h \
  ../../lib/parser.h ../../lib/memory.h
vrrp.o: vrrp.c ../include/vrrp.h ../include/vrrp_scheduler.h \
  ../include/vrrp_notify.h ../include/ipvswrapper.h ../../lib/memory.h \
  ../../lib/list.h ../include/vrrp_data.h ../include/vrrp_sync.h ../include/vrrp_index.h \
  ../include/vrrp_arp.h ../../lib/utils.h
vrrp_notify.o: vrrp_notify.c ../include/vrrp_notify.h ../../lib/memory.h \
  ../../lib/notify.h
vrrp_scheduler.o: vrrp_scheduler.c ../include/vrrp_scheduler.h \
  ../include/vrrp_ipsecah.h ../include/vrrp_if.h ../include/vrrp.h \
  ../include/vrrp_sync.h ../include/vrrp_notify.h ../include/ipvswrapper.h \
  ../../lib/memory.h ../../lib/list.h ../include/vrrp_data.h ../include/vrrp_index.h \
  ../include/smtp.h ../../lib/notify.h
vrrp_sync.o: vrrp_sync.c ../include/vrrp_sync.h ../include/vrrp_if.h \
  ../include/vrrp_notify.h ../include/vrrp_data.h
vrrp_index.o: vrrp_index.c ../include/vrrp_index.h ../include/vrrp.h \
  ../include/vrrp_data.h ../../lib/memory.h
vrrp_netlink.o: vrrp_netlink.c ../include/vrrp_netlink.h ../include/check_api.h \
  ../include/vrrp_if.h ../../lib/memory.h ../../lib/scheduler.h \
  ../../lib/utils.h
vrrp_arp.o: vrrp_arp.c ../include/vrrp_arp.h
vrrp_track.o: vrrp_track.c ../include/vrrp_track.h ../include/vrrp_if.h \
  ../include/vrrp_data.h ../../lib/memory.h
vrrp_if.o: vrrp_if.c ../include/vrrp_if.h ../include/vrrp_netlink.h \
  ../../lib/scheduler.h ../include/vrrp_data.h ../../lib/memory.h \
  ../../lib/utils.h
vrrp_ipaddress.o: vrrp_ipaddress.c ../include/vrrp_ipaddress.h ../include/vrrp_netlink.h \
  ../include/vrrp_if.h  ../include/vrrp_data.h ../../lib/memory.h ../../lib/utils.h
vrrp_iproute.o: vrrp_iproute.c ../include/vrrp_iproute.h ../include/vrrp_netlink.h \
  ../include/vrrp_if.h  ../include/vrrp_data.h ../../lib/memory.h ../../lib/utils.h
vrrp_ipsecah.o: vrrp_ipsecah.c ../include/vrrp_ipsecah.h
vrrp_ndisc.o: vrrp_ndisc.c ../include/vrrp_ndisc.h ../include/vrrp_ipaddress.h \
  ../../lib/utils.h ../../lib/memory.h
