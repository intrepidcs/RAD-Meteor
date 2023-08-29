# Host USB Commands

**NOTE : This topic may change significantly based on further review and testing.**

## Overview

The RAD-Meteor has the ability to receive commands over the normal Ethernet data stream. RAD-Meteor will intercept host messages targeted to the MAC Address **00:FC:70:1C:00:00.** These Ethernet frames are processed by RAD-Meteor and discarded (they are not sent on the T1s bus).

Similarly RAD-Meteor will send responses or status using this same mac address.

Please see the RAD-Meteor settings project on GitHub to use as an example app (Figure 1).&#x20;

## Settings App Example

The RAD Meteor example settings app is an open source app from Intrepid. The Windows App is below. You need to install [WinPCAP ](https://www.winpcap.org/install/)for this to work.

{% file src="../.gitbook/assets/RADMeteorSettingsV3.zip" %}
Example Windows Console app to change settings
{% endfile %}

<figure><img src="../.gitbook/assets/settings_app.png" alt=""><figcaption><p>Figure 1 - The settings example is a winpcap application that sends the settings host command.</p></figcaption></figure>

## Commands

The data payload begins at 42 bytes. The first two bytes of the payload are the command in big endian format (AA is the first byte).  The command's data begins right after the command (44 bytes). The table below lists the commands.&#x20;

<table><thead><tr><th width="344">Command</th><th width="182">ID</th><th>Notes</th></tr></thead><tbody><tr><td>HOST_COMMAND_SET_SETTINGS</td><td>0xAA01</td><td></td></tr></tbody></table>

## Settings Command

The settings command allows you to set the device settings from the host. You can optionally have them saved as the power up default. The settings example app uses this command - please reference this app for an example. The settings are the same as described in the [Main Screen topic](../display-main-screen/).

The payload bytes not used should be set to zero for future compatibility.

**Note** The defaults are stored in flash memory and are not meant to be updated 1000's times a day as might happen in a tester application. So do not save settings to flash if its not necessary. The flash typical endurance is 100k writes.

**Command: 0xAA01**

**Data**

<table><thead><tr><th width="437">Position</th><th width="74">ID</th><th>Notes</th></tr></thead><tbody><tr><td>HOST_SETTING_PLCA_ENABLE</td><td>0</td><td>1 to enable, 0 Disable</td></tr><tr><td>HOST_SETTING_PLCA_LOCAL_ID</td><td>1</td><td></td></tr><tr><td>HOST_SETTING_BUS_NODE_COUNT</td><td>2</td><td></td></tr><tr><td>HOST_SETTING_MAX_BURST_CNT</td><td>3</td><td></td></tr><tr><td>HOST_SETTING_BURST_TIMER</td><td>4</td><td></td></tr><tr><td>HOST_SETTING_TX_OPP_TMR</td><td>5</td><td></td></tr><tr><td>HOST_SETTING_TEST_MODE</td><td>6</td><td>0 = enter normal mode, 1-4 = <a href="../10baset1s-test-modes.md">Test Modes</a> (Not saved in flash as default)</td></tr><tr><td>HOST_SETTING_STATUS_INTERVAL_LSB</td><td>7</td><td>Bytes 7 and 8 are 16 bit value for reporting register status in milliseconds. 0 = disabled</td></tr><tr><td>HOST_SETTING_SAVE_SETTINGS_TO_FLASH</td><td>9</td><td>1 = update as power up defaults, 0 = do not update. </td></tr><tr><td>HOST_SETTING_OSCOPE_TRIGGER</td><td>10</td><td>0 = disabled, <a href="../oscilloscope-trigger.md">x is scope trigger</a></td></tr></tbody></table>

