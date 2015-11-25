# Copyright (C) 2008,2009,2010 Nokia Corporation
# Contact: Kai Vehmanen 
# Licensed under LGPL. See file COPYING.

SUBDIRS =		doc

EXTRA_DIST = 		cmtspeech_config.h.in \
			libcmtspeechdata.ver

# libcmtspeechdata main library sources
# -------------------------------------

lib_LTLIBRARIES = 	libcmtspeechdata.la

cmtspeechdata_common_src = \
			cmtspeech_msgs.c \
			cmtspeech_backend_common.c \
			sal_debug.c

cmtspeech_data_kernel_inc = \
			kernel-headers/linux/cs-protocol.h

cmtspeechdata_common_inc = \
			cmtspeech_backend_common.h \
			sal_ring.h \
			sal_debug.h

cmtspeechdata_pub_inc = \
			cmtspeech.h \
			cmtspeech_msgs.h

cmtspeechdata_pub_inc_nodist = \
			cmtspeech_config.h

include_HEADERS =	$(cmtspeechdata_pub_inc)

nodist_include_HEADERS =$(cmtspeechdata_pub_inc_nodist)

libcmtspeechdata_la_SOURCES = \
			$(cmtspeechdata_common_src) \
			$(cmtspeechdata_pub_inc) \
			cmtspeech_nokiamodem.c
libcmtspeechdata_la_CFLAGS = -prefer-pic
libcmtspeechdata_la_LIBADD = -lrt
libcmtspeechdata_la_LDFLAGS =  -Wl,--version-script,$(srcdir)/libcmtspeechdata.ver

# documentation rules
# -------------------

doc: 
	(cd doc && $(MAKE) $(AM_MAKEFLAGS) doc)

.PHONY : doc
