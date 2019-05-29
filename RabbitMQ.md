# 

Concept

淺談I/O Model
-blocking
-non-blocking
-synchronous
-asynchronous

https://medium.com/@clu1022/%E6%B7%BA%E8%AB%87i-o-model-32da09c619e6
https://stackoverflow.com/questions/41227272/how-non-blocking-api-works

非同步程式設計和 non-blocking IO
https://medium.com/@fcamel/%E9%9D%9E%E5%90%8C%E6%AD%A5%E7%A8%8B%E5%BC%8F%E8%A8%AD%E8%A8%88%E5%92%8C-non-blocking-io-a43881081aac

How to install Latest RabbitMQ Server on Ubuntu 18.04 LTS
https://computingforgeeks.com/how-to-install-latest-rabbitmq-server-on-ubuntu-18-04-lts/


https://www.baeldung.com/spring-remoting-amqp
https://www.baeldung.com/rabbitmq
https://www.baeldung.com/spring-amqp-reactive

Spring remoting AMQP
https://molchanoff.me/software-development/spring-remoting-amqp/

RabbitMQ async consumption
https://wheleph.gitlab.io/2015/09/06/rabbitmq-async-consumption/

How to reset user for rabbitmq management
https://stackoverflow.com/questions/14699873/how-to-reset-user-for-rabbitmq-management


Docker install:

docker run -d --hostname rabbitMQ --name rabbitMQ -p 5672:5672 -p 15672:15672 -e RABBITMQ_VHOST=myvhost  -e RABBITMQ_DEFAULT_USER=admin -e RABBITMQ_DEFAULT_PASS=password rabbitmq:3-management

Example:
https://github.com/Gsantomaggio/rabbitmqexample/blob/master/cluster_docker_compose/cluster_conf/docker-compose.yml

io.reactivex.rxjava2:rxjava:
<dependency>
  <groupId>io.reactivex.rxjava2</groupId>
  <artifactId>rxjava</artifactId>
  <version>2.2.8</version>
</dependency>


https://medium.com/omarelgabrys-blog/microservices-with-spring-boot-intro-to-microservices-part-1-c0d24cd422c3




