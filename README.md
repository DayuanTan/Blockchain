# Blockchain

We setup a hyperledgr fabric blockchain baseline environment which can be used for future projects built on it.

## Prerequisites
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


  
## Installation

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

3. Pull the Docker containers and clone the samples repo
```
./install-fabric.sh docker samples
```


Now that you have downloaded Fabric and the samples, you can start running Fabric.

## 

Using the Fabric test network: https://hyperledger-fabric.readthedocs.io/en/latest/test_network.html



## Run

Then you can run  the example. 

You can find the scripts to bring up the network in the test-network directory of the fabric-samples repository. Navigate to the test network directory by using the following command:
```
cd fabric-samples/test-network 
```