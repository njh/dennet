Dennet
======

Experiment into sending MQTT-SN packets on a multi-master, half-duplex RS-485 network.


Framing
-------

Src Address: 8-bits
Dest Address: 8-bits
Length: 8-bits
<data>
Checksum: 8-bits



Wiring
------

The T568A cable scheme is recommended.

| RJ-45 Pin  | T568A Colour | Description  |
| ---------- | ------------ | ------------ |
| 1          | white/green  | Power - +24v |
| 2          | green        | Power - +24v |
| 3          | white/orange | Ground       |
| 4          | blue         | Flow - A     |
| 5          | white/blue   | Flow - B     |
| 6          | orange       | Ground       |
| 7          | white/brown  | Return - A   |
| 8          | brown        | Return - B   |
