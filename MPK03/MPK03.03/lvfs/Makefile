# Copyright (C) 2019 Logitech

VENDOR=Logitech
PROJECT_NAME=K370s_K375s
VERSION=MPK03.03_B0013
FIRMWARE_FILES=../MPK03.03_B0013.dfu
METAINFO_FILES=com.logitech.MPK03.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
