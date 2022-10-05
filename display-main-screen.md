# Display: Main Screen

The default screen for RAD-Meteor shows statistics of the T1s network. Figure 1 below shows the main screen.

<figure><img src=".gitbook/assets/2022-10-05 13_11_28-Window.png" alt=""><figcaption><p>Figure 1 - The Main contains a lot of information about the T1s network.</p></figcaption></figure>

## Buttons

There are 3 function buttons on the main screen. They are below

"A" to Enter the [Test mode generation feature](10baset1s-test-modes.md)

"B"  to Enter the simulation mode feature

"X" to enter the device setup

##

## Device Setup Information

The first two lines of the display show the device's setup.

| Caption | Description                                                               | Notes |
| ------- | ------------------------------------------------------------------------- | ----- |
| PLCA EN | Indicates if the PLCA feature is enabled.                                 |       |
| ID      | This is the PLCA local id                                                 |       |
| TO      | Transmit Opportunity time in bit times                                    |       |
| Nodes   | Node count for network                                                    |       |
| Burst   | amount of bit times for consecutive frames in burst mode                  |       |
| Max     | for Burst how many frames allowed. 0 means burst is disabled              |       |
| MAC     | Lower 3 bytes of MAC address. The upper 3 bytes are Intrepid **00-FC-70** |       |
|         |                                                                           |       |

## Transmit and Receive Statistics

The display indicates statistics on numbers sent and received by the device. They are in the table below.

| Caption            | Description                                                                                                    | Notes                                                |
| ------------------ | -------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| Rx Count           | The number of frames received by RAD-Meteor                                                                    |                                                      |
| Tx Count           | The number of frames transmitted by RAD-Meteor                                                                 |                                                      |
| Logical Collisions | The number of transmits that were retried because of PLCA assertions of the COL (MII Collision Pin) indication | This is the normal function of PLCA and not an error |

## PHY Status Registers

The display shows information gathered by the PHY status registers. These items are detailed in the LAN867x data sheet from [Microchip](https://www.microchip.com). They are in the table below:

| Caption     | Description                                                                                                                                                                            | Notes                                                                                                                                                                                                                                                                                                                              |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PLCA Active | This field indicates that the PLCA reconciliation sublayer is active and a BEACON is being regularly transmitted or received.                                                          |                                                                                                                                                                                                                                                                                                                                    |
| Beacon      | This will flash when PHY beacon counter changes                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                    |
| EMPCYC      | This bit indicates an empty PLCA cycle                                                                                                                                                 | Common occurrence on a network that is not heavily loaded.                                                                                                                                                                                                                                                                         |
| TXCOL       | Physical collision on the network was detected                                                                                                                                         | Not a logical collision                                                                                                                                                                                                                                                                                                            |
| TXJAB       | This bit indicates the occurrence of a transmit jabber condition. A jabber condition occurs when the PHY detects that the PCS has remained in the transmit state longer than 2 ms.     |                                                                                                                                                                                                                                                                                                                                    |
| RXINTO      | This bit indicates the detection of another node transmitting in this node’s local assigned transmit opportunity. This could indicate multiple nodes being assigned the same Local ID. |                                                                                                                                                                                                                                                                                                                                    |
| UNEXPB      | When configured as the PLCA coordinator in charge of transmitting the periodic coordinating BEACONs, this bit indicates the detection of an unexpected BEACON on the segment.          | This condition may be due to the configuration of multiple PLCA coordinators on the segment.                                                                                                                                                                                                                                       |
| BCNBFTO     | This bit indicates the detection of a BEACON before the node’s assigned transmit opportunity.                                                                                          | This condition could indicate the configuration of multiple PLCA coordinators on the segment. Other conditions that may cause this to occur include a PLCA coordinator with an incorrectly configured maximum node count resulting in a PLCA cycle that is too short, or a PLCA Local ID that is configured beyond the PLCA cycle. |
| PLCASYM     | This bit indicates the detection of PLCA BEACON symbols when PLCA is not enabled.                                                                                                      | This condition may indicate the local node is operating with PLCA disabled on a segment with PLCA enabled nodes.                                                                                                                                                                                                                   |
| ESDERR      | This bit indicates the reception of an End-of-Stream Delimiter Error (ESDERR) or End-of-Stream Jabber (ESDJAB) symbol.                                                                 |                                                                                                                                                                                                                                                                                                                                    |
| DEC5B       | This bit indicates a 5B decoder encountered an unknown or reserved 5B codeword that could not be decoded.                                                                              |                                                                                                                                                                                                                                                                                                                                    |

## General Device information

The last line of the display indicates the firmware revision of RAD-Meteor and the USB connection status. (1 meaning connected)

