include ../Makefile.param

# target
TARGET := sample_adec

# target source
SRC := sample_adec.c

# header
INC := -I.\
    -I/usr/include/mpp/system/include \
    -I/usr/include/mpp/middleware/include/utils \
    -I/usr/include/mpp/middleware/include/media \
    -I/usr/include/mpp/middleware/include \
    -I/usr/include/mpp/middleware/media/include/utils \
    -I/usr/include/mpp/middleware/media/include/component \
    -I/usr/include/mpp/middleware/media/LIBRARY/libcedarx/libcore/common/iniparser \
    -I/usr/include/mpp/middleware/sample/configfileparser

# share libraries
LIBS := \
    -llog \
    -lsample_confparser \
    -lmedia_utils \
    -lmedia_mpp \

CFLAGS += $(INC)

OBJS := $(SRC:%.c=%.o)

.PHONY: all
all: $(OBJS) $(TARGET)

%.o: %.c
	@$(if $(strip $(Q)), echo '  CC    $@')
	$(Q)$(CC) $(CFLAGS) -c -o $@ $<

$(TARGET): $(OBJS)
	@$(if $(strip $(Q)), echo '  LD    $@')
	$(Q)$(CC) $(LDFLAGS) $(OBJS) $(LIBS) -o $@
	@$(if $(strip $(Q)), echo '  STRIP $@')
	$(Q)$(STRIP) $@

.PHONY: clean
clean:
	-rm -f $(TARGET) $(OBJS)
