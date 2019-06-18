# Notes


![image](https://blockgeeks.com/wp-content/uploads/2017/05/hyperledgerfabricmodel.jpg)

![image](https://i.stack.imgur.com/zuGTC.png)


https://www.iterm2.com/

https://zhuanlan.zhihu.com/HiBlock

https://zhuanlan.zhihu.com/p/41605393
https://zhuanlan.zhihu.com/p/41769787
https://zhuanlan.zhihu.com/p/25383775


https://www.youtube.com/watch?v=TbPsou9ok7Y

https://www.youtube.com/watch?v=nS_MRqAeEbQ

https://www.youtube.com/watch?v=gAxK6zYrfxI&t=996s

https://www.youtube.com/watch?v=t5wZvmZGuAY

https://www.youtube.com/watch?v=fyYSBNXism0

https://www.youtube.com/watch?v=kMktpqo0FH8


https://medium.com/swlh/hyperledger-chapter-1-foundation-7ad5bd94d452

https://www.youtube.com/watch?v=c0tIdl2ePJ0

https://www.codementor.io/damcosset/getting-started-with-hyperledger-composer-and-private-blockchains-gsjuligf0

https://github.com/hyperledger/blockchain-explorer

Hyperledger Frameworks <br/>
1. Iroha- A simple and easy to incorporate into infrastructure projects requiring distributed ledger technology <br/>
2. Sawtooth- A modular blockchain framework that implements the PoET consensus algorithm <br/>
3. Fabric- Modular Blockchain with private channels <br/>
4. Indy — De-centralised Identity <br/>
5. Burrow — Smart Contract Machine <br/>

Hyperledger Modules: <br/> 
* Cello - toolkit to build Blockchain as a service revenue stream for a consulting company <br/>
* Explorer - To create something similar to etherscan or blockchaininfo. A tool to visualise transactions, blocks etc <br/>
* Composer - suite of tools for building blockchain business networks <br/>

The following are prerequisites for installing the required development tools:

Operating Systems: Ubuntu Linux 14.04 / 16.04 LTS (both 64-bit), or Mac OS 10.12 <br/>
Docker Engine: Version 17.03 or higher <br/>
Docker-Compose: Version 1.8 or higher <br/>
Node: 8.9 or higher (note version 9 and higher is not supported) <br/>
npm: v5.x <br/>
git: 2.9.x or higher <br/>
Python: 2.7.x <br/>
A code editor of your choice, we recommend VSCode.


Hyperledger Composer simplifies application development on top of the Hyperledger Fabric blockchain infrastructure.

If you are interested in the blockchain infrastructure, start with the Fabric tutorials.
https://hyperledger-fabric.readthedocs.io/en/latest/build_network.html#

If you are interested in blockchain applications, start with the Composer tutorials.
https://hyperledger.github.io/composer/latest/tutorials/tutorials.html

The Fabric tutorials also include samples of low level chaincode development (in golang). Composer is a higher level application development framework.

I'd suggest trying both to get an overall view of the capabilities.

As a Java developer, you will also want to check out the Fabric Java SDK for building Java client applications that interact with the blockchain. Java chaincode is also available as of Fabric v1.3.

Problem: <br/>
Error while running npm install -g composer-cli

xcode-select --install # Install Command Line Tools if you haven't already. <br/>
sudo xcode-select --switch /Library/Developer/CommandLineTools # Enable command line tools

Solution: <br/>
https://github.com/nodejs/node-gyp/issues/569
