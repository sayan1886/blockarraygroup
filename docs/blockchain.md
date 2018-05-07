# Blockchain Specifications 

Designing both a performant and scalable blockchain requires drawing on various disciplines, from computer science to business administration. Creating a network that enhances the benefits of using a blockchain is typically focused on various criteria involving benchmarking. Performance has been shown not to be a barrier for adoption by businesses, but rather the lack of applications, adherence to industry standards, and consideration of business-wide impact of certain actives (i.e. accounting implications that arise from the use of cryptocurrencies). 


> “Differences in performance between chains are usually almost entirely due to differences in the protocols and the implementations, not the consensus algorithm”
> Go Ethereum pg. 8


## Requirements 

Our requirements list:


- Adoption of Industry Standards/Compliance with Standards 
  - PCI DSS, FIPS, ISO Standards
- Easy Key Management 
- Ability for 100% Privacy
- Ability for determinism in state (no hard-forking)
- Ability to withstand off-chain attack vectors, e.g.:
  - Bribery
  - Cartel Forming
- Ability to withstand on-chain attack vectors, e.g.:
  - 51% Attack
  - Refusal to Participate
  - Sybil Attack
- Reduce the use of cryptocurrency to a bare minimum 
- Adherence to Strict Data Retention and Privacy policies (e.g. GDPR)
- Multiple Security Audits by outside Firms
- Contract outside Security Firms at the designing and conception phase of products
- Rigorous pilot study with large enough sample size 
- Multiple testing phases with different user base
- Create a Blockchain Network Management Plan that documents design, development, distribution, deployment, maintenance, and end-of-life procedures for any network service

<paragraph >


## Model


- Assets - Asset definitions enable the exchange of almost anything with monetary value over the network, from whole foods to antique cars to currency futures.
- Chaincode - Chaincode execution is partitioned from transaction ordering, limiting the required levels of trust and verification across node types, and optimizing network scalability and performance.
- Ledger Features - The immutable, shared ledger encodes the entire transaction history for each channel and includes SQL-like query capability for efficient auditing and dispute resolution.
- Privacy through Channels - Channels enable multi-lateral transactions with the high degrees of privacy and confidentiality required by competing businesses and regulated industries that exchange assets on a common network.
- Security & Membership Services - Permissioned membership provides a trusted blockchain network, where participants know that all transactions can be detected and traced by authorized regulators and auditors.
- Consensus -a Byzantine Fault Tolerant (BFT) consensus protocol, PBFT or RBFT.

### Architecture

#### Blocks

|                    Block                   |
|:------------------------------------------:|
|       Header (hash of previous block)      |
|        Block Number (vBlock Number)        |
| Transactions (valid transactions commited) |

More specifically, every block of a validated ledger contains:
• The hash of the previous vBlock.
• vBlock number.
• An ordered list of all valid transactions committed by the peers since the last vBlock was computed (i.e., list of valid transactions in a corresponding block).
• The hash of the corresponding block (in PeerLedger) from which the current vBlock is derived.
All this information is concatenated and hashed by a peer, producing the hash of the vBlock in the validated ledger.

#### Channels

A **channel** is a private “subnet” of communication between two or more specific network members, for the purpose of conducting private and confidential transactions. A channel is defined by members (organizations), anchor peers per member, the shared ledger, chaincode application(s) and the ordering service node(s). Each transac- tion on the network is executed on a channel, where each party must be authenticated and authorized to transact on that channel. Each peer that joins a channel, has its own identity given by a membership services provider (MSP), which authenticates each peer to its channel peers and services.

To create a new channel, the client SDK calls configuration system chaincode and references properties such as an- chor peers, and members (organizations). This request creates a genesis block for the channel ledger, which stores configuration information about the channel policies, members and anchor peers. When adding a new member to an existing channel, either this genesis block, or if applicable, a more recent reconfiguration block, is shared with the new member.

## Design Considerations: Creating a High-Performance Blockchain

Conducting an industry-wide search of the literature on creating a performant blockchain network has yielded several specifications on achieving a **high performing**, **scalable**, **secure**, and **robust** blockchain network.


Integrate oft-used Applications 
most frequently used smart contracts should be supported natively by the blockchain, leaving only the rarely-used custom contracts to run in a virtual machine. 

Avoid Hashes, Assign IDs Instead


**Transaction Size**

Transaction Size (bytes) X Transactions Processed (seconds)
becomes clear that transaction size directly impacts the block interval, and therefore the confirmation latency.


## Implementation 

Differences between standard Hyperledger Fabric Deployment 

Block Explorer
  The Block Explorer we are using has been created from the ground up in-house. It focuses on serving *Fabric* blockchains as opposed to trying to serve many different blockchains, which is the case with the Hyperledger Explorer Project.


