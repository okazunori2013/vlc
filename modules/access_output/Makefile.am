access_outdir = $(pluginsdir)/access_output

libaccess_output_dummy_plugin_la_SOURCES = access_output/dummy.c
libaccess_output_file_plugin_la_SOURCES = access_output/file.c
libaccess_output_http_plugin_la_SOURCES = access_output/http.c

access_out_LTLIBRARIES = \
	libaccess_output_dummy_plugin.la \
	libaccess_output_file_plugin.la \
	libaccess_output_http_plugin.la

libaccess_output_livehttp_plugin_la_SOURCES = access_output/livehttp.c
libaccess_output_livehttp_plugin_la_CFLAGS = $(AM_CFLAGS) $(GCRYPT_CFLAGS)
libaccess_output_livehttp_plugin_la_LIBADD = $(GCRYPT_LIBS) $(LIBM)
if HAVE_GCRYPT
access_out_LTLIBRARIES += libaccess_output_livehttp_plugin.la
endif

libaccess_output_shout_plugin_la_SOURCES = access_output/shout.c
libaccess_output_shout_plugin_la_CPPFLAGS = $(AM_CPPFLAGS) $(SHOUT_CFLAGS)
libaccess_output_shout_plugin_la_LDFLAGS = $(AM_LDFLAGS) -rpath '$(access_outdir)'
libaccess_output_shout_plugin_la_LIBADD = $(SHOUT_LIBS) $(SOCKET_LIBS)
access_out_LTLIBRARIES += $(LTLIBaccess_output_shout)
EXTRA_LTLIBRARIES += libaccess_output_shout_plugin.la

libaccess_http_put_plugin_la_SOURCES = access_output/http-put.c
libaccess_http_put_plugin_la_CPPFLAGS = $(AM_CPPFLAGS) -I$(srcdir)/access/http
libaccess_http_put_plugin_la_LIBADD = libvlc_http.la
access_out_LTLIBRARIES += libaccess_http_put_plugin.la

### SRT ###
libaccess_output_srt_plugin_la_SOURCES = access_output/srt.c access/srt_common.c access/srt_common.h dummy.cpp
libaccess_output_srt_plugin_la_CFLAGS = $(AM_CFLAGS) $(SRT_CFLAGS)
libaccess_output_srt_plugin_la_CPPFLAGS = $(AM_CPPFLAGS) $(SRT_CPPFLAGS)
libaccess_output_srt_plugin_la_LIBADD = $(SRT_LIBS)
libaccess_output_srt_plugin_la_LDFLAGS = $(AM_LDFLAGS) -rpath '$(access_outdir)'
access_out_LTLIBRARIES += $(LTLIBaccess_output_srt)
EXTRA_LTLIBRARIES += libaccess_output_srt_plugin.la

### RIST ###

libaccess_output_rist_plugin_la_SOURCES = access_output/rist.c
libaccess_output_rist_plugin_la_CFLAGS = $(AM_CFLAGS) $(RIST_CFLAGS)
libaccess_output_rist_plugin_la_LIBADD = $(RIST_LIBS) $(SOCKET_LIBS)
libaccess_output_rist_plugin_la_LDFLAGS = $(AM_LDFLAGS) -rpath '$(access_outdir)'
access_out_LTLIBRARIES += $(LTLIBaccess_output_rist)
EXTRA_LTLIBRARIES += libaccess_output_rist_plugin.la
