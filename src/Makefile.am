# Process this file with automake to produce Makefile.in 
# Makefile for chessopp/src.
#
# Copyright (C) 2020 David Yockey
# Copyright (C) 2001-2011 Free Software Foundation, Inc.
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3, or (at your option)
# any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.

bin_SCRIPTS = chessoppx chessoppu

bin_PROGRAMS = chessopp

chessopp_SOURCES = main.cc components.cc components.h

AM_CXXFLAGS = $(PTHREAD_CXXFLAGS)

AM_LDFLAGS = $(PTHREAD_LDFLAGS) $(PTHREAD_LIBS)

localedir = $(datadir)/locale

AM_CPPFLAGS = -I$(top_srcdir)/lib -I$(top_builddir)/lib
DEFS = -DLOCALEDIR=\"$(localedir)\" @DEFS@

DISTCLEANFILES = *~

SUBDIRS = frontend adapter engine
chessopp_LDADD = $(LIBINTL) frontend/libfrontend.a adapter/libadapter.a engine/libengine.a

configmake.h: Makefile
	rm -f $@-t $@
	{ echo '/* DO NOT EDIT! GENERATED AUTOMATICALLY! */'; \
	  echo '#define PKGDATADIR "$(pkgdatadir)"'; \
	} | sed '/""/d' > $@-t
	mv $@-t $@
BUILT_SOURCES = configmake.h
CLEANFILES = configmake.h configmake.h-t