Gossip Protocol
Consensus Protocol 
State Database
Data Storage
Account Identifiers  



### Tendermint


### RBFT 

As described in their paper, existing BFT protocols use a special replica, called the "primary", which indicates to other replicas the order in which requests should be processed. This primary can be smartly malicious and degrade the performance of the system without being detected by correct replicas. Our evaluation shows that RBFT achieves similar performance as the most robust protocols when there is no failure and that, under faults, its maximum performance degradation is about 3%, whereas it is, at least, equal to 78% for existing protocols."

RBFT implements a new approach whereby multiple instances of the protocol run simultaneously, a Master instance, and one or more Backup instances. All the instances order the requests, but only the requests ordered by the Master instance are actually executed. All nodes monitor the Master and compare its performance with that of the Backup instances. If the Master does not perform acceptably, it is considered malicious and replaced.



### Gossip Protocol

RAET: Reliable Asynchronous Event Transport Protocol, a high-performance, fault-tolerant communications protocol on top of UDP. RAET leverages Curve25519, a highly-secure high-performance elliptic curve.

RAET is designed to provide secure reliable scalable asynchronous message/event transport over the internet in a micro-threaded multi-process application framework that uses UDP for interhost communication and LibSodium for authentication, encryption and the CurveCP handshake for secure bootstrap.

The queue management and micro-threaded application support is provided by Ioflo. RAET is a complementary project to Ioflo in that RAET enables multiple Ioflo applications to work together over a network as part of a distributed application.


Instead of using Message Authentication Codes, every communication is digitally signed using Curve25519.
While MAC authenticators are computationally less expensive to verify than digital signatures, we feel that given the foreseeable protocol applications today, the security trade-offs of using MACs would be too high.

> For more Information visit the [RAET Github](https://github.com/saltstack/raet)

### State Database
CouchDB additionally enables rich query against the smart contract data, when chaincode values (e.g. assets) are modeled as JSON data.

you can also perform complex rich queries against the chaincode data values, using the CouchDB JSON query language within chaincode. These types of queries are excellent for understanding what is on the ledger. 

### Account Identifiers 

`1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa` - A Bitcoin Address

  Traditional blockchain designs use cryptographic hashes to generate globally unique IDs that are statistically guaranteed to never have a collision. 
The problem with these hashes is that they require significantly more memory and more CPU cycles to manipulate. It takes significantly more CPU time to look up an account record by hash than with a direct array index. 
For example, 64-bit integers are easier to compare and manipulate than 160+bit IDs. Larger hash IDs means there is less room in the CPU cache and that more memory is required. On modern operating systems, infrequently accessed RAM is compressed, but hash identifiers are random data that is not compressible.

We propose the implementation of a Globally Unique Identifier (GUID) for use in account identification. Various implementations have been studied such as **IBAN** or International Bank Account Number.  Requirements for such an address scheme must:

+ Serialized
+ Standardized 
+ Efficient 



### Endorsement Policies

Signatures (Ring Signature Implementation)

### Masternodes
paragraph 


1. Primary
2. Secondary
3. Heartbeat

#### Primary

Primary nodes provide specific services:

- Membership Service Provider
- Validating Peers

These are to ensure server uptime 

#### Secondary

Data Layer nodes
Non-Validating Peers
These are to ensure the public layer channel redundancy. 


> Think of Primary as “Miners” and Secondary as “Full Nodes” - they keep a record of the entire chain but do not commit blocks to the chain

$$\sigma = \alpha * 1.37$$
where $$\sigma$$ is the amount of Secondary and $$\alpha$$ is the number of Primary nodes and $$1.37$$ is a fixed constant determined by us

#### Heartbeat 

Heartbeat nodes are specific network participants for the gossip protocol. They are responsible for the ordering of transactions.

**Dynamic leader election**
Dynamic leader election enables organization peers to elect one peer which will connect to the ordering service and pull out new blocks. Leader is elected for set of peers for each organization independently.
Elected leader is responsible to send the heartbeat messages to the rest of the peers as an evidence of liveness. If one or more peers won’t get heartbeats updates during period of time, they will initiate a new round of leader election procedure, eventually selecting a new leader. In case of a network partition in the worst case there will be more than one active leader for organization thus to guarantee resiliency and availability allowing the organization’s peers to continue making progress. After the network partition is healed one of the leaders will relinquish its leadership, therefore in steady state and in no presence of network partitions for each organization there will be only one active leader connecting to the ordering service.
Following configuration controls frequency of the leader heartbeat messages:

    peer:
      gossip:
            election: leaderAliveThreshold: 10s