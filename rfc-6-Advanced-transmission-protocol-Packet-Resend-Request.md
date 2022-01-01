Advanced transmission protocol Packet Resend Request (APRR)

#### Note 1:
This protocol is designed to be used in conjunction with and depends on
several other protocols. We recommend that you read and understand RFC 5 
and RFC 1 before reading this RFCso that you have all of the nescicary background 
information.


# Introduction

## Terminology

### ATP
**Advanced Transmission Protocol**, Designed for sending and receiving many catnet packets. ATP is used for direct connections
where having no data loss or corruption is important. See RFC 5 for more information.

### CNMP
**Catnet Non-Application Message Protocol**, Designed for small messages that are not realavent to the end user but may be
needed for internal functionality. Most commonly, these messages will be error reports, key information, or requests. See RFC ? for more information.


## Motivation
The APRR protocol simply reports the validity of incoming Catnet Protocol packets sent via *ATP*. Upon 
recieving a packet and calculating its checksum, Catnet will use APRR to send a small message over *CNMP* to 
the origin of the packet, indicating weather a valid packet was recieved and, if nescicary, requesting a re-send of the packet.

## Scope
APRR runs below *CP* and is facilitated by *CNMP*. CNMP is designed for sending small and simple messages that end users are not (usually) 
immediately concerned with and do not need all of the overhead or extra features of CP. As APRR sends such simple information, CNMP is all
that is necessary to faclilitate it.

## Interface
APRR will send all of its messages over CNMP and will be fed information by the *Catnet Module.* APRR messages will be sent between all members of the catnet network,
as is is key to ensuring integrity and stability.





# Authors

Eli Hatton