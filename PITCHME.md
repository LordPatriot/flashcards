---

# Internet

---

## Delays
* Processing
* Queuing
* Transmission
* Propagation

---

## Processing delay
Time required to examine the packet's header and determine where to direct it

---

## Queuing delay
Time that the packet has to wait before it gets transmitted through the outgoing link

---

## Transmission delay
Time required to push all the packet's bytes into the link

---

## Transmission delay
* L (length in bits) / R (rate, bits/sec)
* Rate can be 10 Mbps and 100 Mbps

---

## Propagation delay
Time required to propagate from one end of the link to another

---

## Propagation delay
* Speed of propagation is 2-3 * 10<sup>8</sup> meters per second

---

## Layers
* Application (HTTP, FTP, SMTP)
* Transport (TCP, UDP) - transports application layer messages between application endpoints
* Network (IP) - gets a segment and a destionation address, contains routing protocols
* Link - facilitates node to node delivery along the route (Ethernet, WiFi etc)
* Physical - moves individual bits across a physical link

---

* Routers have Network layer
* Switches don't

---

## TCP
Breaks down application messages into segments, provides congestion control, establishes connections, guarantees delivery

---

## Types of networks

* curcuit switching (dedicated channel, telephone)
* packet switching (Internet)

---

## Linkerd (layer 5 proxy)

* Layer 5 proxy (HTTP and other protocols - Thrift, Mux, HTTP/2, gRPC)
* Request/response, not raw TCP packets
* Linkerd orients itself around concepts of request success/failure, latency (not possible with raw TCP packets)
* Service discovery (apps move around, proxy points to the correct location)
* Intelligent load-balancing beyond round robin (based on latency for instance)
* Can do retries
* Circuit breakers (stop sending requests to failing node)
* Metrics/tracing