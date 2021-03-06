**BETaaS Project**
===================

BETaaS is a STREP Research project developed and co-funded by the European Commission Research and Innovation 7th Framework Program by the [BETaaS Consortium](http://www.betaas.eu/consortium.html#.VEeGuhZvAgk) under the ICT theme (Call 8) of DG CONNECT.

* BETaaS Framework Architecture
* Getting Started with BETaaS
* About BETaaS License


## BETaaS Architecture

BETaaS Instances are organized with an especial gateways architecture: a centralized and a distributed architecture. Even if this sounds a bit confusing or even contradictory, it makes sense to do it this way, in order to gain efficiency and robustness while we still provide flexibility and control over certain operations.
There are some operations, which require the intervention of a central component which will orchestrate certain interactions and decision making processes (what we call the star component). This is the case of some QoS management operations, when negotiating QoS conditions. It is also the case of the instances management process, in which we prefer to have only one access point which will avoid new gateways to request joining an instance by contacting several gateways at the same time (creating race conditions an
d potential inconsistencies related to the decision of accepting or rejecting the new gateway). Not performing some operations in a centralized way may increase the risk of certain attacks to the platform or just keep the instance in an inconsistent status.

<p style='color:red'>{WILL INSERT BETAAS THREE LAYER IMAGE HERE}.</p>

On the other hand, there are other operations which do not require a concrete component to orchestrate any process, since they may be performed through direct interactions. Facilitating a distributed execution of these operations is good for the instance, since we may gain in efficiency, avoid bottlenecks, store the instance status in a distributed manner and avoid inconsistencies because of components keeping a different point of view about the instance. This is the case, for example, of the resources synchronization and registration in an instance, which is performed in a distributed way, being the corresponding component responsible of broadcasting any change in the list of known resources, so all the gateways will be aware of the new situation.

The three layers of BETaaS are:

* BETaaS adaptation layer
* BETaaS TaaS(Thing as a Service) layer
* BETaaS Service Layer

Details about architecture are available [here](http://www.betaas.eu/docs/deliverables/BETaaS%20-%20D3.1.2%20BETaaS%20Architecture%20v1.0.pdf)



#### BETaaS Adaptation Layer

Adaptation layer offer the following capabilities to BETaaS:

The Adaptation Layer aims at providing a common interface to the TaaS layer regardless of the underlying IoT/M2M system. Through this common set of APIs, the TaaS can access the functionalities offered by any IoT/M2M system in a uniform manner.
The Adaptation Layer relies on a set of basic functionalities which are assumed to be provided by the Physical Layer.
For each IoT/M2M system which is integrated in BETaaS, a specific implementation of the Adaptation Layer has to be provided through a plugin. Nevertheless, the Adaptation Layer exposes a uniform set of functionalities to the TaaS layer. A BETaaS gateway can run different instances of the Adaptation Layers concurrently to interconnect to different local IoT/M2M systems. 

More specific details of the adaptation layer structure can be found  <font style='color:red'>(LINK goes here).</font>

#### BETaaS TaaS Layer

TaaS enables the service layer to access things as a service.
TaaS is implemented in a distributed manner: each gateway implements a TaaS local component which connects to the others to provide access to the things transparently regardless of their location in the network. A service requiring access to one thing, interacts with its TaaS local component, the unique interface towards the things. The local component is then responsible for accessing the thing through its own Adaptation Layer, if the thing is connected to the local network, or for requesting the service to the TaaS local component of the gateway where the thing is connected. The interconnection of all the TaaS local components forms an overlay which allows services to access the things regardless of their physical location through its local component which is a single point of access 

More specific details of the adaptation layer can be found <font style='color:red'>(LINK goes here).</font>

#### BETaaS Service Layer

The Service Layer is built on top of TaaS: it provides services to applications leveraging on the things accessed through the TaaS. The Service layer implements the basic and extended capabilities of the BETaaS platform. The abstraction provided by TaaS allows services to access the things as they were connected the local gateway without have knowledge of their physical location. 

More specific details of the adaptation layer can be found <p style='color:red'>(LINK goes here).</p>

## Getting Started with BETaaS:

In order to star developing or deploying BETaaS two guides are provided:

* Setup and deployment of BETaaS <font style='color:red'>(LINK goes here).</font>

## BETaaS Examples:

Additionally the following examples are provided:

* How to build an adapter for BETaaS <font style='color:red'>(LINK goes here).</font>
* How to build a BETaaS application <font style='color:red'>(LINK goes here).</font>

###** About BETaaS Project**

#### ** About BETaaS Software License**

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software  distributed under the License is distributed on an "AS IS" BASIS,  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the License for the specific language governing permissions and  limitations under the License.


2014 All Rights Reserved by [BETaaS Project](www.BETaaS.eu)
