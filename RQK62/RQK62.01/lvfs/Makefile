# Copyright (C) 2017 Logitech

VENDOR=Logitech
PROJECT_NAME=K830
VERSION=RQK62.01_B0015
FIRMWARE_FILES=../RQK62.01_B0015.dfu
METAINFO_FILES=com.logitech.RQK62.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
