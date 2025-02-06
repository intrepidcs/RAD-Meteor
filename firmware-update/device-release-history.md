# Device Release History

## Firmware Release Revision 22

### Notes:

1. **Version 20**: First Release.
2. **Version 21**: Fixes a bug where packet traffic at power up would cause the USB fifo to become un-syncronized. This would cause invalid messages to appear over USB (mostly zeros).
3. **Version 22**: Fixes a bug where Meteor would count frames larger than 1518 as CRC errors. Now it's 1526 to support two VLAN tags. Documentation updated with the production meteor graphics.
4. **Version 23** - Internal Release.
5. **Version 24** - Internal Release.
6. **Version 25** - Fix FCS CRC on frames that get padded up to 60 bytes.
