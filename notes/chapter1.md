# Chapter 1: Networks
[&larr; Back](/README.md)

## Networks
> A series of packet switches connected by communication links


## Host = End System
* Any interconnected device
    * ex. smartphone, pc
* **connects** via socket interface
* further delimination
    * client/server


## Physical Link Types
* Coaxial
* Copper wire
* Optical fiber
* Radio spectrum


## Packets
* messages broken up
* generally reconsctructed at end system


## Packet Switches
* Multiple forms
    * routers
        * generally at core of network
    * link-layer switches
        * used in access networks


## IP Protocol
* Format of the packet

## Distributed Applications
* Application running accross multiple computers
    * think cloud computing

## Protocol
* Defines the format and order of messages btw. entities

## Access Technologies

### DSL (Digital Subscriber Line)
* used telephone line
* translates bits to high freq. tones
* sends data to **DSLAM**
    * in telcos central office
    * data translated back to digital
    * within 5 - 10 miles of home
* **Downstream**
    * 50kHz to 1MHz
* **Upstream**
    * 4kHz to 50kHz
* Telephone Channel
    * 0 - 4kHz


### Cable Internet Access
* Same as cable provider
* **HFC** &rarr; Hybrid Fibre Coaxial
* Two assymetric channels
    * **Downstream**
        * Higher transmission rate
        * 40 Mbps &rarr; 1 Gbps
    * **Upstream**
        * 30Mbps &rarr; 100 Mbps

### FTTH (Fiber to the Home)
* Fibre from central office (**CO**) to home
* Multiple Gbps speeds
#### PON (Passive Optical Network)
* Each home has optical network termination
* connected via dedicated optical fiber to neighbourhood splitter
* around 100 homes connected onto a single shared optical fiber
* connects to **OLT** in **CO**
    * provides conversion between optical and electrial signals

### WiFi
* Wireless LAN based on IEEE 802.11

### Wide-Area Wireless Access
* range of 10km +


## Physical Mediums
* Send by propagating electromagnetic waves accross physical

### Two Types

#### Guided
* Fibre, coaxial, etc.
#### Unguided
* Waves propagate in the atmosphere

### Twisted Pair
* High speed LAN

### Coaxial Cable
* Concentric opposed to twisted
* Provides insulation &rarr; higher rates

### Fibre
* Pulses of light representing bits
* immune to electromagnetic interference

### Terrestrial Radio Channels
* No wires
* Penetrates walls
* Three ranges
    * 1m &rarr; 2m
    * 10 &rarr; 300m
    * 10km +

## Satellite Radio Channels
![sats](/assets/sats.png)


## OC Standard (OC-n)
* 1000mb = 1Gb
* link speed
    * n x 51.8Mbps
    * ex: OC-768 &rarr; 39782.4 Mbps ~ 39GBps
    
## Network Core (Math)

### Packet Switching
* breaks data down into packets
* Packets travel through:
    * packer switches
    * link-layer switches
    * routers

### Transfer Types

#### Store and Forward
* wait for whole packet to arrive
> $ Time_{end-to-end} = {NumRouters \times {Bits \over Bits/second}}$

## Queueing Delay
* Buffer
* Stored here if outgoing link busy
* Has finite space
* Buffer full &rarr; packet loss

## Packet Header
* Contains destination IP address
    * router forwards based on portion

## Circuit Switching