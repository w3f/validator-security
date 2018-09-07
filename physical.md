## Overview
This section of the repo concerns the physical security of the node's hardware. Here we will collate information related to good practise for defending nodes against physical attacks. 

While many of the new projects have yet to launch, it is to be expected that most users will either run a validator node at home or on a Virtual Private Server (VPS) in the cloud. This ought to be fine for test networks, but once the networks have properly launched there are serious concerns about not properly securing the physical entity of the node. Personal homes, or even office spaces, tend not to have the highest levels of security. The use of a VPS ought to mitigate some concerns as the providers should ideally have their servers located in a secure data centre.

The likely norm for validator nodes will be to co-located in a datacentre, as they will provide 24/7 physical security via CCTV and human guards. In addition, they should provide a high level of connectivity which is a requirement for data availability guarantees.

why is such great importance being placed on physical security? The reason: there are signing keys held on the validator nodes. When the future networks are transacting billions of dollars every day it forces a great amount of responsibiltiy on the validator nodes to be secure.
