# Copyright (C) 2017 Richard Hughes <richard@hughsie.com>

VENDOR=Logitech
PROJECT_NAME=Unifying
VERSION=RQR24.03_B0027
FIRMWARE_FILES=../RQR24.03_B0027.hex
METAINFO_FILES=com.logitech.Unifying.RQR24.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
