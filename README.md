fw_updates
==========

This repository contains official FW update files for Logitech control devices
(mice, keyboards, etc.)


UUID generation
---------------

A universally unique identifier (UUID) is contained in the LVFS meta-data for
each product, as the tag `<firmware type="flashed">` within `<provides>`.

This identifier is an [RCF4122][1] version 5 UUID, generated using the DNS
name-space and the string:

    USB\VID_046D&PID_xxxx (USB devices and receivers)

or

    UFY\VID_046D&PID_xxxx (Unifying devices)

Where `xxxx` is the USB or Unifying product identifier (PID).

Several tools exist to generate [RCF4122][1] UUIDs. For example, in Python:

```python
#!/usr/bin/python
import uuid
print uuid.uuid5(uuid.NAMESPACE_DNS, 'UFY\VID_046D&PID_xxxx')
```

Using the command-line `uuid` program:

    uuid -v 5 'ns:DNS' 'UFY\VID_046D&PID_xxxx'

Or, using the `appstream-util` tool:

    appstream-util generate-guid 'UFY\VID_046D&PID_xxxx'

[1]: https://tools.ietf.org/html/rfc4122
