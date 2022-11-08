CFLAGS=-Wall -O0 -Wno-narrowing -Wno-sign-compare -fPIC -DSWELL_PROVIDED_BY_APP
CPPFLAGS=$(CFLAGS)
LDFLAGS=
LDLIBS=

vpath %.cpp ../../WDL/swell

ALL: reaper_nanoKontrol2.so

csurf_main.o:	csurf_main.cpp res.rc_mac_dlg

res.rc_mac_dlg:	res.rc
	../../WDL/swell/swell_resgen.sh $<

reaper_nanoKontrol2.so:	csurf_nanokontrol2.o csurf_main.o swell-modstub-generic.o
	gcc -shared $(LDFLAGS) $+ -o $@ $(LDLIBS)
