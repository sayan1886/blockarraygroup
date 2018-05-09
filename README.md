


# Block Array White Paper


!> **Warning** This is in progress, and may have breaking issues

:warning: Spelling errors are soon to be fixed, along with new graphics. we are nearing completion and aim for release candidate to be version 2.5

---

**version 2.2.0**

Author: Sam Bacha *Founder*

To Do List (as of 5/6/18)
Add Disclosures and Legal Section
Add EPCIS transaction table
Add Network Topology Map
Redo Maximizing token Value section
Import Intro and SCM sections from v1 whitepaper
Check Spelling mistakes
Check Grammar 

Re-do all graphics and have graphics on AWS dedicated folder
Re-do all tables in airtable 

have editorial process completed
Flesh out industry scope (pharma, defense)
Insert in-line citations and import references 

Reformat Inline Table of Contents to reflect new sections

## Introduction


Block Array Corporation 

www.blockarray.com


----------
Table of Contents 


1. Abstract
  1. Overview
2. Overview of the Supply Chain Industry
  1. Problems
  2. Use Cases
  3. Solutions
    1. Blockchain Network
    2. Industry Specific Applications
    3. Infrastructure 
3. Ecosystem
  1. Goals
  2. Design Considerations
4. Blockchain Specifications
  1. Requirements
  2. Unique Implementations
  3. ARY Token
  4. Performance Benchmarks
5. Applications
  1. Trucking
  2. Logistics
  3. Data Analytics
  4. Insurance
  5. Retail
6. Roadmap
7. Corporate Information
  1. Overview
  2. Commercialization 
8. References 
9. Appendix



----------
>
>
>
>
>
>
>this section left intentionally blank 
>
>
>
>
>
>
>
----------


