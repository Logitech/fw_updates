# Copyright (C) 2017 Logitech

VENDOR=Logitech
PROJECT_NAME=K400_Plus
VERSION=RQK63.02_B0016
FIRMWARE_FILES=../RQK63.02_B0016.dfu
METAINFO_FILES=com.logitech.RQK63.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
