# Using in Vehicle Spy

## Overview

Vehicle Spy from Intrepid contains many features for analyzing Ethernet networks that exceed that of Wireshark. This includes being able to transmit ethernet frames, scripting, simulate ECUs and gateways, and decode protocols with OEM databases.

<figure><img src="../.gitbook/assets/vehicle_spy_status.png" alt=""><figcaption><p>Figure 1 -  Vehicle Spy software for transmit and receiving Ethernet.</p></figcaption></figure>

{% file src="../.gitbook/assets/RADMeteor.vs3" %}
Setup file for Vehicle Spy 3
{% endfile %}

## Setting up Vehicle Spy

First it is recommended to give your RAD-Meteor a custom name. This is described in the [Windows setup](./) topic.

Vehicle Spy is licensed software. To use Vehicle Spy with RAD-Meteor, you must have a licensed hardware such as Value-CAN or neoVI.&#x20;

To use RAD-Meteor you must enable Ethernet NIC support inside Vehicle Spy. Enter the options dialog from the Tools drop down menu. Then select the check box: "Use PC Ethernet interface" (Figure 1).

<figure><img src="../.gitbook/assets/VSPYSetup.png" alt=""><figcaption><p>Figure 1 - You must enable the Ethernet NIC feature of Vehicle Spy to use a RAD-Meteor</p></figcaption></figure>

Next you have to enable the correct NIC from the logon screen. The Ethernet interfaces are listed in the lower left corner (Figure 2). You can only connect to one Ethernet NIC at a time.

<figure><img src="../.gitbook/assets/met-in-vspy.png" alt=""><figcaption><p>Figure 2 - Here the RAD-Meteor "Met with Screen" is selected.</p></figcaption></figure>
