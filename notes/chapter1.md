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
> $$1,000mb = 1Gb = 1,000,000kbps (million)$$ 
* link speed
    * n x 51.8Mbps
    * ex: OC-768 &rarr; 39782.4 Mbps ~ 39GBps
    
## Network Core (Math)

## Packet Switching
* breaks data down into packets
* No guarantee of delivery (packet loss)
* Packets travel through:
    * packer switches
    * link-layer switches
    * routers

### Example
> Users share 1 Mbps link. Suppose each user alternates periods of activity. Active is 100mbps. Inactive is 0 Mbps. User is active 10% of the time.
> 100Mbps 10% of the time &rarr; 100 kbps reserved at all times.
> Circuit switched TDM with 10 time slots &rarr; 100ms per frame.
> Can only support  $$ 10 = {{1 Mbps}\over {100 kbps} } \; users $$

### Channel Noise
* Symbols being misinterpreted

### Baud and Bits
* 300 b/s = 0.3kBps = 300 baud

## Nyquists theorem
> * specifies the maximum data rate over a noiseless channel
> $$ 2Hlog_2V \; bps $$
---
> Key<br/>
> H: Channel Bandwidth <br/>
> V: # of different kinds of symbols <br/>
> S: Signal <br/>
> N: noise <br/>
> S/N: Signal-to-noise ratio (**SNR**)

## Shannon theorem
> maximum data rate over noisy channel
> $$ Hlog_2(1+{S \over N}) \; bps$$
---
### Transfer Types

#### Store and Forward
* wait for whole packet to arrive
> $$ Time_{end-to-end} = {NumRouters \times {Bits \over Bits/second}} $$

## Queueing Delay
* Buffer
* Stored here if outgoing link busy
* Has finite space
* Buffer full &rarr; packet loss

## Packet Header
* Contains destination IP address
    * router forwards based on portion

## Circuit Switching
* Communication between end systems reserved for duration of session
    * Think telephone call
* Reserves one circuit between two links
* **Benefits** include: guaranteed constant data transfer rate
* **Silent periods** are wasted resources (time there is no data being sent)

### Example
> Q. How long to send a file of 640,000 bits from host A to B over circuit switched networ. Using TDM, 24 slotsm bit rate of 1.536Mbps. 500 msec to establish end-to-end circuit before host A can transfer.

> A. Each circuit (host &rarr; host) connected has $$ {{1.536 Mbps}/{24}} = 64 kbps $$
> $$ {640,000 \over 64 kbps} = { 640,000 \over 64,000 bps } = 10 seconds $$ 
> $$ 10 seconds + 500 ms = 10.5 seconds $$

## Multiplexing in Circuit-Switched

### FDM (Frequency-Division Multiplexing)
* Frequency spectrum divided up among connections
* Typical Bandwidth &rarr; 4kHz
> $$ 4kHz == 4000Hz == 4000 {Cycles/second} $$
* Each circuit gets a fraction of resources
![FDM](/assets/FDM.png)
e
### TDM (Time-Division Multiplexing)
* Time divided into frames &rarr; each frame divided into fixed number of time slots
* When connection established across link network dedicates a time slot in each frame
* Each circuit gets all the bandwidth for short time
![TDM and FDM](/assets/TDMFDM.png)

### ISP Hierarchy 
* access ISP pays &rarr; regional ISP pays &rarr; tier-1 ISP
![networks](/assets/networkconnect.png)

## Types of Delay

### Processing Delay
* Time required to process header
* Where to direct packet
* Check bit level errors
* **FAST** microseconds

### Queueing Delay
* Time at router to pushed onto link
* ** ZERO ** if queue empty
* microseconds to milliseconds

### Transmission Delay
* Time to push out packet (all bits) onto the link
> $$ {Bits}\over {Bits/Second} $$

### Propogation Delay
* Time to propogate from router A to router B.
* Propogation Speed &rarr; Depends on physical medium of the link
> $$ Distance \over Propogation Speed $$
* **Longer**, takes ms.

## Sending Packet Time
* How long send 3 packets?
* L = # Bits, N = # of links, R = Rate (speed)

1. Time: 0 (Packet is send from source to router/switch)
2. Time: L/R (Packet received in full at router/switch - Starts to now transmit)
3. Time: 2(L/R) (Router transmitted the entire packet to the destination) [Packet 1]
4.Time: 3(L/R) (Router transmitted the entire packet to the destination) [Packet 2]
5.Time: 4(L/R) (Router transmitted the entire packet to the destination) [Packet 3]
6. Done.

* Observed, it takes:
$$ (NumLinks+1) \times {NumBits \over Bitrate} $$

## Traffic Density
* Average amount of incoming bits > Rate at which bits can be transmitted
    * Results in **traffic density** > 1 &rarr; Queue increase without bound


## Traceroute
![trace](/assets/trace.png)
* First Column &rarr; Number of router along route
* Second Column &rarr; Name of router
* Third Column &rarr; Address of router
* 4/5/6 Column &rarr; 3 Seperate experiments

## Throughput

### Instantaneous
* Rate at any time in bits/second
### Average
$$ F bits \over T bits/sec $$

### Link Bottlenecks
* Link is bottlenecked by throughput of the slowest link
    * If link from server &rarr; router is less than link from router &rarr; client, server &rarr; router is the bottleneck.
* **Throughput** is the min of the slowest link.
    * Typically the access network.

### Example
> Suppose R_s = 2Mbps, R_c = 1 Mbps, R = 5Mbps. Common link divides evenly.
> $$ {R \over 10} = 500Kbps $$
> 500 Kbps bottlenecks other speeds

## Layering
![planex](/assets/planex.png)
* Makes it slower but more modular
    * Change individual components without affecting larger system
    * Easier to update

### Basics
* Each layer utilizes layer prior
* All various layers &rarr; protocol stack

### Application Layer
* Many protocols ex. HTTP
* Translation of Domain using DNS to IP

### Transport Layer
* TCP
    * Connection oriented
    * Guaranteed delivery of application layer messages
    * Breaks long message into shorter
    * Congestion control
* UDP
    * Connectionless
    * No flow control
    * No congestion control

### Network Layer
* Responsible for moving packets known as **datagrams**
* Service for deliverying to transport layer
* IP Protocol

### Link Layer
* Routes diagrams through series of routers
* Link layer passed to network layer at arrival
    * ex. Ethernet, WiFi, cable
* Can be handled by different link-layer protocls at different routers
* link-layer packets = **frames**

### Physical Layer
* Move individual bits
* Depends on medium of link

![links](/assets/links.png)

### Implementation of Layers
* Hosts implement all 5 layers
* link-layer switches implement layer 1 and 2
* routers implement layers 1 - 3

## DoS Attacks

### Vulnerability
* Few well crafted packets
### Bandwidth flooding
* So many packets the link becomes clogged
### Connection Flooding
* Large number of half-open TCP connections
    * Stops accepting legit ones
### Distribued DoS (DDoS)
* Attack comes from multiple sources
    * Can't block
### Packet Sniffer
* Can look at or copy packets
* Could be planted in a router/access link
* Don't inject new packets
    * hard to detect
* Best **defense** is cryptography
### IP Spoofing
* Injecting packets from false locaiton
* end-point authentication solves by determining where message originates