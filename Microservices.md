# 


![alt text](https://developers.redhat.com/blog/wp-content/uploads/2016/12/365c0d94-eefa-11e5-90ad-9d74804ca412-21.png)
![alt text](https://developers.redhat.com/blog/wp-content/uploads/2016/12/screen-shot-2016-12-06-at-10-32-19.png)
https://developers.redhat.com/blog/2016/12/09/spring-cloud-for-microservices-compared-to-kubernetes/

![alt text](https://piotrminkowski.files.wordpress.com/2017/05/pvdi-microservices-architecture1.png?w=840)

RabbitMQ

Concept

https://cdn-images-1.medium.com/max/1600/1*pwheOTtJylSwXNctKif2Xw.png

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

Concept:RabbitMQ學習筆記
https://read01.com/d3k6.html#.XOZj2dMzbxo

Spring Boot RabbitMQ实践
https://my.oschina.net/u/3748347?tab=newest&catalogId=5740269
https://www.jianshu.com/p/86b8171e4be4
RabbitMQ学习笔记九：RabbitMQ实现RPC（远程过程调用）
https://blog.csdn.net/chenxyt/article/details/79280168

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

spring boot admin:

http://www.ityouknow.com/springboot/2018/02/11/spring-boot-admin.html

https://medium.com/omarelgabrys-blog/microservices-with-spring-boot-intro-to-microservices-part-1-c0d24cd422c3
RxJava学习指南
1. :https://www.zybuluo.com/cxm-2016/note/440764
9. :https://www.zybuluo.com/cxm-2016/note/574566

Reactor : Mono & Flux & rabbitMQ
https://projectreactor.io/docs/core/release/api/reactor/core/publisher/Mono.html#fromCallable-java.util.concurrent.Callable-

Reactor RabbitMQ Reference Guide
https://projectreactor.io/docs/rabbitmq/snapshot/reference/

https://projechttps://www.zybuluo.com/cxm-2016/note/574566treactor.io/docs/core/release/reference/index.html#_asynchronicity_to_the_rescue
https://www.ibm.com/developerworks/cn/java/j-cn-with-reactor-response-encode/index.html
https://projectreactor.io/docs/core/release/api/
https://projectreactor.io/docs/rabbitmq/release/api/

Net core microservices communication using RabbitMQ, Dapper & Docker
https://medium.com/@l.tambarin/net-core-microservices-communication-using-rabbitmq-dapper-docker-40353e40df1b
Asynchronous Microservices with RabbitMQ and Node.js
https://www.manifold.co/blog/asynchronous-microservices-with-rabbitmq-and-node-js
Using RabbitMQ for Microservices Communication on Docker
https://codeburst.io/using-rabbitmq-for-microservices-communication-on-docker-a43840401819

Hystrix
https://www.cnblogs.com/ityouknow/p/6868833.html

redis
https://segmentfault.com/a/1190000014091287
https://nickjanetakis.com/blog/docker-tip-27-setting-a-password-on-redis-without-a-custom-config

Axon
http://edisonxu.com/categories/Java/%E6%A1%86%E6%9E%B6/CQRS/Axon/
