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

How to create a docker image from a container
https://www.scalyr.com/blog/create-docker-image/

Kubernetes (K8S)
is an open-source system for automating deployment, scaling and management of conatineried applications

K8S vocab:
Node - Kubelet, communicates with master, runs pods
Pod - Run 1+ containers, Exists on a node
Service - Handles requests, usually a load balancer
Deployment - Defines desired state, Kubernetes handles the rest


Jenkins:

Tutorial
https://www.youtube.com/watch?v=7q2YuDFhXrE&list=PL6tu16kXT9PqIe2b0BGul-cXbmwGt7Ihw&index=19

[ DevOps ] Jenkins 基本設定及 Pipeline 腳本教學
https://oranwind.org/-devops-jenkins-yu-centos-ubuntu-an-zhuang-jiao-xue/

Creating your first Pipeline
https://jenkins.io/doc/pipeline/tour/hello-world/

Build a Java app with Maven
https://jenkins.io/doc/tutorials/build-a-java-app-with-maven/#prerequisites

Bash Shell: Check File Exists or Not
https://www.cyberciti.biz/faq/unix-linux-test-existence-of-file-in-bash/

Get Docker CE for Ubuntu
https://docs.docker.com/install/linux/docker-ce/ubuntu/

Dockerizing a Spring Boot Application
https://www.baeldung.com/dockerizing-spring-boot-application

Quick Intro to Spring Cloud Configuration
https://www.baeldung.com/spring-cloud-configuration

spring cloud+docker+jenkins ( gardle )
https://my.oschina.net/weidedong/blog/1824736

***
Microservices Continuous Delivery with Docker and Jenkins
https://piotrminkowski.wordpress.com/2017/03/20/microservices-continuous-delivery-with-docker-and-jenkins/

Automated Deployment – Jenkins – Docker – Spring Boot
https://denisdbell.wordpress.com/2017/08/26/automated-deployment-jenkins-docker-spring-boot/

Spring Cloud DevOps之旅（二）Jenkins+Git+Docker搭建单机测试环境
https://www.jianshu.com/p/fa85be6164e4

Microservices and DevOps Using Java, Spring Boot, Git Flow, Jenkins, and Docker
https://dzone.com/articles/microservices-and-devops-1

Achieve CI/CD with Jenkins X, Kubernetes, and Spring Boot
https://developer.okta.com/blog/2018/07/11/ci-cd-spring-boot-jenkins-x-kubernetes
https://dzone.com/articles/achieve-cicd-with-jenkins-x-kubernetes-and-spring

Topic: What is the "The best automated deployment Tool/ Procedure"
Continuous Integration & Continuous Delivery (持續性整合與發佈)

https://blog.91app.com/continuous-integration-delivery/

https://www.amarinfotech.com/automated-deployment-tools.html


Solutions
Continuous Deployment to Kubernetes Engine using Jenkins

Introduction to Microservices, Docker, and Kubernetes
https://www.youtube.com/watch?v=1xo-0gCVhTU

