Automated Deployment Tools - Jenkins

Jenkins is software that allows continuous integration (CI) by empowering teams to implement the technical part of a Continuous Delivery (CD). Jenkins can be used as a simple CI server or turned into the continuous delivery hub for any project. It is a server-based system running in a servlet container such as Apache Tomcat. It supports CVS, Subversion, Git, Mercurial, Perforce, Clearcase and RTC, and can execute Apache Ant, Apache Maven and sbt based projects as well as arbitrary shell scripts and Windows batch commands.Jenkins functionality can be extended with plugins.

![image](https://www.guru99.com/images/1/091318_0510_JenkinsPipe1.png)
The picture above represents a continuous delivery pipeline in Jenkins.

JenkinsFile
Jenkins pipelines can be defined using a text file called JenkinsFile. You can implement pipeline as code using JenkinsFile, and this can be defined by using a domain specific language (DSL). With JenkinsFile, you can write the steps needed for running a Jenkins pipeline.

Pipeline:
The pipeline is a set of instructions given in the form of code for continuous delivery and consists of instructions needed for the entire build process. With pipeline, you can build, test, and deliver the application.

Node:
The machine on which Jenkins runs is called a node. A node block is mainly used in scripted pipeline syntax.

Stage:
A stage block contains a series of steps in a pipeline. That is, the build, test, and deploy processes all come together in a stage. Generally, a stage block is used to visualize the Jenkins pipeline process.

Step:
A step is nothing but a single task that executes a specific process at a defined time. A pipeline involves a series of steps.

Jenkins Pipeline Tutorial: JenkinsFile EXAMPLE
https://www.guru99.com/jenkins-pipeline-tutorial.html

Setup Jenkins in CentOS/Ubuntu:
[ DevOps ] Jenkins 於 CentOS & Ubuntu 安裝教學
https://oranwind.org/-devops-jenkins-an-zhuang-jiao-xue/

What is Docker and how does it work?

What is Docker and why it is used?
Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. 
Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package.

What is Docker Architecture?
![iamge](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2016/10/Docker-Architecture-What-Is-Docker-Container-Edureka.png)
Docker Architecture includes a Docker client – used to trigger Docker commands, a Docker Host – running the Docker Daemon and a Docker Registry – storing Docker Images. The Docker Daemon running within Docker Host is responsible for the images and containers.

The contents of /var/lib/docker/, including images, containers, volumes, and networks, are preserved. The Docker CE package is now called docker-ce.

Dockerfile:
A Dockerfile is in principle, a linewise batch file, containing commands to build an image.

What is Docker Image?
Docker Image can be compared to a template which is used to create Docker Containers. They are the building blocks of a Docker Container.

What is Docker Container?
Containers are the ready applications created from Docker Images or you can say a Docker Container is a running instance of a Docker Image and they hold the entire package needed to run the application.

What is Docker Registry?
Docker Registry is where the Docker Images are stored. The Registry can be either a user’s local repository or a public repository like a Docker Hub allowing multiple users to collaborate in building an application. 

What is Volumes?
Volumes are the preferred way to persist data in Docker containers and services. Some use cases for volumes include: Sharing data among multiple running containers. If you don't explicitly create it, a volume is created the first time it is mounted into a container.

Get Docker CE for CentOS
https://docs.docker.com/install/linux/docker-ce/centos/
1 )Uninstall old versions

sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine

Dockerizing a Spring Boot Application
https://www.baeldung.com/dockerizing-spring-boot-application
What Is Docker & Docker Container ? A Deep Dive Into Docker !
https://www.edureka.co/blog/what-is-docker-container
Docker, Microservices and Continous Deleivery with Kenkins:
![image](https://dzone.com/storage/temp/4703327-docker-micro-1.png)
