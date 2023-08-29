# Host USB Responses

## Overview

The RAD-Meteor can generate Ethernet frames that occur across the USB interface only. These responses allow the RAD-Meteor to communicate status to the host.  For example, these responses can provide additional information about the T1s network. For example the status message contains status information like on the [main screen](../display-main-screen/).

{% file src="../.gitbook/assets/RADMeteor (1).vs3" %}
Vehicle Spy Setup File to decode status messages
{% endfile %}

<figure><img src="../.gitbook/assets/vehicle_spy_status.png" alt=""><figcaption><p>Figure 1 - Analyzers like Vehicle Spy can decode Ethernet frame data such as the status message.</p></figcaption></figure>

## Responses

The data payload begins at 42 bytes. The first two bytes of the payload are the response id in big endian format (55 is the first byte).  The response's data begins right after the command (44 bytes). The table below lists the responses.

<table><thead><tr><th width="294">Response</th><th>ID</th><th>Notes</th></tr></thead><tbody><tr><td>HOST_RESPONSE_STATUS_ID</td><td>0x5501</td><td></td></tr></tbody></table>

## Status Response&#x20;

&#x20;The status response is sent on a interval when commanded by the [Settings command](./#settings-command). It contains device status such as PHY settings, Network statistics, and device performance.

<table><thead><tr><th width="483">Position</th><th width="72">ID</th><th>Encoding</th><th>Notes</th></tr></thead><tbody><tr><td>HOST_RESPONSE_STATUS_PLCA_ACTIVE</td><td>0</td><td>bit</td><td></td></tr><tr><td>HOST_RESPONSE_STATUS_PLCASTATUS1</td><td>1</td><td>little endian bitfield</td><td>See below</td></tr><tr><td>HOST_RESPONSE_STATUS_PLCASTATUS2</td><td>3</td><td></td><td>Not Implemented</td></tr><tr><td>HOST_RESPONSE_STATUS_PLCASTATUS3 </td><td>5</td><td></td><td>Not Implemented</td></tr><tr><td>HOST_RESPONSE_STATUS_BEACON_COUNT</td><td>7</td><td>uint32</td><td>Not Implemented</td></tr><tr><td>HOST_RESPONSE_STATUS_TX_OPPORTUNITY_CNT</td><td>11</td><td>uint32</td><td>Not Implemented</td></tr></tbody></table>

<figure><img src="../.gitbook/assets/plca_status_bits.png" alt=""><figcaption><p>Figure 2 - PLCA Status bits reported in status 1.</p></figcaption></figure>
