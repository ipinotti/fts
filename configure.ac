AC_PREREQ([2.64])
AC_INIT([fts-digistar], [0.1], [ipinotti@pd3.com.br])
AC_CONFIG_SRCDIR([src/fts-digistar.h])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])

AM_INIT_AUTOMAKE(AC_PACKAGE_NAME, AC_PACKAGE_VERSION)

# Checks for programs.
AC_PROG_CC
AM_PROG_AS
AC_PROG_INSTALL
AC_PROG_MAKE_SET

# Check endianess
AC_C_BIGENDIAN

# Checks for libraries.
AC_CHECK_LIB(m, log10,, exit)
AC_CHECK_LIB(crypt, setkey,,exit)
AC_CHECK_LIB(ncurses, tgetent,, exit)
AC_CHECK_LIB(pam, pam_get_data,, exit)
AC_CHECK_LIB(pam_misc, pam_misc_setenv,, exit)
AC_CHECK_LIB(crypto, RSA_public_encrypt,, exit)
AC_SEARCH_LIBS([iptc_init], [iptc ip4tc],, AC_MSG_ERROR([unable to find the iptc_init() function]))
AC_CHECK_LIB(usb-1.0, libusb_init,, exit)
AC_CHECK_LIB(router, librouter_config_mmap_cfg,, exit)
AC_CHECK_LIB(readline, rl_on_new_line,, exit)

# Checks for header files.
AC_CHECK_HEADERS([arpa/inet.h fcntl.h netdb.h netinet/in.h stdlib.h string.h sys/file.h sys/ioctl.h sys/mount.h sys/socket.h sys/time.h syslog.h termios.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_PID_T
AC_TYPE_SIZE_T

# Checks for library functions.
AC_FUNC_CHOWN
AC_FUNC_FORK
AC_FUNC_MALLOC
AC_FUNC_MKTIME
AC_FUNC_MMAP
AC_CHECK_FUNCS([alarm gethostbyname gethostname gettimeofday inet_ntoa localtime_r memset munmap select sethostname socket strcasecmp strchr strcspn strdup strerror strrchr strstr strtol strtoul strtoull uname])

AM_PROG_LIBTOOL

SHAVE_INIT([m4], [enable]) # dnl Make the output pretty

AC_CONFIG_FILES([m4/shave
		 m4/shave-libtool
		 Makefile
		 src/Makefile])

AC_OUTPUT
