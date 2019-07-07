### Different terminologies which are important for any software design and developement
----------------------------------------------------------------------------------------------------

In this article we would try to get familiar with different terminologies which possibly most of the developer or architect use in software design or implementations.

Here are few of them :

- ***`Frontend Vs Backend`*** [Ref](https://www.coursereport.com/blog/front-end-development-vs-back-end-development-where-to-start)=>
    - Any front end component of any application mostly UI layer.
    - Any backend component of any layer, could be database or service layer.
    - Technology stack would be different in each components.

- ***`Client Vs Server`*** [Ref](https://www.techopedia.com/definition/438/clientserver-architecture) =>
    - Standard architecture where client makes the request to server.
    
- ***`Program Vs Process`*** [Ref](https://www.guru99.com/program-vs-process-difference.html) =>
    - Program is a first step.
    - Program is in execution phase is called as process. 

- ***`Single Process Vs Multi Processes`*** [Ref](https://stackoverflow.com/questions/19156924/multi-process-vs-single-process-multi-threading-for-software-modules-commun) =>
    - It's process related concept.
    - Could be of one main thread of performing all set of operations or in another hand it could be multiple processes performing same job together. 

- ***`Synchronous Vs Asynchronous`*** [Ref](https://www.youtube.com/watch?v=BFcNDPt6SlE&list=PLjXnSLTXFtB8HzWDhUCFf4ttjiz5UhV_c&index=39&t=0s) =>    
    - Doing any operations synchronously.
    - Performing any operations in asynchronously. Could be any type of non-blocking call.    

- ***`Single Threading Vs Multi Threading`*** [Ref](https://medium.com/@bfortuner/python-multithreading-vs-multiprocessing-73072ce5600b)=>
    - Single thread most of the time gets referred by the main thread.
    - Spawning multiple threads from the main thread to perform one operations.

- ***`Multithreading Vs Multiprocessing`*** [Ref](https://dev.to/nbosco/multithreading-vs-multiprocessing-in-python--63j)=>
    - Multithreading to spin up different threads from the main thread.
    - Spawning multiple processes from the main process for performing same operations.

- ***`Standalone Vs Distributed`*** [Ref](https://www.freecodecamp.org/news/a-thorough-introduction-to-distributed-systems-3b91562c9b3c/)=>
    - Over the period time when we talk about distributed data processing platform then we can think of Hadoop Map/Reduce as an options.
    - But distributed concept also come in place for any application level as well, where some of the application would get only scalable based on 
        introducing more component in different components. 

- ***`Parallelism Vs Concurrency`*** [Ref](https://github.com/sughosneo/blogs/blob/master/concurrency_vs_parallelism.md)=>
    - Concurrency : When multiple tasks are performed in overlapping time periods with shared resources (potentially maximizing the resources utilization).
    - Parallelism : When single task is divided into multiple simple independent sub-tasks which can be performed simultaneously.

- ***`I/O bound Vs CPU bound`*** [Ref](https://stackoverflow.com/questions/868568/what-do-the-terms-cpu-bound-and-i-o-bound-mean)=>
    - I/O bound could be file system interactions or network interactions.
    - CPU bound could be how much is the machine logical core comes to the picture to performs any operations. 
    - Some operations are CPU extensive or some are I/O extensive based on that program gets written or executed.

- ***`Latency Vs Throughput`*** [Ref](https://www.comparitech.com/net-admin/latency-vs-throughput/)=>
    - Both the concepts are related.
    - It's basically based gets referred in terms of network bandwidth and how data gets traversed overthe wire.
    - Some of the time it also shows how one application or service is performing.

- ***`Scalable Vs Non Scalable`*** [Ref](https://www.youtube.com/watch?v=OyTEd9h_CVQ&list=PLjXnSLTXFtB8HzWDhUCFf4ttjiz5UhV_c&index=16&t=0s)=>
    - Platform which can be extended or scaled to compute heavy workload.
    - Non-scalable platform which can't handle more workload after certain limit.
    
- ***`Horizontal Vs Vertical Scaling`*** [Ref](https://www.youtube.com/watch?v=xpDnVSmNFX0)=>
    - Systems which can be scaled horizontally just adding few more servers. 
    - Vertical scaling could be adding more compute resources in single system.

- ***`Reliable Vs Unreliable`*** [Ref](https://www.inetdaemon.com/tutorials/basic_concepts/communication/reliable_vs_unreliable.shtml)=>
    - These concepts could be discussed based on the applications or communications between two applications point of view.     

- ***`Persistent Vs Non-Persistent`*** [Ref](https://devcentral.f5.com/s/articles/persistent-and-persistence-whats-the-difference)=>
    - These concepts can be discussed in terms of data or in terms of connections or any other many aspects.
    - For an example : a persistent connection can be reused many times but a non-persistent connection can be reinitialized everytime.

- ***`Stable Vs Unstable`*** [Ref](https://myclassbook.org/stable-unstable-system-stability-property/)=>
    - This is the system property where based on certain attributes it gets decided if its stable or non-stable.

- ***`Stateful Vs Stateless`*** [Ref](https://www.bizety.com/2018/08/21/stateful-vs-stateless-architecture-overview/)=>
    - It could be services.
    - It could be different applications.
    
- ***`Monolithic Vs Microservices`*** [Ref](https://myclassbook.org/stable-unstable-system-stability-property/)=>
    - It's standard traditional application design. 
    - Where microservices has become the most popular in recent past years.

- ***`Single Tier Vs Multi Tier`*** [Ref](https://www.softwaretestingmaterial.com/software-architecture/) =>
    - In one tier of application.
    - Multi tier of applications.

- ***`Local Vs Remote`*** [Ref](https://stackoverflow.com/questions/33781618/remote-procedure-calls-vs-local-procedure-calls) =>
    - It could be functional calls or component calls from one client app.
    - Local call would be specific to the a method calls or procedure call within same machine.
    - Remote call would be over the network. Calling any method through RPC.

- ***`RPC Vs gRPC`*** [Ref](https://www.hardikp.com/2018/07/28/services/)=>
    - Standard remote procedure call.
    - gRPC is RPC framework defined by Google.

- ***`SOAP Vs REST`*** [Ref](https://www.javatpoint.com/soap-vs-rest-web-services)=>
    - SOAP would be basically a protocol.
    - REST is an architectural style.

- ***`In-Proc Vs Out-Proc`*** =>
    - This is mainly to be a .NET programming concept, where session state runs on the same application server.    

- ***`Push Mechanism Vs Pull Mechanism`*** [Ref](https://simplicable.com/new/pull-vs-push-technology)=>
    - Pull mechanism is the traditional client server architecture where client fetches the information from server.
    - Push mechanism is the new approach where server pushes information to the client. 
    
- ***`Native Vs Cross platform`*** [Ref](https://www.zeolearn.com/magazine/native-vs-cross-platform-apps-youll-be-the-winner)=>
    - This actually descides how app could be designed or developed.
    

- ***`IaaS Vs Paas Vs Saas`*** [Ref](https://www.bmc.com/blogs/saas-vs-paas-vs-iaas-whats-the-difference-and-how-to-choose/) =>
    - All these 3 concepts related to the cloud computing. 

- ***`Single Tenant Vs Multitenant`*** [Ref](https://docs.microsoft.com/en-us/azure/sql-database/saas-tenancy-app-design-patterns)=>
    - Software design paradigm of supporting more than one tenant using one single platform.
    - It's popular design pattern where most of the cloud providers have achieved.

- ***`Batch/Archived Data Processing Vs Real Time Data Processing`*** [Ref](https://www.bmc.com/blogs/batch-processing-stream-processing-real-time/) =>
    - This concept is basically focused on the data.
    - Batch by batch processing from a data source where data has been archived.
    - Real time data processing on streaming data source.

- ***`SQL Databases Vs No-SQL Databases Vs Graph Databases`*** [Ref](https://neo4j.com/developer/graph-db-vs-nosql/)=>
    - RDBMS databases could be considered as sql databases.
    - mongoDB/Azure Document DB could be no-sql databases.
    - Orient DB graph databases.

- ***`Functional Vs Object Oriented`*** [Ref](https://medium.com/@sho.miyata.1/the-object-oriented-programming-vs-functional-programming-debate-in-a-beginner-friendly-nutshell-24fb6f8625cc) =>
    - Programming paradigm. 
    - Functional would be based on functions like - C
    - OOPs could be of C++,Java,Python etc.. But any object orient language can have also few of functional programming capabilities inbuilt in it. 
    
- ***`Overloading Vs Overriding`*** [Ref](https://data-flair.training/blogs/python-inheritance/)=>
    - It's generic concept but python3 has some exception to it.
    - But conceptually it definetly exist.

- ***`Waterfall Vs Agile`*** [Ref](https://www.guru99.com/waterfall-vs-agile.html)=>
    - This is software design and developement methodology.
    
- ***`Lazy Loading Vs Dynamic Loading`*** [Ref](https://www.geeksforgeeks.org/what-is-lazy-loading/)=>
    - Lazy loading (also called on-demand loading) is an optimization technique for the online content, be it a website or a web app.
    - All the programs are loaded in the main memeory for execution. Sometimes complete program is loaded into the memory, but some times a certain part or routine of the program is loaded into the main memory only when it is called by the program, this mechanism is called Dynamic Loading, this enhance the performance.
    
- ***`Containers Vs Virtual Machine`*** [Ref](https://blog.netapp.com/blogs/containers-vs-vms/)=>
    - ![Containsers Vs Virual Machines](./images/containers_vs_vm.png)
    
- ***`Unit Vs Functional Vs Integration Vs Regression Vs User Acceptance Testing`*** [Ref](https://www.softwaretestinghelp.com/types-of-software-testing/) =>
    - In software developement life cycle we follow different set of testing. Above are few important terminologies in that. 
    

    