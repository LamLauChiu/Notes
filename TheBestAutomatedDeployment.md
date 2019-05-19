# This is the remarka about all the things during my study.

Pre-view:

Legacy application
https://searchitoperations.techtarget.com/definition/legacy-application


https://www.youtube.com/watch?v=1xo-0gCVhTU
Microservices:
- Separate busniness logic functions
- Instead of one big problem, several smaller applications
- Communicate via well defined APIs => usually HTTP
- In demand

Monolithic architecture vs Microservices:

![alt text](https://res.cloudinary.com/practicaldev/image/fetch/s--seen3BGm--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://user-images.githubusercontent.com/2697570/49395813-cd094980-f737-11e8-9e9a-6c20db5720c4.jpg)

Microservices advantanges:
- language independent
- fast itetations
- small teams
- fault isolation
- pair well with containers
- SCALABLE *

disadvantanges: 
- complex networking
- Overhead: databases, servers

Docker vs VM

Dockerfile
- describles the build process for an image
- can be run to automatically create an image
- contains all the commanda neccessary to build the image and run your application
![alt text](https://cdn-images-1.medium.com/max/2600/1*asSDJQpw1EQPFN-BqQSU0Q.png)


Conatiner orchestration - Deploying and scaling conatiners

Kubernetes (K8S)
is an open-source system for automating deployment, scaling and management of conatineried applications

K8S vocab:
Node - Kubelet, communicates with master, runs pods
Pod - Run 1+ containers, Exists on a node
Service - Handles requests, usually a load balancer
Deployment - Defines desired state, Kubernetes handles the rest

Topic: What is the "The best automated deployment Tool/ Procedure"
Continuous Integration & Continuous Delivery (持續性整合與發佈)

https://blog.91app.com/continuous-integration-delivery/

https://www.amarinfotech.com/automated-deployment-tools.html


Solutions
Continuous Deployment to Kubernetes Engine using Jenkins


Introduction to Microservices, Docker, and Kubernetes
https://www.youtube.com/watch?v=1xo-0gCVhTU

