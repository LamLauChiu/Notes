Java:
https://segmentfault.com/a/1190000020140435#articleHeader0

Interface:
https://www.javatpoint.com/interface-in-java

Why use Java interface?
There are mainly three reasons to use interface. They are given below.

1. It is used to achieve abstraction.
2. By interface, we can support the functionality of multiple inheritance.
3. It can be used to achieve loose coupling.

A class extends another class, an interface extends another interface, but a class implements an interface.
![alt text](https://static.javatpoint.com/images/core/interfacerelation.jpg)
![alt text](https://static.javatpoint.com/images/core/multipleinheritance.jpg)



DesignPattern
https://openhome.cc/Gossip/DesignPattern/

public void multiThreadsHandler(Request request) throws ExecutionException, InterruptedException {

	      CompletableFuture<String> ServiceOenResult = processRemoteServiceOne(request);
	      CompletableFuture<String> ServiceTwoResult = processRemoteServiceTwo(request);
	      CompletableFuture<String> ServiceThreeResult = processRemoteServiceThree(request);

	      log.info("ServiceOenResult --> {}" , ServiceOenResult());
	      log.info("ServiceTwoResult --> {}" , ServiceTwoResult());
	      log.info("ServiceThreeResult --> {}" , ServiceThreeResult());
    }



	public CompletableFuture<String>  processRemoteServiceOne(Request request) {
		log.info("processRemoteServiceOne - START");
		
		CompletableFuture<String> result = CompletableFuture.supplyAsync(()-> {
			try {
				 // simulate long running task
                Thread.sleep(5000);
                log.info("processRemoteServiceOne - PROCESS END");
			} catch(InterruptedException e) {
				 e.printStackTrace();
			}
			return "EFH";
		});
		log.info("processRemoteServiceOne - END");
		return result;
	}
