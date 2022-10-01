# Blockchain

We setup a hyperledgr fabric blockchain baseline environment which can be used for future projects built on it.

- [Blockchain](#blockchain)
  - [0. Prerequisites](#0-prerequisites)
  - [1. Installation](#1-installation)
  - [2. Using the Fabric test network:](#2-using-the-fabric-test-network)
  - [3. Deploy my production network](#3-deploy-my-production-network)

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