[![](https://img.shields.io/badge/whitepaper-v2.1.9-lightgrey.svg)](https://github.com/blockarraygroup/blockarraygroup)


[![](https://img.shields.io/badge/telegram-group-blue.svg)](https://t.me/Block_Array)

[![](https://img.shields.io/badge/twitter-%40blockarraygroup-blue.svg)](https://twitter.com/@blockarraygroup)

[![](https://img.shields.io/badge/e--mail-contact%40blockarray.com-brightgreen.svg)](mailto:contact@blockarray.com)




----------


# Abstract

Blockchain Networks are typically designed for public-facing applications, i.e. cryptocurrency usage. 

In order to create a blockchain network for business use, specific changes need to be implemented, from the protocol layer all the way to the application layer. It is this goal in which we hope to acheive for the supply chain / logistics industry: a blockchain network that has modular components that can be plugged-in to enable performant use and provide industry specific applications for clear and demonstrable use cases for industry use.

In pursuit of the goal a few things must be done:
Enhanced transaction style to match Industry norms
Deterministic consensus protocol 
High throughput in transactions
Applications that are industry-specific
On-chain and off-chain governance 
Security standards that meet well-established Industry needs 


----------


# Overview

Global operations need consistent global standards to be applied across their supply chain, and this is only going to become increasingly difficult with legacy enterprise systems and increased legal costs. Laws recently passed like The California Transparency Supply Chain Act or the Electronic Logging Data Mandate for Trucking add additional burdens to businesses trying to comply with the law, coupled with more demands on increasingly outdated IT systems - this then creates multiple problems for firms. 

This document is broken up into  # main sections.

1. Logistics and Supply Chain Industry Overview
2. Areas of Improvement 
3. Our Ecosystem
4. Implementation of our Ecosystem
5. Corporate Overview

# Logistics & Supply Chain Management

We can divide the logistics industry into three (3) segments: Land, Air and Sea.

Of these market segments, land (overland freight) compromises the largest share, with Trucking being the largest segment of overland freight.

> Supply Chain Management main goal is: **Demand Forecasting**



## Freight Industry

### Trucking 

> **Revenue**
`$738.9 billion in gross freight revenues` (primary shipments only) from trucking, representing 81.5% of the nation’s freight bill in 2016.

> **Tonnage**
`$10.55 billion tons of freight (primary shipments only)` transported by trucks in 2016, representing 70.9% of total domestic tonnage shipped.


> **Number of Companies**
According to the U.S. Department of Transportation, as of June 2017, the number of for-hire carriers on file with the Federal Motor Carrier Safety Administration totaled *777,240*.

> `91% operate 6 or fewer trucks.`
`97.3% operate fewer than 20 trucks.`


#### Advances in Trucking Operations

While many have touted the arrival of autonomous driving vehicles, drones, and even electric tractors, most advances in trucking have been in *how* the distribution of goods happens in the supply chain. Cross Docking operations have given certain companies a competitive advantage when it comes to their operations, so much so that they have been able to drive success from it.

*Distributor Cross Docking*: This is where a distributor consolidates inbound products from various vendors into a mulit-SKU pallet, which is delivered as soon as the last product is received. Computer distributors often source components and consolidate them into one shipment in merge-in-transit centers before delivering them to the customer, and rarely have the same vendor for all the products. Think of a Desktop tower, a monitor, a keyboard, and mouse that are combined into one package at a cross-dock for delivery to the customer as a single package. 

*Retail cross-docking*: This involves the consolidation of shipments from different shippers and vendors to be sorted onto outbound trucks for different stores. Walmart pioneered this system in the 1980s to gain a competitive advantage against competitors such as Sears or Kmart.


#### Electronic Logging Device Mandate

The Electronic Logging Device Mandate (ELD) is intended to help create a safer work environment for drivers, and make it easier and faster to accurately track, manage, and share records of duty status (RODS) data (FMCSA 2018). An ELD synchronizes with a vehicle engine to automatically record driving time, for easier, more accurate hours of service (HOS) recording.


  The ELD Mandate Includes provisions to help prevent data tampering and harassment of drivers.

What is the impact of this new law?


!> Under Federal regulations, the motor carrier is responsible for training and monitoring its drivers to ensure compliance with Hours of Service rules.  Any driver violation may also be held against the carrier. Failing to establish an effective Hours of Service monitoring and compliance system can result in fines of thousands of dollars.  In extreme cases, motor carrier officials have even received jail sentences.

So, any violation in failing to comply with this new law could mean 


Four Driver Status Modes
The choices of duty status when a property-carrying driver records his or her time on a record of duty status, or R.O.D.S

>  `off duty | sleeper berth | driving | on duty/not driving`



| Hours of Service Rules       |
| ---------------------------- |
| 10 hours off-duty            |
| 14-hour duty period          |
| 11 hours driving             |
| 30 minute break              |
| 60 hours/7-day on-duty limit |
| 70 hours/8-day on-duty limit |


Add to these rules are the burdensome additional regulations such as when


+ Once the duty period starts, it runs for 14 consecutive hours after which the driver may not drive a CMV again until having another 10 or more consecutive hours off-duty. Nothing stops the running of the 14 hour clock.
+ During the 14-hour duty period, which some people refer to as a “driving window,” you may drive a maximum of 11 hours.
+ When you reach a total of 60 on-duty hours in 7 days, you must have a period of at least 34 consecutive hours off duty. (There is an alternative available for carriers that operate every day of the week-- that is a maximum of 70 hours in 8 days.)
+ Requires an off-duty break at some point during the duty period. The rule says that you may not drive a CMV if it has been 8 or more hours since your last off-duty period of at least 30 minutes.
+ For every 5 duty periods that they return to their starting point, they may choose one 16-hour duty period.
+ The counting of the maximum 60 or 70 hours on duty restarts anytime a driver has at least 34 consecutive hours off duty.


[airtable-embed](https://airtable.com/embed/shrAK5qn8v7XOt5fq?backgroundColor=blue&viewControls=on ':include :type=iframe width=100% height=533x')


----------


# Ecosystem

Our ecosystem includes a variety of solutions aimed at leveraging existing technologies and market fit. 


- Both Blockchain and Traditional Solutions
- Web and Mobile
- B2B and B2C Solutions 
- Analytics and Intelligence Toolset


Our Ecosystem strives to cover these core competencies

+ Compliance and Accountability
+ Document Authentication and Management
+ Data Forecasting, Insights and Analytics

FreightRelay: 
ChainProof: API for Inter-Blockchain Connectivity
Driver & Vehicle Passports
SmartQR: Barcodes (1D/2D)

Therefore, our product listings are:
Passports for Drivers, Vehicles and Assets
Documents & Records: Bills of Lading, Industry Specific Documents, Legally Mandated Records
Barcodes -  


## Passports - Driver, Vehicle and Asset

Passports are in essence, the public address of an account with additional information. This information is tied to the account through the `accountHeader`. It is in essence a merkle tree of records from different sources (both on-chain and off-chain)

+Driver_Passport
  _Identity
    Name
    Address
  _Certification
    Medical
    CDL
    Restricted Transport Loads
  _Driver History
    Records of Accidents
    Years driving with current CDL rating
  _Employer Records
    Manager Information
    Payroll
      Payroll History
        2017
        2018
    Signed Documents
    Tax Witholding Information

These records can refer to on-chain records or off-chain records. 

>Driver Passports are in control of the driver themselves. By default they are shared with only their employer: they have complete control over disclosing any information to other parties, including Block Array



[airtable-embed](https://airtable.com/embed/shrCzCmWXhYaIs4oX?backgroundColor=blue&layout=card&viewControls=on ':include :type=iframe width=100% height=533x')                                                                              

*These must be listed on the supporting documents in order to be eligible for use.*

### Supporting Documents 

[airtable-embed](https://airtable.com/embed/shrmxXAV1idTUZ1xE?backgroundColor=blue&layout=card&viewControls=on ':include :type=iframe width=100% height=533x')

What happens if a log was anchored incorrectly? 
The ELD regulation provides for this, as both the original and edited versions must be retained. Any edits to the log, either by the motor carrier or driver must be annotated as to the reason for the edit. On the Driver Passport page, both records are accessible. 


https://airtable.com/shrCzCmWXhYaIs4oX


## EPCIS

EPCIS – Electronic Product Code Information Service It is an international standard adopted by GS1 in September 2016 to Identify, Capture and Share Information using barcodes/etc. It enables disparate applications to leverage Electronic Product Code (EPC) data by sharing that data. The EPC data is shared within and across enterprise boundaries. Sharing this data enables all participants within an EPCIS compliant ecosystem to gain visibility into the status of all EPC “marked” digital or physical items (also known as EPCIS “objects”) within a given business context. Simply put, EPCIS provides a framework that allows trading partners to know the status of a given trade item or conveyance. 

> GS1 is a non-profit org. that manages standards for the supply chain industry, including barcodes.

EPCIS events affect the status of a trade item or conveyance by changing or setting the object’s disposition (its current state, such as sold, expired, recalled, in transit, or active). “EPCIS is a standard which provides the means to Identify real-world entities so that they may be the subject of electronic information that is stored and/or communicated by end users/clients. GS1 identification standards include standards that define unique identification codes (called GS1 Identification Keys), such as the Global Trade Item Number.” [GS1] 

*GS1 data capture standards include definitions of bar code and radio-frequency identification (RFID).*

It also provides the means to share information, both between trading partners and internally, providing the foundation for electronic business transactions, electronic visibility of the physical or digital world, and other information applications. GS1 standards for information sharing include this EPCIS Standard which is a standard for visibility event data. Other standards in the “Share” group are standards for master data and for business transaction data, as well as discovery standards that help locate where relevant data resides across a supply chain and trust standards that help establish the conditions for sharing data with adequate security.

**Description of EPCIS Event Data**
EPCIS is structured in a way to define business processes as individual business steps. Information of a single EPCIS event data is organized into four different dimensions:


- **What** The identifiers of the object(s) or other entities that are the subject of the event 
- **When** The date and time when the event took place, and the local time zone in effect 
- **Where** The identifier of the location at which the event occurred, and identifier of the location where the object(s) are expected to be following the event 
-  **Why** Information about the business context, including: a identifier that indicates the business step taking place (e.g., shipping, receiving, etc.), an identifier that indicates the business state of the object(s) following the event (e.g., active, recalled, damaged, etc.), identifiers of the shipping and receiving parties (if the event is part of a process of transfer between parties), links to relevant business transaction documents (e.g., a purchase order, an invoice, etc.), instance- or lot-level master data, and/or other information defined via user extensions. 

The EPCIS data model calls for an identifier, EPCIS allows any URI/URL to be used to store additional data. We use this model because of interoperability with barcodes across the globe.

**Why EPCIS is important**
EPCIS Event Data The Core Business Vocabulary (CBV) is a GS1 Standard that defines specific data values to populate the EPCIS data model. This ensures that all parties who exchange EPCIS data have a common and consistent understanding of the semantic meaning of that information. [GS1] By documenting supply chain events, EPCIS data complements other types of data exchange in the supply chain, such as business transaction data (exchanged with GS1 eCom) and master data (exchanged with GS1 Global Data Synchronization Network or GDSN).


> EPCIS provides visibility on a “need-to-know” basis for goods.

A company implementing EPCIS can use the authenticated identity of a trading partner in conjunction with pre-defined business rules (smart contracts/chaincode) to determine which information is made available to that partner. 


| Business Applications that utilize EPCIS event data |
| --------------------------------------------------- |
| Product Authentication                              |
| Pharmaceutical Pedigree                             |
| Product and food traceability                       |
| Inventory Management                                |
| Shipment Tracking                                   |
| Electronic Article Surveillance (EAS)               |
| Promotion Tracking                                  |


### A New Transaction Type

Ordinary transactions on a blockchain typically are just a movement of an asset from one account to another. With Ethereum, there has been additional transaction types, *additional data* in which a user may interact with a smart contract. In order to adapt a blockchain for supply chain needs a transaction must be able to provide **EPCIS event information**. 

## Object Naming Service 

In order to use DNS to find information about an item, the item’s GS1 Identification Key must be converted into a format that DNS can understand, which is the typical, “dot” delimited, left-to-right form of all domain names. As the purpose of ONS is to discover data and services associated with a GS1 Identification Key and multiple sets of data and services may exist for that key, the appropriate DNS record type is the Naming Authority PoinTeR (NAPTR) [RFC 3403]. This record type contains several fields for denoting the protocol, services, and features that a given service endpoint exposes. It also allows the service endpoint to be expressed as a URI, thus allowing complex services to be encoded in a standard way. 

The figure below describes a typical ONS query from start to finish from the viewpoint of an application. In this example, the starting point is a bar code or RFID tag. However, the source of the GS1 IdentificationKey is not restricted to data carriers; it could be part of a transaction document (e.g. a purchase order), an event record, a master data record, or any other source.

%% insert img %%

## Shipping Documents

%primer on shipping documents

+ Bill of Lading
+ Letter of Credit
+ Certificate of Origin
+ Insurance Certificate
+ Packing List
+ Material Safety Datasheet

> Cosignee: Person/Business the shipment is intended for

Bill of lading (BOL) is one of the most important documents in the shipping process. To ship any goods, a **bill of lading is required and acts as a receipt and a contract**. A completed BOL legally shows that the carrier has received the freight as described and is obligated to deliver that freight in good condition to the consignee.


## Bill of Lading

A Bill of Lading is a legal document issued by the Carrier or agent of the Carrier. They are the legal title to the cargo. It has three main attributes:  

Document of Title to the goods: possession of the Bill of Lading is equal to having title in the referenced goods. 
Receipt - Evidence that the Carrier has received the goods of a certain quality etc in compliance with the Commercial Contract between the parties
Contract of Carriage - Evidence of the Contract of Carriage (CoC) - that the carrier will transport the goods in compliance with the Commercial Contract.

### Problems with the current system

Theft - BoL is a bearer document of title. This bears a particular risk that anyone who has possession of the BoL has a prima facie claim to the goods. Because possession equals ownership this creates an incentive for BoL theft. 

**Fraud** - Manipulation/alteration of BoL to hide accountability due to shipment damage or other issues.
Inefficiency - BoL are issued as three original physical documents. One document is managed by the banks involved in trade finance. One document is couriered to the recipient of the goods. And one document is retained by the Carrier. 

**Physicality** - Delay in distribution of the BoLs. Due to the originals only existing in a physical form, this means that the Carrier has to courier one of the originals to the Consignee. This leads to a situation where the goods have arrived at a Discharge port but that the Consignee has not received their BoL. 

**Amendments** - Making amendments to a BoL can be complicated. All three BoLs have to be sent to the Carrier who destroys them, then issues a new set of BoLs with the intended amendments. 


![alt text](https://s3.amazonaws.com/blockarray-hosting/static/whitepaper_imgs/gs1_bol.png "Bill of Lading, GS1")


Many attempts have been made at modernizing shipping documents, and the shipping industry as a whole. Yet there are vestiges of poorly implemented solutions such as EDI (Electronic Data Interchange) and the widespread use of XML that still plague the industry. Electronic document management is not a new solution, especially in the logistics/shipping industry. Yet the issue that has prevented bills of lading and other shipping documents from *truly* taking hold is uniqueness. Since a title is supposed to be unique, a physical, paper bill of lading has always been required as digital documents had, until now, been unable to retain that crucial property of being unique. Having a blockchain-based bill of lading can solve this issue, and all the issues we have listed in the previous section.

> Digital Scarcity is the property required for a digital bill of lading being able to truly succeed in the logistics/shipping industry

Our solution, **Visual SmartContracts** is an application that allows users to create a smart contract-based document like a bill of lading. 

#### Visual SmartContracts 

Visual SmartContracts implements the following

!> **Warning** Some features may not be implemented depending on user feedback/product market fit

+ WYSIWYG Form/Text Editor
+ Define user policies to implement EPCIS events
+ Import existing documents 
+ Create new documents
+ API to automate field imports
+ API to notify/trigger users/events
+ Document Signing using PKI/Legacy Signatures
+ Advanced Meta-data collection
+ 100% Privacy
+ 100% Standards compliant (GS1, SSAC, etc.)
+ Unique Physical Document Authentication and Tracking
+ Foreign Language Localization Support (UTF-8, RTL, etc.)

Once a Bill of Lading is transferred from one user to another, the original user will not be able to modify the bill of lading and will only retain a generated copy after the transfer for their records.

### Enterprise Smart Contracts
In order to design and implement enterprise-quality smart contracts, we need to define exactly what an enterprise smart contract is. We shall decompose this concept into its major components below:

**Components**

+ Schema: the data elements required for the execution and fulfillment of contract obligations between counterparties and the cryptographic proofs needed to maintain the integrity and trust in the contract for the participating counterparties and any regulatory or oversight entities. 

+ Counterparties – authenticated identity that can utilize the same cryptographic primitives as blockchains like digital signatures, of participants (people, organizations and things) agreeing to the terms and execution of the contract. Counterparties are represented as personas in the logic of a contract that are assigned identity as the contract goes through its binding process.

+ External Sources – contracts that require external interaction, input of data or notification in order to fulfill the execution requirements of the contract. These external sources and conditions for interaction are agreed to by the counterparties and the regulatory oversight entities and must provide cryptographic proofs in order to trust and maintain the integrity these external sources. 

+ Ledger – the immutable instance on a distributed ledger (blockchain) based on the schema that is used to record all contract activities and proofs required. This is can be either the public version of a “distributed trustless truth database” or a “shared, permissioned, semi-trusted, discretionarily private, truth database”. 

+ Contract Binding - A Enterprise Smart Contract Binding is the composition of these parts creating a unique instance of an Enterprise Smart Contract. It is created when a contract begins negotiation between counterparties and becomes versioned and locked when each counterparty signs the contract. Once signed and locked the Enterprise Smart Contract begins the execution of the terms and conditions that lead to fulfillment.

In order to develop Enterprise quality smart contracts standards, need to be put in place. 
+ Universal Business Language 
+ Industry Agreed-upon Standards and Verbiage 
+ Data Attestation for data being provided
+ Discrete Privacy Levels

We can categorize smart contracts into two distinct feature sets 
> **Notification** and **Executing**

#### Parametric Smart Contracts

As discussed in the previous section, there are two basic types of smart contracts: Notifying and Executing. These both fall into a category we call **Parametric** smart contracts.



## ChainProof 

For example, if a screwdriver manufacturer creates a new screwdriver, they could tokenize the screwdriver and record it using the digital signature of the manufacturer establishing provenance. 
Then, once sold and shipped to a distributor, a transaction transfers ownership of the tokenized screwdriver to the distributor (public key). This transfer of ownership is confirmed by signing the transaction with the same digital signature of the manufacturer. 
The distributor can repeat the same exercise using their keys when selling the asset in the future, documenting the lineage of that screwdriver as it navigates the supply chain.

erc721
Tokenization and signing with public/private key pairs in the blockchain world establishes provenance, documenting the moment a thing is recorded.
Public key can be used to support buying, selling, trading, insuring and tracking of things across organizations thus creating a full audit trail of the tokenized object itself, or lineage.

Tokens can and usually are bundled together in a collection. The collection can also be tokenized creating a composite token of all the tokens contained within. 
For example, if every phone part were to be tokenized and assembled into a phone, the phone itself could be represented with a token made from its parts.

## Barcodes

%% BARCODE IMG %% 

The first six to nine digits of a UPC are referred to as the “Company Prefix”, and they are
assigned by a non-profit organization (GS1). This number uniquely identifies a company and
always remains constant on all of a company’s products. The next set of digits is called the
“product numbers.” Product numbers uniquely identify individual items. Unlike the GS1
Company Prefix, product numbers are arbitrarily assigned by each company. The twelfth
character is called the “check digit”. Using some form of check digit generator this digit is
calculated using a mathematical calculation based on the first 11 digits of the UPC code.

!> Since 2016 Amazon requires and in addition verifies the authenticity of product UPC’s by
checking the GS1 database. 

----------



<<<<<<< HEAD
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

- Anchor Peers
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
=======
>>>>>>> 3c2523cb532bd93e22bcbcb1bdf11484edb12f96



## ARY Token
  

The Block Array Token, "ARY" is an Ethereum standard compliant "ERC-20" blockchain asset. The asset is our implementation of a software license that is used in a variety of ways for the end customer. The ARY token can be thought of as an access card, granting the end user the ability to interact with various applications and infrastructure. The ARY token enables the user rights of access depending on the number of tokens they have in their possession. Along with access rights they are granted an allotment of network resources based on the amount of ARY held.
*** insert equation here ***
ARY is not a currency nor a virtual asset meant to be used for the payments of goods and services.
This design choice was made because of the following factors

[ ] Ease of Use
[ ] Lower Wallet Requirements
[ ] Little Accounting/GAAP considerations
[ ] Less Accounting Headache


The amount of ARY tokens is preliminary and has not been finalized yet

| Tier      | # of ARY Tokens |
| --------- | --------------- |
| Primary   | 40,000          |
| Secondary | 22,500          |
| Heartbeat | 7,500           |

### Token Implementation 

In order to establish a token to distribute the network a **Token Generation Event** is required. The token *must* have a value in order for it to be useful in safeguarding the network and for creating the incentives for individuals to participate in hosting the network.

ARY, the Ethereum Token we have created is based on a standard that has been accepted by the community through an EIP (Ethereum Improvement Proposal) called `ERC-20`

> to read the full standards reference visit the [Ethereum github](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md)

Symbol: ARY
Decimals: 18
Address: 0xa5F8fC0921880Cb7342368BD128eb8050442B1a1

**Difference between an ICO and a TGE**
An ICO, *initial coin offering*, has some characteristics different than what we consider a TGE, *token generation event*, such as:

+ Supply of coins/tokens is determined no matter if contribution amount hits hard cap
+ Coin/Token is used for proprietary payment 
+ Coin/Token is eventually replaced with a native on-chain asset 
+ Coin/Token is itself the "application"

The ARY Token is different in that:
+ Token supply is generated only when *contributions* are sent to the smart contract 
+ Token is *not* used for payment of services, rather is used as a *license* 
+ Token is *not* replaced with a native on-chain asset
+ Token is *not* itself the application, rather enables access to multiple applications

#### Maximizing Token Value

There are three (3) main token economic models:

Payment Token
Service Token
2-Way Token (Burn-and-Mint Equilibrium)

In a monetary base, valuation is obtained through the *equation of exchange* which is defined as `MV=PQ` where `V` is *velocity*.

![](https://www.dropbox.com/s/ls37aojppwmtpcl/mv_pq.svg?dl=0)

In designing a token model in which *value* increases with *network usage* we can claim that as *v* increases *Price,p* accelerates in the downward slope (i.e. negative price pressure)

A Service Token is one in which a user "stakes" or "bonds" the token of the network in order to provide *services* to the network, such as file storage (Storj, Filecoin), computation power (Golem), or -etc-. 

So, as demand for the service grows and a fixed supply (*ceterus paribus*) the price per token will increase as more users wish to provide services. This can be modeled by NPV;

> **Net Present Value**

![alt text](https://s3.amazonaws.com/blockarray-hosting/static/whitepaper_imgs/net_present.svg "Net Present Value Formula")

**Currency Tokens** trend towards a **fractional value of transaction volume**

**Service Tokens** trend towards a **multiple of operating cash flow**

> *Note* while this model holds true for pure service commodities, an argument can be made that it is applicable in drawing a close approximation in our use case as *service providers* provide the service of network security and uptime (i.e. they host part of the network)


#### Token Use Case

Token License for Network & Application Access
In order for businesses to become a network participant they must buy a certain amount of ARY Tokens. This baseline creates a minimum amount of network resources they are entitled to per day. If they require more resources they must purchase more tokens. Tokens are NOT used per transaction, but rather held and staked, whereby the system chaincode enables them to conduct the amount of transactions they are entitled to per their token holdings.

Access to specific applications will also require additional tokens. 

3rd Party Application developers may also offer their applications for sale on the network, whereby a revenue royalty agreement is agreed upon. 


Whereby resources per day provides a variable in a function that is responsible for determining the *expenditure* rate or "burn" rate.

> Example
> 

Business "A" wants to join the blockchain network and wants to have 10 employees on the network. B
Step 1: Business "A" must buy 10,000 ARY Tokens
   5,000 ARY is used to register the Business Entity
   500 ARY is used per employee to create accounts
 Step 2: Business "A" goes to the Registry DApp and selects what kind & how many licenses it wants (1 ORG licenses and 10 personal ONEL licenses)
Step 3: Business "A" sends 10,000 ARY Tokens to the Registry DApp

Step 4: Registry DApp creates three (3) smart contract licenses. One for the ORG and 1 for its PERSONAL list. The third smart contract contains a  (m-n) in which the tokens are held. -replace: tokens sent to the token pool contract which contain all the tokens. 

`70% are "Staked"
 20% are sent to the Merkle Pool (to be used to pay for masternodes)
 10% are "expended" per *actual* transactions conducted on ARY Network while their reputation is being formed (expenditure ends when reputation reaches threshold`

Step 5: 
Step 6. Registry DApp sends off information to the ARY Membership Service Provider. User is given an authentication code that enables them to claim their registration on the MSP.
Step 7: User claims their Membership Certificate, and depending on their registration, can begin enrolling their employees, or being transacting on the network. 

#### Keeping the ERC-20 Token 

**The ERC-20 Token is the asset used**, in other words *there is no "conversion" to another digital asset needed* under our system

![](https://s3.amazonaws.com/blockarray-hosting/static/whitepaper_imgs/resource_eq.png)

` R = [X / square root(Z)] `<br>
` R = Resources (transactions, queries, etc.) available per 24h period `<br>
` X = Tokens Staked by User `<br>
` Z = Resource Modifier defined by Price Function of ARY Token `<br>


> The variable 'Z' Price Function will be finalized upon the completion of market research and community input, and is not a permeant constant 


<center>*Example*</center>

![alt text](https://s3.amazonaws.com/blockarray-hosting/static/whitepaper_imgs/network_resources_table.png "Preliminary Staking")

#### Calculating Node Reputation 

Developing a benchmark to calculate malicious nodes 

**Eigenvector Centrality**
` equation1 here `

**Max-Flow Analysis**
` Equation2 here `

Node Reputation 
` function of Equation1+2 here `

#### Mitigating Attack Vectors

By distributing the network among individuals who have our ARY token, they reduce the chance of businesses being able to form a cartel for the purpose of disrupting the network. 

![Distribution of the Network among all Participants](https://www.dropbox.com/s/zbbacvd6r9w84bo/Screenshot%202018-04-23%2013.39.51.png?raw=1)


token as network incentive 

The following diagram illustrates how the ARY Blockchain distributes rewards by using the Ethereum Blockchain (thereby the ERC-20 token).


![](https://www.dropbox.com/s/m92bfzsfew7i8ei/Screenshot%202018-04-23%2013.41.30.png?raw=1)


### Developing on the ARY Blockchain

Our API/SDKs will be available in at least 10 different programming languages, which are:

PHP, .NET, Ruby, Python, Node, Golang, iOS, Android, HTTP, Java, & Angular.

Developers can already begin work utilizing SDKs available for Hyperledger Fabric:

*We Recommend using Node as it has better documentation*
[Node.js](https://fabric-sdk-node.github.io/index.html)
[Java](https://github.com/hyperledger/fabric-sdk-java)

Developers may establish a side chain through invoking system chaincode. In order to establish a side chain you will need to create a specific Certificate by staking ARY. 

For more information please e-mail: admin@blockarray.com with the subject;
"Side Chain Certificate Request"

**Software Licenses**
Applications created by 3rd Party Developers must follow our license scheme, and any open source software must follow our criteria for licenses. Supported F/OSS licenses include:

Apache Foundation 2.0
BSD 2.0
BSD + Patents
MIT License

> GPL Licenses require a review process as GNU/GPL imposes certain requirements on downstream applications that utilize GNU/GPL licensed software. *This does not mean that you cannot license it under GNU/GPL, rather that it requires us to make sure what parts are and are not licensed under it*.

For more information please visit [**Open Source Initiative**](https://opensource.org/licenses/category)

**Documentation and non-software licenses**
Documentation is licensed under the Creative Commons 4.0 International Share-Alike

For more information please visit [**Creative Commons**](https://creativecommons.org)
Requirements

  1. Unique Implementations
  2. ARY Token
  3. Performance Benchmarks



### Octopus 

`struct block_header
{
digest_type digest()const;
obuint32_t block_num()const { return num_from_id(previous) +
˓→1; }
fc::time_point_sec timestamp;
witness_id_type witness;
checksum_type transaction_merkle_root;
extensions_type extensions;
static uint32_t num_from_id(const block_id_type& id);
};`


# Summary



## Use Cases & Solutions


**Compliance** 
Truck Drivers are required to undergo both a Drug & Alcohol certification and a Medical Certification 

**Bill of Lading, Shipping Documents, etc**

**EPCIS Style Transaction Types**

**Detention Proofs & Payouts**

**Decentralized Load Board**
Brokers will no longer be able to rely solely on booking loads, as our decentralized load board will be able to complete that task. 

**Maximizing Used Shipping Capacity**

**Physical Goods and Document Authentication**

----------

# References

FMCSA 
https://www.fmcsa.dot.gov/hours-service/elds/electronic-logging-devices

D.O.T 
https://www.gpo.gov/fdsys/pkg/FR-2015-12-16/pdf/2015-31336.pdf

BitShares - Blockchain Scalability
https://bitshares.org/technology/industrial-performance-and-scalability/

RBFT: Redundant Byzantine Fault Tolerance
https://pakupaku.me/plaublin/rbft/5000a297.pdf

Software Licenses | Open Source Initiative 
https://opensource.org/licenses/category 



___

# Document & Development Styling Guide

This document was prepared in [**Sublime 3**](https://www.sublimetext.com/)

We follow the [**Semantic Versioning**](https://semver.org/) specification for version numbering.
$$ \alpha $$

This document uses the following Markdown Specifications 
<b>Common Mark</b>

Finally, the site was generated using [**docsify**](https://docsify.js.org/#/)

(C) 2018 **Block Array Corporation** | *All Rights Reserved*



