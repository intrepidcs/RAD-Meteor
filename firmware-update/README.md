# Firmware Update

The RAD-Meteor supports a field update of firmware. This works on Linux, Windows and Mac.&#x20;

The current version of the firmware is shown on the [main screen](../display-main-screen/).

## Firmware Update Process

1\) Receive a UF2 FW file from [Intrepid support](https://intrepidcs.com/support/contact-support/)

2\) Hold boot load button and plug in USB. It is on the bottom of RAD-Meteor. Please see figure 1 below.

3\) The host computer will show RAD-Meteor as a flash drive

4\) Copy the UF2 file to the flash drive. Allow firmware to update.

5\) When done RAD-Meteor will disconnect from USB and reconnect as a USB NIC (normal operation)

**Note** If flash fails you can erase the flash using the nuke.uf2 file.  Just follow the above steps using the the nuke.uf2. Then re-flash with the RAD-Meteor UF2 file.

{% file src="../.gitbook/assets/flash_nuke.uf2" %}

<figure><img src="../.gitbook/assets/2022-10-05 14_15_36-Window.png" alt=""><figcaption><p>Figure 1 - The boot load button is on the bottom of RAD-Meteor</p></figcaption></figure>