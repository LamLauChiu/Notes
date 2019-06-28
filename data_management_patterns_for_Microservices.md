Concepts:

http://edisonxu.com/2017/03/23/hello-cqrs.html <br/>
Domain Driven Design（DDD）

Aggregate

A DDD aggregate is a cluster of domain objects that can be treated as a single unit.
—— Martin Fowler

![image](http://edisonxu.com/images/2017/03/nG3Vc.png)

Event Sourcing and CORS ( Command Query Responsibility Segregation ) 
![image](http://edisonxu.com/images/2017/03/cqrs.png)

http://edisonxu.com/2017/03/30/hello-axon.html
AxonFramework
![image](http://edisonxu.com/images/2017/03/detailed-architecture-overview.png)

CommandGateway
send（command，CommandCallback）發送命令，根據執行結果調用CommandCallback中的onSuccess或onFailure方法
sendAndWait（command）發送完命令，等待執行完成並返回結果
sendAndWait（command，timeout，TimeUnit）這個好理解，比上面多了一個超時
send（命令）該方法返回一個CompletableFuture，不用等待命令的執行，立刻返回。結果通過future獲取。

![image](http://edisonxu.com/images/2017/03/flowchart.png)
-ReserveProductCommand (orderId, productId, number)
-RollbackReservationCommand (orderId, productId, number)
-ConfirmOrderCommand (orderId)
-RollbackOrderCommand (orderId)
-ProductReservedEvent (orderId, productId, number)
-ProductNotEnoughEvent (orderId, productId)
-OrderCancelledEvent (orderId)
-OrderConfirmedEvent (orderId)

DistributedCommandBus:
![image](http://edisonxu.com/images/2017/03/distributed-command-bus.png)

AMQP:
4type

Direct
![image](http://edisonxu.com/images/2017/04/direct_exchange.png)

Fanout
![image](http://edisonxu.com/images/2017/04/fanout_exchange.png)

topic
![image](http://edisonxu.com/images/2017/04/topic_exchange.png)

headers


SpringCloud & AxonFramework
![image](http://edisonxu.com/images/2017/04/lesson7_archi.png)

Docker setup:

docker run --name mysql \
  -p 3306:3306 \
  -v /Users/Ivan.lam/Projects/axon/mysql/db1/data:/var/lib/mysql \
  -e MYSQL_ROOT_PASSWORD=password \
  -d mysql

docker run -d -v /Users/Ivan.lam/Projects/axon/mysql/db1/data:/var/lib/mysql -v /Users/Ivan.lam/Projects/axon/mysql/db1/conf:/etc/mysql/conf.d --name mysql -e MYSQL_ROOT_PASSWORD=mysql123 -p 3306:3306 -d mysql:latest

docker run --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password -d mysql

docker run -p 27017:27017 -v /Users/Ivan.lam/Projects/axon/mogo/data:/data/db -d mongo:3.2

Setup rabbitMQ docker

docker run -d --hostname rabbitMQ --name rabbitMQ -p 5672:5672 -p 15672:15672 -e RABBITMQ_VHOST=myvhost -e RABBITMQ_DEFAULT_USER=admin -e RABBITMQ_DEFAULT_PASS=password rabbitmq:3-management



Spring Boot Microservices – Fastest Production Ready Microservices
http://progressivecoder.com/spring-boot-microservices-fastest-production-ready-microservices/

6 Data Management Patterns for Microservices
http://progressivecoder.com/6-data-management-patterns-for-microservices/

Implementing Event Sourcing using Axon and Spring Boot
http://progressivecoder.com/implementing-event-sourcing-using-axon-and-spring-boot-part-1/

Event Sourcing and CQRS with Axon and Spring Boot
http://progressivecoder.com/event-sourcing-and-cqrs-with-axon-and-spring-boot-part-1/

Saga Pattern Implementation with Axon and Spring Boot
http://progressivecoder.com/saga-pattern-implementation-with-axon-and-spring-boot-part-1/
