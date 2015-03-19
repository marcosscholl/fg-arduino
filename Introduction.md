## Simulator ##
  * The FlightGear simulator runs as an "instance" on a machine
  * FlightGear internally uses a property tree to relate parts to each other
  * The flight dynamics model (FDM) provides these readable values
  * various interfaces interact with the instance
  * Controls move the surfaces within the FDM
  * All values are exposed and manipulated via the property tree
  * the PropertyTree is FlightGear has many nodes
  * similar to a file system its eg /acontrols[0](0.md).engine!" (TBA)

## Interface ##
There are a few ways to interface with FlightGear but there can be summaries as:
MultiPlayer In/Out Multiplayer
Socket Reads - ie reading values from flightgear
SocketWrites - pushing into into the FDM
Telnet - R/W

## Generic Protocol ##
**The "Generic Protocol" is a way of sending FlightGear values to an output:**


##  ##