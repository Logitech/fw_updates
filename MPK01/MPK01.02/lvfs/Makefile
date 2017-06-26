# Copyright (C) 2017 Logitech

VENDOR=Logitech
PROJECT_NAME=K780
VERSION=MPK01.02_B0021
FIRMWARE_FILES=../MPK01.02_B0021.dfu
METAINFO_FILES=com.logitech.MPK01.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
