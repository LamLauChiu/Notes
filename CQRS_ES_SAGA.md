https://medium.com/@so3da/transactions-and-failover-using-saga-pattern-in-microservices-architecture-baf5a13111c9
Transactions and Failover using Saga Pattern in Microservices Architecture
Problem
Building distributed transaction across multiple services counted as very complex and tricky task as we have to consider many issues that may take place like dealing with service availability with transient states, eventual consistency between services, isolations, and rollbacks all these scenarios should be considered during the design phase carefully.

Solution: The Saga Pattern
A Saga is a sequence of transactions where each transaction interacts with its corresponding single service. The first transaction is initiated by an external request corresponding to the system operation, and then each subsequent step is triggered by the completion of the previous one and it contains the mechanism of handling rollback for the whole transaction sequence.

Using our previous example, in a helicopter view, a Saga implementation would look like the following:
![image](https://cdn-images-1.medium.com/max/1600/0*nG-NmhsfjVI3_ELX.png)

There are a couple of different ways to implement a saga transaction, but the two most popular are:

Command/Orchestration: There’s an orchestrator which responsible for centralizing the saga’s decision making and sequencing business logic.

Events/Choreography: There’s no coordination or orchestrator, each service integrates and listens to the other service’s events and decides if an action should be taken or not.

Command/Orchestration is my favorite one for these reasons:
Avoid messy dependencies between services, as the Saga orchestrator is the one who invokes the saga participants.
Reduce complexity as they only need to execute/reply commands.
Easier to be implemented and tested.
The transaction complexity remains linear when new steps are added.
Rollbacks are easier to manage.

Let’s dive more
In the orchestration approach, we’ll create a new service which will take the responsibility of telling each participant what to do and when. The saga orchestrator communicates with each service in a command/reply style telling them what operation should be performed and will take the responsibility of firing rollbacks if needed.

![image](https://cdn-images-1.medium.com/max/1600/0*kqSQuC_u41lhiAFp.png)
1.Order Service saves a pending order and asks Order Saga Orchestrator to start a create order transaction.
2.Orchestrator sends an execute payment command to Payment Service and wait for feedback on orchestrator queue channel.
3.Orchestrator sends a confirm booking command to Booking Service, and wait for feedback on orchestrator queue channel.
4.Orchestrator sends execute send a notification to Notification Service.
5.Orchestrator executes confirm the order in Order Service.
In the case above, Order Saga Orchestrator knows what is the flow needed to execute a “create order” transaction. If anything fails, it is also responsible for coordinating the rollback by sending commands to each participant to undo the previous operation.

Notice: We should move the operations which can’t be rollback to the last order in the transaction flow like Notifications/SMS as we can not revert this action if it has been executed.

Rolling Back in Saga’s Command/Orchestration
Rollbacks are a lot easier now, the Orchestrator should fire execute compensation/rollback event once needed for the corresponding services.

Example: If the booking has been failed by the supplier for any reason after we take money from the client for any reason, we should refund the money to the customer again.
![image](https://cdn-images-1.medium.com/max/1600/0*YHreR8wMr2YQ1kaS.png)
However, This approach still has some drawbacks, one of them is the risk of concentrating too much logic in the orchestrator and ending up with an architecture where the smart orchestrator tells dumb services what to do.

https://blog.bernd-ruecker.com/saga-how-to-implement-complex-business-transactions-without-two-phase-commit-e00aa41a1b1b
Saga: How to implement complex business transactions without two phase commit.

Concept of two-phase commit(2PC):
![iamge](https://ai2-s2-public.s3.amazonaws.com/figures/2017-08-08/2ee359fdeb0969a7be5e23141c5b0e9550ee6927/4-Figure1-1.png)

SQL:
https://medium.com/@totoroLiu/%E8%B3%87%E6%96%99%E5%BA%AB-acid-bb87324035a8
ACID
在資料庫的交易中，為確保交易(Transaction)是正確可靠的，所以必須具備四個特性，Atomicity (原子性）、Consistency (一致性）、Isolation (隔離性）、Durability (持續性）。在資料庫中，交易意旨由各種資料庫操作(select、update、insert等)所組成的邏輯過程。一般來說，我們會將Transaction寫在stored procedure中，以SQL server舉例，經常會看到 BEGIN TRANSACTION、COMMIT、 ROLLBACK等語法出現在stored procedure。

Atomicity (原子性）- 在資料庫的每一筆交易中只有兩種可能發生，第一種是全部完全(commit)，第二種是全部不完成(rollback)，不會因為某個環節出錯，而終止在那個環節，在出錯之後會恢復至交易之前的狀態，如同還沒執行此筆交易。

Consistency (一致性）- 在交易中會產生資料或者驗證狀態，然而當錯誤發生，所有已更改的資料或狀態將會恢復至交易之前。

Isolation (隔離性）- 資料庫允許多筆交易同時進行，交易進行時未完成的交易資料並不會被其他交易使用，直到此筆交易完成。

Durability (持續性）- 交易完成後對資料的修改是永久性的，資料不會因為系統重啟或錯誤而改變。

Index
Index Scan — 在查詢時，SQL server 會去尋找所有Index colume組成中是否符合查詢時的條件。執行消耗時間與Index總數成正比，與查詢結果的筆數無關。

Index Seek — 當查詢條件包含Index中的欄位，SQL server 會使用b-tree演算法尋找到match的資料。執行消耗時間與查詢結果筆數成正比。

Saga:
The Saga has the responsibility to either get the overall business transaction completed or to leave the system in a known termination state. 
So in case of errors a business rollback procedure is applied which occurs by calling compensation steps or activities in reverse order.

https://www.nexocode.com/blog/posts/smooth-implementation-cqrs-es-with-sping-boot-and-axon/
Smooth implementation of CQRS/ES with Spring Boot and Axon framework



https://www.nexocode.com/blog/posts/cqrs-and-event-sourcing/
CQRS and Event Sourcing as an antidote for problems with retrieving application states
![image](https://www.nexocode.com/blog/images/cqrs.jpg)

Commands represent user intent. They contain all the necessary information about actions that user would like to perform.

  Command Bus is a type of queue that receives commands and passes them to Command Handlers. <br/> <br/>
  Command Handlers contain actual business logic which validates and processes data received in commands. Command handlers are   responsible for generation and propagation of domain events to Event Bus <br/> <br/>
  Event Bus dispatches events to event handlers subscribed for specific event types. Event bus can propagate events both         asynchronously or synchronously if consecutive events are dependent. <br/> <br/>
  Event Handlers are responsible for handling specific incoming events. Their role is to save the new state of the application   in read repository, and perform terminal actions like sending emails, storing files etc. <br/> <br/>

Queries are objects, which represent the actual state of application available for a user. Getting data for UI should be done through these objects. 

We can distinguish many advantages of CQRS approach including the following:

We can split development tasks between people more experienced who will be working on the business logic and those ones who will be working on queries part. We have to be careful because this advantage may hurt knowledge transfer.<br/> <br/>
We can achieve a great read/write performance by scaling commands and queries on multiple different servers.<br/> <br/>
Using two different repositories (read/write) which are synchronized gives us automatic backup without any additional effort.
Reads don’t hit write database, so they can go faster when using Event Sourcing.<br/> <br/>
We can structure read data directly for the views, without thinking about domain logic, which simplifies views and can improve performance.


Event Sourcing - case study
At Nexocode we were trying to solve a problem of storing the previous states of the domain objects that influenced current state. Particularly, we were interested in generating statistics at any point of time. We wanted to check the state of our aggregate from the last month, last quarter or any other date from the past. The problem was not easy. We could keep additional data in the database for particular ranges of time, but there were also some drawbacks to this approach. We didn’t know how ranges should look like and what data would be necessary for future statistics. To avoid those problems, we could make snapshots all aggregates every day, but it produces a lot of redundant data.

Event Sourcing seems to be the best solution for that problems. Event sourcing allows us to keep every change of aggregate state as events in a repository called Event Store. Publishing event by command handler should finish with saving event in write DB (event store) and initiating logic handled by event handlers. To create the current state of aggregate we need to run all events which create expected domain object and perform all changes to it. Below schema should explain that idea in a clear way:

![image](https://www.nexocode.com/blog/images/event-sourcing.jpg)

We are able to specify some advantages of ES:

Time traveling. Possibility to recreate the state of specific aggregates in time. Every event contains a timestamp. It is not a problem to run events and stop them at a particular time based on these timestamps.<br/> <br/>
Natural audit. We can check who made a change and what was that change without any additional effort. Unlike system logs that can show changes history, events can tell the intent behind each change.<br/> <br/>
Ease of introducing corrects. When inconsistency appears in DB, we are able to reverse application state to a specific point in time, apply fixing event and further events.<br/> <br/>
Better debugging. If something goes wrong, we can prepare test environment and rebuild the state of application step by step from scratch by applying all events. Thanks to that, we can find the issue faster and in consequence, we can save a lot of time.

Aggregates
I used word aggregate many times in this article, but what does it mean? It is a concept that comes from Domain-Driven-Design (DDD) and it refers to the entity or group of related entities which are always kept in a consistent state. We can think of it as a box which accepts and handle commands (contains command handlers) and then generates events based on the current state (applying events on event bus). In our particular case aggregate root is composed of one domain object, but it can be composed of multiple objects. We have also to be aware that the whole application can consist of multiple aggregates and all events are stored up in one repository.

Conclusion
CQRS/ES can be a good alternative as a solution for specific problems. <br/>
It can be introduced in some parts of the standard n-layer app and it can resolve non-standard problems where not only the current state is important, but also in places where we have to know how current state was built. <br/>
Are CQRS and ES concepts that should exist together? <br/>
In fact, no. Write DB can store only the current state. It wasn’t the case in our application and introducing CQRS only didn’t resolve our problem. We’ve implemented CQRS/ES using Axon framework for resolving some specific problems of one of the domain objects, especially gathering statistics.

https://www.cnblogs.com/yangecnu/p/Introduction-CQRS.html
CRUD - Data-Driven
![image](https://images0.cnblogs.com/blog/94031/201408/261851413457170.png)

Problems:
使用同一個對象實體來進行數據庫讀寫可能會太粗糙，大多數情況下，比如編輯的時候可能只需要更新個別字段，但是卻需要將整個對象都穿進去，有些字段其實是不需要更新的。在查詢的時候在表現層可能只需要個別字段，但是需要查詢和返回整個實體對象。

使用同一實體對象對同一數據進行讀寫操作的時候，可能會遇到資源競爭的情況，經常要處理的鎖的問題，在寫入數據的時候，需要加鎖。讀取數據的時候需要判斷是否允許臟讀。這樣使得系統的邏輯性和複雜性增加，並且會對系統吞吐量的增長會產生影響。

同步的，直接與數據庫進行交互在大數據量同時訪問的情況下可能會影響性能和響應性，並且可能會產生性能瓶頸。
由於同一實體對象都會在讀寫操作中用到，所以對於安全和權限的管理會變得比較複雜。

這裡面很重要的一個問題是，系統中的讀寫頻率比，是偏向讀，還是偏向寫，就如同一般的數據結構在查找和修改上時間複雜度不一樣，在設計系統的結構時也需要考慮這樣的問題。

Solution:
解決方法就是我們經常用到的對數據庫進行讀寫分離。讓主數據庫處理事務性的增，刪，改操作（插入，更新，刪除）操作，讓從數據庫處理查詢操作（選擇操作），數據庫複製被用來將事務性操作導致的變更同步到集群中的從數據庫。這只是從DB角度處理了讀寫分離，但是從業務或者系統上面讀和寫仍然是存放在一起的。他們都是用的同一個實體對象。

CQRS
命令（指令）：不返回任何結果（無效），但會改變對象的狀態。
查詢（查詢）：返回結果，但是不會改變對象的狀態，對系統沒有副作用。
![iamge](https://images0.cnblogs.com/blog/94031/201408/261851418137013.png)
=>
![image](https://images0.cnblogs.com/blog/94031/201408/261851423609113.png)

主數據庫處理CUD，從庫處理R，從庫的的結構可以和主庫的結構完全一樣，也可以不一樣，從庫主要用來進行只讀的查詢操作。
在數量上從庫的個數也可以根據查詢的規模進行擴展，在業務邏輯上，也可以根據專題從主庫中劃分出不同的從庫。
從庫也可以實現成ReportingDatabase，根據查詢的業務需求，從主庫中抽取一些必要的數據生成一系列查詢報表來存儲。

![image](https://images0.cnblogs.com/blog/94031/201408/261851432666257.png)
使用ReportingDatabase的一些優點通常可以使得查詢變得更加簡單高效：
ReportingDatabase的結構和數據表會針對常用的查詢請求進行設計。
ReportingDatabase數據庫通常會去正規化，存儲一些冗餘而減少必要的加入等聯合查詢操作，使得查詢簡化和高效，一些在主數據庫中用不到的數據信息，在ReportingDatabase可以不用存儲。
可以對ReportingDatabase重構優化，而不用去改變操作數據庫。
對ReportingDatabase數據庫的查詢不會給操作數據庫帶來任何壓力。
可以針對不同的查詢請求建立不同的ReportingDatabase庫。
當然這也有一些缺點，比如從庫數據的更新。如果使用SQLServer的，本身也提供了一些如故障轉移和複製機制來方便部署。


什麼時候可以考慮CQRS:

CQRS模式有一些優點：

分工明確，可以負責不同的部分
將業務上的命令和查詢的職責分離能夠提高系統的性能，可擴展性和安全性。\並且在系統的演化中能夠保持高度的靈活性，能夠防止出現CRUD模式中，對查詢或者修改中的某一方進行改動，導致另一方出現問題的情況。
邏輯清晰，能夠看到系統中的那些行為或者操作導致了系統的狀態變化。
可以從數據驅動（Data-Driven）轉到任務驅動（Task-Driven）以及事件驅動（Event-Driven）。

在下場景中，可以考慮使用CQRS模式：

當在業務邏輯層有很多操作需要相同的實體或者對象進行操作的時候.CQRS使得我們可以對讀和寫定義不同的實體和方法，從而可以減少或者避免對某一方面的更改造成衝突
對於一些基於任務的用戶交互系統，通常這類系統會引導用戶通過一系列複雜的步驟和操作，通常會需要一些複雜的領域模型，並且整個團隊已經熟悉領域驅動設計技術。寫模型有很多和業務邏輯相關的命令操作的堆，輸入驗證，業務邏輯驗證來保證數據的一致性。讀模型沒有業務邏輯以及驗證堆，僅僅是返回DTO對象為視圖模型提供數據。讀模型最終和寫模型相一致。
適用於一些需要對查詢性能和寫入性能分開進行優化的系統，尤其是讀/寫比非常高的系統，橫向擴展是必須的。比如，在很多系統中讀操作的請求時遠大於寫操作。為適應這種場景，可以考慮將寫模型抽離出來單獨擴展，而將寫模型運行在一個或者少數幾個實例上。少量的寫模型實例能夠減少合併衝突發生的情況
適用於一些團隊中，一些有經驗的開發者可以關注複雜的領域模型，這些用到寫操作，而另一些經驗較少的開發者可以關注用戶界面上的讀模型。
對於系統在將來會隨著時間不段演化，有可能會包含不同版本的模型，或者業務規則經常變化的系統
需要和其他系統整合，特別是需要和事件溯源事件採購進行整合的系統，這樣子系統的臨時異常不會影響整個系統的其他部分。
但是在以下場景中，可能不適宜使用CQRS：

領域模型或者業務邏輯比較簡單，這種情況下使用CQRS會把系統搞複雜。
對於簡單的，CRUD模式的用戶界面以及與之相關的數據訪問操作已經足夠的話，沒必要使用CQRS，這些都是一個簡單的對數據進行增刪改查。
不適合在整個系統中到處使用該模式。在整個數據管理場景中的特定模塊中CQRS可能比較有用。但是在有些地方使用CQRS會增加系統不必要的複雜性。


CQRS與Event Sourcing的關係
在CQRS中，查詢方面，直接通過方法查詢數據庫，然後通過DTO將數據返回。
在操作（命令）方面，是通過發送命令實現，由CommandBus處理特定的命令，然後由司令部將特定的事件發布到EventBus上，然後EventBus使用特定的處理程序來處理事件，執行一些諸如，修改，刪除，更新等操作。這裡，所有與命令相關的操作都通過事件實現。這樣我們可以通過記錄事件來記錄系統的運行歷史記錄 ，並且能夠方便的回滾到某一歷史狀態.Event Sourcing就是用來進行存儲和管理事件的。

![image](https://www.codeproject.com/KB/architecture/555855/CQRS.jpg)
上圖很清晰的說明了CQRS在讀寫方面的分離，在讀方面，通過QueryFacade到數據庫裡去讀取數據，這個庫有可能是ReportingDB。在寫方面，比較複雜，操作通過命令發送到CommandBus上，然後特定的CommandHandler處理請求，產生對應的事件，將Eevnt持久化後，通過EventBus特定的EevntHandler對數據庫進行修改等操作。

![image](https://images0.cnblogs.com/blog/94031/201408/261851449547571.png)

