## Overview
This section of the repo concerns the physical security of the node's hardware. Here we will collate information related to good practise for defending nodes against physical attacks. 

While many of the new projects have yet to launch, it is to be expected that most users will attempt to run a validator node either at home or on a Virtual Private Server (VPS) in the cloud. This ought to be fine for test networks, but once the networks have properly launched there are serious concerns about not properly securing the physical entity of the node. Personal homes, or even office spaces, tend not to have the highest levels of security. The use of a VPS ought to mitigate some concerns as the providers should ideally have their servers located in a secure data centre, but it is less clear that they can offer a high enough level of seurity (or assurance there of).

Why is such great importance being placed on physical security? The reason: the validator nodes hold a copy of the signing keys. These are the keys used to signal that a valid block has been created. When the future networks are transacting billions of dollars every day it forces a great amount of responsibiltiy on the validator node owners. The nodes need to be secure, such that it is incredibly difficult to take get access to the servers.

# Location Types
## Co-location
The likely norm for validator nodes will be to co-located in a datacentre, as they will provide 24/7 physical security via CCTV and human guards. In addition, they should provide a high level of connectivity which is a requirement for data availability guarantees. There will also need to be considerations for power redundancy, data backups, and a good process about what to do when there is a failure. More discussion on operational security can be found here: [operational security](https://github.com/w3f/validator-security/blob/master/operational.md).

It is likely that hardware will need to be purchased by node operators (unlike with VPS providers). For some networks, this will be the only reasonable option.


## VPS
Choosing to purchase a VPS with one of the known big providers ought to be a cheaper option than the above, but there will be no control over the hardware itself. If you need access to the machine in order to plug in a hardware security module (HSM), then a VPS will not be a viable solution. 

For networks that don't necessarily require physical access to the machine then a VPS could be a consideration. It is still important to be aware that such providers make heavy (or exclusive use) of virtualised servers. Consequently, your validator node will be host on the same machine as other clients of the provider. While your instance is logically separated from the other instances, this does entail some additional risk. To avoid being on a multi-tenant machine you should check if the provider offers a 'bare metal' product.

The best VPS providers state that they take security seriously.


## Home server
Running a server at home will be sufficient for running a node on a test network, but it is unlikely to be sufficient for a live network. Caution is advised!

[Further details to be added]

# Physical Security Checklist
This is a non-exhaustive checklist of security considerations. These points should be considered when making a choice of server location and determining if the location will offer sufficient security. Given that phsysical security is outsourced when you colocate or use a VPS, the amount of depth provide here will only be at a surface level.

* 24/7 physical security guards.
* CCTV of the facility (internal and external).
* Operational management of security.
* Access restrictions to the facility (property).
* Access restrictions to the machines (even for those who can enter the property).
* Inconspicuous building.
* Sufficient cooling.
* Power redundancy.
* High throughput connectivity.


Any node operator who attempts to set up a dedicate facility for such facilities will require greater detail from a checklist. Naturally, we can draw upon standards (e.g. ISO27002) to seed such a list.
