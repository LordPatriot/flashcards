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

## Asymmetric cryptography

* Public key known to everyone - anyone can encrypt messages and send it to you
* Private key is a secret and belongs to you - only you can decrypt messages using private key
* Algorithms - RSA, ECC

---

## RSA
* RSA is based on the difficulty of factoring large integers that are the product of two large prime numbers. Multiplying is easy, the reverse is hard
* Choose 2 primes - let's say 11 and 13, N = 143
* Compute totient function - F(N) = F(143) = F(11) * F(13) = 10 * 12 = 120
* Choose public key, let's say 7

---

# Algorithms

---

## Turing completeness

* conditional branching
* ability to change an arbitrary amount of memory

---

---

# Distributed systems

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

---

## Kubernetes

* Master - orchestrates everything
* Nodes - physical or virtual machines
* Kubectl - CLI for sending commands to master
* Deployment - creates & monitors instances of your service (need to specify container image and number of replicas)
* kubectl proxy will create an endpoint on your localhost to reach services without exposing them externally
* Pod - one or more app containers + shared resources
* Pods are fungible (interchangeable)
* Service - an abstraction which defines a logical set of Pods and a policy by which to access them