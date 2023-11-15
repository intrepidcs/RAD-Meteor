# Device Release History

## Firmware Release Revision 22

### Notes:

1. **Version 20**: First Release.
2. **Version 21**: Fixes a bug where packet traffic at power up would cause the USB fifo to become un-syncronized. This would cause invalid messages to appear over USB (mostly zeros).
3. **Version 22**: Fixes a bug where Meteor would count frames larger than 1518 as CRC errors. Now its 1526 to support two VLAN tags.
