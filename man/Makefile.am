# Makefile for chessopp/man
#
# Copyright (C) 2020 David Yockey
# Copyright (C) 2015 Free Software Foundation, Inc.
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

man_MANS = chessopp.1
EXTRA_DIST = $(man_MANS)
MAINTAINERCLEANFILES = $(man_MANS)

# The man pages depend on the --help strings and the version number.
common_mandeps = $(top_srcdir)/configure.ac

# Depend on the source, not the binary; we don't need to regenerate the
# binary when any source file changes, only the main one.
# Use -o so that the `missing' program can infer the output file.
chessopp.1: $(top_srcdir)/src/main.cc $(top_srcdir)/src/frontend/cmd.cc $(common_mandeps)
	$(HELP2MAN) --name='Chess Opponent' --section=6 --include='manmods' --info-page='gnuchess' ../src/chessopp -o $@

CLEANFILES = ${man_MANS}
DISTCLEANFILES = ${CLEANFILES}
