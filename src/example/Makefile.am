# Copyright (c) 2014-2015, Fabian Knorr
#
# This file is part of libgtkglcanvas.
#
# libgtkglcanvas is free software: you can redistribute it and/or modify
# it under the terms of the GNU Lesser General Public License as published
# by the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# libgtkglcanvas is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public License
# along with libgtkglcanvas.  If not, see <http://www.gnu.org/licenses/>.


check_PROGRAMS = $(top_builddir)/example

__top_builddir__example_SOURCES = \
	main.c \
	filter-dialog.c

__top_builddir__example_LDADD = \
	$(top_builddir)/libgtkglcanvas.la \
	-lm \
	$(GTK_LIBS) \
	$(OpenGL_LIBS) \
	$(Epoxy_LIBS)

__top_builddir__example_CPPFLAGS = \
	-I$(top_srcdir)/include \
	$(OpenGL_CFLAGS) \
	$(Epoxy_CFLAGS) \
    $(GTK_CFLAGS)

if PLATFORM_WIN32
__top_builddir__example_LDFLAGS = \
	-Wl,--export-all-symbols
# FreeType missing symbols workaround
__top_builddir__example_LDADD += -lbz2
else
__top_builddir__example_CFLAGS = \
	-rdynamic
endif
