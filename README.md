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


The following are prerequisites for installing the required development tools:

Operating Systems: Ubuntu Linux 14.04 / 16.04 LTS (both 64-bit), or Mac OS 10.12
Docker Engine: Version 17.03 or higher
Docker-Compose: Version 1.8 or higher
Node: 8.9 or higher (note version 9 and higher is not supported)
npm: v5.x
git: 2.9.x or higher
Python: 2.7.x
A code editor of your choice, we recommend VSCode.

Problem:
Error while running npm install -g composer-cli

xcode-select --install # Install Command Line Tools if you haven't already.
sudo xcode-select --switch /Library/Developer/CommandLineTools # Enable command line tools

Solution:
https://github.com/nodejs/node-gyp/issues/569
