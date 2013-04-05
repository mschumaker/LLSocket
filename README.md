LLSocket
========
A low level socket api that makes it easy to share data between C#, Java and other languages.  Built on top of TCP/IP it takes some of the pain out of socket level programming.

On the Wire Protocol
====================

Step 1. Version handshake
-------------------------
64 Bits Total

[LLSocket Protocol Version, 32 bits][Application Protocol Version, 32 bits]

Step 2. Version Ack or Nack
---------------------------
[Ack, 8 bits = 1]

[Nack, 8 bites = 0]

In the case of a Nack by either side, the connection is closed 

Step 3. Commence Data
---------------------
Data packet sizes are limited to signed 32 bit integer in size or 2147483647 bytes
Data Format

[Channel Id, 8 bits][Payload Size, 32 bits][Payload]


