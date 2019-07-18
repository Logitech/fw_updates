# Copyright (C) 2019 Logitech

VENDOR=Logitech
PROJECT_NAME=R500_Receiver
VERSION=RQR45.01_B0005
FIRMWARE_FILES=../RQR45.01_B0005.shex
METAINFO_FILES=com.logitech.RQR45.metainfo.xml

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ $(FIRMWARE_FILES) $(METAINFO_FILES)
