# Blockchain

We setup a hyperledgr fabric blockchain baseline environment which can be used for future projects built on it.

- [Blockchain](#blockchain)
  - [0. Prerequisites](#0-prerequisites)
  - [1. Installation](#1-installation)
  - [2. Using the Fabric test network:](#2-using-the-fabric-test-network)
  - [3. Deploy my production network](#3-deploy-my-production-network)
  - [3. 1 Step one: Decide on your network configuration](#3-1-step-one-decide-on-your-network-configuration)
  - [3.2 Step two: Set up a cluster for your resources](#32-step-two-set-up-a-cluster-for-your-resources)
  - [3.3 Step three: Set up your CAs](#33-step-three-set-up-your-cas)
    - [3.3.1 Fabric CA](#331-fabric-ca)

## 0. Prerequisites
- Advanced Operating Systems (Distributed Systems) - Graduate level 
  - Ordering, Gossip, BFT, Raft
- Computer Security
  - Hash
  - Cryptography
  - Public Key Infrastructure (PKI)
- Key Concepts in [Hyperledger-Fabric Offical website](https://hyperledger-fabric.readthedocs.io/en/latest/key_concepts.html)

  Note:
    It would be better if you have took the first two courses. If not please read "Key Concepts" and understand them.
- [Docker](docker.md)


  
## 1. Installation

0. Check prerequisites

https://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html


1. Create a folder for Go. 

```
mkdir -p $HOME/go/src/github.com/<your_github_userid>

cd $HOME/go/src/github.com/<your_github_userid>
```
This is a Golang Community recommendation for Go projects.

2. To get the install script:

```
curl -sSLO https://raw.githubusercontent.com/hyperledger/fabric/main/scripts/install-fabric.sh && chmod +x install-fabric.sh
```

This will download ```install-fabric.sh``` into the directory ```$HOME/go/src/github.com/<your_github_userid>```.


3. Pull the Docker containers and clone the samples repo
```
./install-fabric.sh docker samples binary 

or 

./install-fabric.sh d s b  

or withour example network

./install-fabric.sh docker binary 
./install-fabric.sh d b  
```

This will  download a directory named ```fabric-samples```.

Now that you have downloaded Fabric and the samples, you can start running Fabric.

## 2. Using the Fabric test network: 

More detials please check out [Run the example (Fabric test network)](example_network.md). I only keep the core part of official website contents which might be too redunctant and complicated. It would be good enough to read this section only.

It's highly recommended you play with the ttest network before you go to next section.

## 3. Deploy my production network


## 3. 1 Step one: Decide on your network configuration

- Blockchain
  - 5 blockchain peers
    - 1 orderer
    - 4 peers which as hubs for 4 intersections
- 3 organizations
  - 1st has 2 peers
  - 2nd has 2 peers
  - 3rd has 1 orderer
- 16 nodes/intersections
 

![](img/intersection_12TL_archi2.png)

- Certificate Authority configuration
  - 6 peers
    - one overall channel
  - ordering service 
    - one orderer, which is the 7th peer
  - TLS CA 
- Use Organizational Units or not?
  - Not yet
- Database type
  - Use defalut LevelDB (key-value database)
- Create a system channel or not
  - Use the recommended method: bootstrap ordering nodes without a configuration block ("system channel")
- Channels and private data
  - For us, channels are enough to ensure privacy and isolation for transactions
- Container orchestration
- Chaincode deployment method
  - options
    - Use a built-in build and run support
      - It looks this is the default. Use this firstly.
    - Use a customized build and run using the External builders and Launchers
    - Use an Running Chaincode as an External Service
- Using firewalls
  
## 3.2 Step two: Set up a cluster for your resources

- Persistent Storage
  - You will also need to add storage to your cluster (some cloud providers may provide storage) as you cannot configure Persistent Volumes and Persistent Volume Claims without storage being set up with your cloud provider first. The use of persistent storage ensures that data such as MSPs, ledgers, and installed chaincodes are not stored on the container filesystem, preventing them from being destroyed if the containers are destroyed.

## 3.3 Step three: Set up your CAs

- 1st compoenet must be a CA
  - Use default Fabric CA

### 3.3.1 Fabric CA


![](img/5peers_network_topology.png)

https://hyperledger-fabric-ca.readthedocs.io/en/latest/operations_guide.html

