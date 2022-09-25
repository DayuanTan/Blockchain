# Blockchain

We setup a hyperledgr fabric blockchain baseline environment which can be used for future projects built on it.

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
```

This will  download a directory named ```fabric-samples```.

Now that you have downloaded Fabric and the samples, you can start running Fabric.

## 2. Using the Fabric test network: 

Reference: https://hyperledger-fabric.readthedocs.io/en/latest/test_network.html



### 2.1 Run the example (Fabric test network)

Then you can run  the example. 

```Don't modify this example. Once modify, it doesn't work. Later you create your own network.```

You can find the scripts to bring up the network in the test-network directory of the fabric-samples repository. Navigate to the test network directory by using the following command:
```
Start your docker. If you use "Docker Desktop" just click its icon. 

cd fabric-samples/test-network # continue use same directory as above

./network.sh down # to make sure everything is down

It will print below or similar:
Kill one or more running containers

At this moment, check your containers in Docker Desktop, or check using "docker ps", you should see no related containers running.

./network.sh up # start up you network

At this moment, check your containers in Docker Desktop, or check using "docker ps", you should see 4 containers running.
```

Screenshot for 4 containers running:

![](img/example_network1.png)

![](img/example_network.png)
