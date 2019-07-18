# Copyright (C) 2019 Logitech

VENDOR=Logitech
PROJECT_NAME=Lightspeed
VERSION=RQR39.05_B0040
FIRMWARE_FILES=../RQR39.05_B0040.hex
METAINFO_FILES=com.logitech.RQR39.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
