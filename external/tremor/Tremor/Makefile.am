AUTOMAKE_OPTIONS = foreign

INCLUDES = -I./

lib_LTLIBRARIES = libvorbisidec.la

libvorbisidec_la_SOURCES = mdct.c dsp.c info.c misc.c \
                        floor1.c floor0.c vorbisfile.c \
                        res012.c mapping0.c codebook.c \
			framing.c bitwise.c \
                        codebook.h misc.h mdct_lookup.h\
                        os.h mdct.h ivorbisfile.h lsp_lookup.h\
                        window_lookup.h floor_lookup.c \
                        codec_internal.h ogg.h \
			asm_arm.h ivorbiscodec.h
libvorbisidec_la_LDFLAGS = -version-info @V_LIB_CURRENT@:@V_LIB_REVISION@:@V_LIB_AGE@

EXTRA_PROGRAMS = ivorbisfile_example
CLEANFILES = $(EXTRA_PROGRAMS) $(lib_LTLIBRARIES)

ivorbisfile_example_SOURCES = ivorbisfile_example.c
ivorbisfile_example_LDFLAGS = -static 
ivorbisfile_example_LDADD = libvorbisidec.la

includedir = $(prefix)/include/tremor

include_HEADERS = ivorbiscodec.h ivorbisfile.h ogg.h os_types.h config_types.h

example:
	-ln -fs . vorbis
	$(MAKE) ivorbisfile_example

debug:
	$(MAKE) all CFLAGS="@DEBUG@"

profile:
	$(MAKE) all CFLAGS="@PROFILE@"
