Dennet
======

Experiment into sending MQTT-SN packets on a multi-master, half-duplex RS-485 network.


Framing
-------

```
Src Address: 8-bits
Dest Address: 8-bits
Length: 8-bits
<data>
Checksum: 8-bits
```


Wiring
------

![Pinout diagram](https://github.com/njh/dennet/raw/master/rj45-dennet.png)

The T568A cable scheme is recommended.

| RJ-45 Pin  | T568A Colour | Description  |
| ---------- | ------------ | ------------ |
| 1          | white/green  | Power: +24v  |
| 2          | green        | Power: +24v  |
| 3          | white/orange | Ground       |
| 4          | blue         | Flow: A      |
| 5          | white/blue   | Flow: B      |
| 6          | orange       | Ground       |
| 7          | white/brown  | Return: A    |
| 8          | brown        | Return: B    |

By having two pairs of RS-485 signals on each cable, it allows us to create a physical 
network with a star topology, but in which electrically it is still a bus topology,
which is what RS-485 requires.


### Gateway

The gateway (node 0) is at both the beginning and end of the RS-485 bus.
The RS-485 transceiver should be connected to Flow A and B.
A 100 Ω termination resistor should be connected to Return A and B.

### Nodes

Other nodes should connect Flow and Return together, close to the RS-485 transceiver.

### Hubs

Hubs are passive devices that chain a series of ports together, so that the Return of one port is connected to the Flow of the next port.

Any unused ports will require a RJ-45 plug connected into them, which connects Flow A to Return A and Flow B and Return B together.
