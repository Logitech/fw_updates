# Copyright (C) 2019 Logitech

VENDOR=Logitech
PROJECT_NAME=Powerplay
VERSION=RQR40.01_B0007
FIRMWARE_FILES=../RQR40.01_B0007.shex
METAINFO_FILES=com.logitech.RQR40.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
