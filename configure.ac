#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.68])
AC_INIT([gstlaunch], [0.1], [greg80303@yahoo.com])
AM_INIT_AUTOMAKE
AC_CONFIG_SRCDIR([src/gstlaunch.c])
AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CC
AM_PROG_CC_C_O

# Libtool
AC_CONFIG_MACRO_DIR([libltdl/m4])
LT_CONFIG_LTDL_DIR([libltdl])
LT_INIT([dlopen])
LTDL_INIT([recursive])

# Checks for libraries.

# Checks for header files.
AC_CHECK_HEADERS([stdlib.h stdio.h])

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.

# pkg-config-based checks
PKG_PROG_PKG_CONFIG
PKG_CHECK_MODULES([GLIB], [glib-2.0 >= 2.32])

AC_ARG_ENABLE([gst-uninstalled],
            AS_HELP_STRING([--enable-gst-uninstalled], [Compile against GStreamer in an uninstalled environment]),
            [gst=gstreamer-uninstalled],
            [gst=gstreamer-1.0])

PKG_CHECK_MODULES([GSTREAMER], [$gst >= 1.0.5])

AC_CONFIG_FILES([Makefile src/Makefile libltdl/Makefile])
AC_OUTPUT
