Server side:
<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-config</artifactId>
			<version>2.1.4.RELEASE</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
			<version>2.1.3.RELEASE</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
		
		<dependency>
        	<groupId>org.springframework.cloud</groupId>
        	<artifactId>spring-cloud-starter-eureka</artifactId>
        	<version>1.4.7.RELEASE</version>
	    </dependency>
	    <dependency>
	        <groupId>io.zipkin.java</groupId>
	        <artifactId>zipkin-server</artifactId>
	        <version>2.12.3</version>
	    </dependency>
	    <dependency>
	        <groupId>io.zipkin.java</groupId>
	        <artifactId>zipkin-autoconfigure-ui</artifactId>
	        <version>2.12.3</version>
	    </dependency>
      
@SpringBootApplication
@EnableDiscoveryClient
@EnableZipkinServer
public class ZipkinServerApplication {
...
}

eureka:
  client:
    serviceUrl:
      defaultZone: http://eureka1.com:8711/eureka,http://eureka2.com:8712/eureka
server:
  port: 9000
spring:
  application:
    name: zipkin-server
  zipkin:
    sender.type: web 
    base-url: http://:9000/
  sleuth:
    sampler.percentage: 1.0


#spring.zipkin.sender.type: web 
#spring.zipkin.base-url: http://:9000/
#spring.sleuth.sampler.percentage: 1.0
 
 
management:
  metrics:
    web:
      server:
        auto-time-requests: false

#spring.zipkin.sender.type: web 
#spring.zipkin.base-url: http://localhost:9000/
#spring.sleuth.sampler.percentage: 1.0



client side:
<dependency>
		    <groupId>org.springframework.cloud</groupId>
		    <artifactId>spring-cloud-starter-zipkin</artifactId>
		</dependency>
		<dependency>  
			 <groupId>org.springframework.cloud</groupId>  
			 <artifactId>spring-cloud-starter-sleuth</artifactId>  
		</dependency>
    
    
    
    spring.zipkin.base-url: http://localhost:9000/
spring.zipkin.sender.type: web
spring.sleuth.sampler.percentage: 1.0
