fw_updates
==========

This repository contains official FW update files for Logitech control devices
(mice, keyboards, etc.)


UUID generation
---------------

The LVFS meta-data define a universally unique identifier (UUID) for each
product, as the tag `<firmware type="flashed">` within `<provides>`.

This identifier is an [RCF4122](https://tools.ietf.org/html/rfc4122) version 5
UUID, generated using the DNS name-space and the string:

    `USB\VID_046D&PID_xxxx`   (USB devices and receivers)

or

    `UFY\VID_046D&PID_xxxx`   (Unifying devices)

Where `xxxx` is the USB or Unifying product identifier (PID).

Several tools exist to generate RCF4122 UUIDs.  For example, in Pyython:

   `#! /usr/bin/python` \
   `import uuid` \
   `print uuid.uuid5(uuid.NAMESPACE_DNS, 'UFY\VID_046D&PID_xxxx')`

or, using the command-line `uuid` program:

   `uuid -v 5 'ns:DNS' 'UFY\VID_046D&PID_xxxx'`
