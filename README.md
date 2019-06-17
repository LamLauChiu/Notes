# Notes

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

Problem: <br/>
Error while running npm install -g composer-cli

xcode-select --install # Install Command Line Tools if you haven't already. <br/>
sudo xcode-select --switch /Library/Developer/CommandLineTools # Enable command line tools

Solution: <br/>
https://github.com/nodejs/node-gyp/issues/569
