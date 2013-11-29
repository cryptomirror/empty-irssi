AM_CFLAGS = $(PACKAGE_FLAGS)

IRSSI_DIST=/usr/include/irssi
IRSSI_INCLUDE = -I$(IRSSI_DIST) \
				-I$(IRSSI_DIST)/src \
				-I$(IRSSI_DIST)/src/fe-common/core \
				-I$(IRSSI_DIST)/src/core \
				-I$(IRSSI_DIST)/src/fe-text \
				-I$(IRSSI_DIST)/src/irc \
				-I$(IRSSI_DIST)/src/irc/core \
				-I$(IRSSI_DIST)/src/irc/dcc \
				-I$(IRSSI_DIST)/src/irc/notifylist

INCLUDES = -I$(top_srcdir)/src $(IRSSI_INCLUDE)

plugindir = $(IRSSI_MODULE_DIR)
plugin_LTLIBRARIES = libempty.la

libempty_la_SOURCES = cmd.c cmd.h utils.h utils.c module.c module.h

libempty_la_LDFLAGS = -avoid-version -module
libempty_la_LDFLAGS += $(LIBOTR_LIBS) $(LIBGCRYPT_LIBS) -lpthread

install-data-hook:
	chmod 644 $(DESTDIR)/$(plugindir)/irssi_emptylib.so
	rm $(DESTDIR)/$(plugindir)/irssi_emptylib.la

uninstall-hook:
	rm $(DESTDIR)/$(plugindir)/irssi_emptylib.so
