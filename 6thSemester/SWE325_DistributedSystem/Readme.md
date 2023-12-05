<h1 align="center">Distributed System</h1>

**Book :**
- Distributed Systems - Concepts and Design

[✅**Book Link**][book]

[book]: https://drive.google.com/drive/folders/1x00yUHeRngC5BxOQlN53pUgrafEzKHbz?usp=sharing

**Resource :**
- System Models
- Communication : Direct, Indirect, Inter-process
- Distributed Shared Memory
- Transaction
- Synchronization
- Indexing, B+ Tree
- gRPC
- Hadoop

[✅**Resource Link**](https://drive.google.com/drive/folders/1s6RlQIp5dzxM6UYJKV7NJkkLQ7BmID6V?usp=sharing)

**⭐Useful Repository :⭐** 
- [System Design Primer](https://github.com/donnemartin/system-design-primer)
- [Free Programming Books](https://github.com/EbookFoundation/free-programming-books)

**TT & Previous Year Question :** [Exam.md](Exam.md)

<br><hr><hr><br>

<h2>Chapter 1 : Characteristics of Distributed System</h2>

- Heterogeneity
- Openness
- Security
- Scalability
- Concurrency
- Transparency
- Quality of Service

Case study : The World Wide Web (WWW)
<h2>Chapter 2 : System Model</h2>

- Physical
- Architectural
- Fundamental (*Interaction, Failure, Security*)

**Architectural Elements**
- **⭐Communication entities from programming perspective**
    - Objects
    - Components
    - Web services

- **⭐Communication paradigms**
    - Inter-process Communication (*such as socket programming*)
    - Remote Invocation (Request-Reply protocols, RPC, RMI)
    - Indirect Communication (groups, pub-sub, message queue, tuple spaces, distributed shared memory)

serialization, marshalling

<h2>Chapter 3 : Networking & Internetworking</h2>

<b>OSI Model : 7 layer
- Application : End user layer.. HTTP, FTP, SSH, DNS
- Presentation : Syntax layer.. SSL, SSH, IMAP, JPEG
- Session : Sync & send to port.. APIs, Sockets
- Transport : End-to-end connections.. TCP, UDP
- Network : Packets.. IP, ICMP, IGMP
- Data Link : Frames.. Ethernet, Switch, Bridge
- Physical : Physical structure.. Fiber, Hubs, Repeaters</b>

<h2>Chapter 4 : Inter-process Communication</h2>

**Socket Programming**
- used for writing program for transport layer
- socket.io
- Server Process : `socket() -> bind() -> listen() -> accept() -> read() -> write() -> close()`
- Client Process : `socket() -> connect() -> write() -> read() -> close()`
- input & output stream related to socket
- Connection in private network
- For private to public : Port Forwarding (**Tool : ngrok**)
- Uni, Bi directional
- Chat Application : i) Multiple Client and Server ii) Client to Client
- Multithreading, [Thread pool](https://www.javatpoint.com/java-thread-pool)
- webhook

<hr><hr><hr>

<h3>✅Communication✅</h3>

- Layered Protocol : OSI Model
- **⭐Remote Procedural Call (RPC)**
    - reducing the complexity of REST api
    - hiding details inside client, server stubs
    - steps of RPC
    - **Framework : gRPC**
        - What is gRPC? How it works?
        - How stubs are generated?
        - Why it uses protocol buffer?
        - What makes gRPC efficient? -> Multiplexing, Binary Framing, Server Push
        - How HTTP 2.0 works? HTTP/2 vs HTTP/1.1
        - 4 types of gRPC (Unary & Streaming : Client, Server, Bidirectional)
        - gRPC vs REST

- **⭐Remote Method Invocation (RMI)**
    - RMI vs RPC
- **⭐Message Oriented Communication**
    - Persistent vs Transient
    - Synchronous vs Asynchronous
    - Req ->, <- ack, <- reply
    - Transient Synchronous - receipt based, delivery based, response based
    - Message Oriented Transient Communication
        - Berkeley Socket
        - Message Passing Interface (MPI)
    - Message Oriented Persistent Communication
        - Message Queue
    - Socket is synchronous and transient
    - Promise() in Javascript is asynchronous and persistent
    - To make socket persistent - Message Queue : **RabbitMQ**
- **⭐Stream Oriented Communication**
    - Media types : Discrete, Continuous
    - Stream types : Simple, Complex, Substream
    - Resource Reservation Protocol (RSVP)
    - Stream Synchronization

<br><hr><br>
<h3>✅Indirect Communication✅</h3>

Space & Time -> Coupling, Uncoupling

**⭐Group Communication**
- Closed vs Open, Overlapping vs Non-overlapping, sync vs async groups
- Reliability in multicast, Ordered multicast
- Group membership management

**⭐Publish-Subscribe System**
- Characteristics -> Heterogeneity, Async
- Programming model -> un/publish, un/subscribe, notify, un/advertise
- Filter model -> Channel, Content, Topic, Type based
- Implementation -> Broker, Centralized, Distributed, Peer-to-peer
- Architecture of pub-sub system

**⭐Message Queues**
- Distributed Message Queue / Message Oriented Middleware(MOM)
- Point-to-point communication
- Programming mode -> Queue, Producer, Consumer, Types of receive : non/blocking, notify
- Queue system -> centralized or distributed
- Message Queueing Interface (MPI) -> MQCONN, MQDISC, MQPUT, MQGET

**⭐Shared Memory Approaches**
- **Distributed Shared Memory**
    - Read, update
    - avoids message passing
    - replicated on each node
- **Tuple Space Communication**
    - Tuples stored in shared tuple space, immutable
    - read, write(create new tuple), take(read & delete)
    - Read & Takes specified by pattern matching queries

<br><hr><br>
<h3>✅Distributed Shared Memory✅</h3>

**⭐Different nodes use shared memory through different buses/channels**
- Overhead - mapping manager
- Pros - high throughput, parallel access
- Data send via pointing, change ownership, thus transfer big amount of data
- Transmitting overhead reduced, Faster
- **Challenge** - concurrently keep data available

**⭐Different algorithm to manage it.** 
- **Central Server** 
    - manage resource access request via queue
    - sequence number, timeout
    - simple but bottleneck
- **Migration**
    - shift data to requesting node
    - one node accesses, no race condition
    - thrashing -> less work, more migration
    - so, set min time before migrating
- **Read Replication**
    - multiple read : safer, owner sends all copy
    - one write : invalidate or update all
- **Full Replication**
    - multiple read & write
    - gap free sequencer assigns sequence number to all nodes
    - issue : **Memory Coherence**
        - read should get latest value, locking needed when written
        - consistency : sequential, general, processor, weak, release
        - **Coherence protocol**
            - to ensure nodes have same info & do not access stale data
            - write-invalidate
            - write-update (more difficult to implement)

**⭐Case Studies**
- Cache coherence protocol (PLUS, MUNIN)
- General DSM (IVY - Integrated Shared Virtual Memory at Yale)

<br><hr><br>

<h3>✅Synchronization✅</h3>

**⭐Characteristics for Distributed Mutex Solution**
- No deadlock
- No starvation
- Fairness
- Fault tolerance

**⭐Distributed Mutex (mutual exclusion) Overview**
- **Permission based solution**
    - `Centralized`
        - no deadlock & starvation but fault tolerant
    - `Decentralized`
        - need permission from m > n / 2 coordinator
    - `Distributed`
        - Request, Processing Request, Enter Critical Section (if OK reply from other process) & Release
        - Timestamp lower -> priority higher `(3, 1) => time 3, process 1`
        - Internal queue of process. Voting to counter fault tolerance.
        - 2 (n - 1) message per critical section
        - Voting scheme modification via Retract, Relinquish message (prevents deadlock). Still O(N) algorithm.
- **Token based solution**
    - `Token Ring`
        - Processors on a bus network are arranged in a logical ring.
        - No starvation & deadlock, but lost token problem
        - Need to elect coordinator
        - Bully Algorithm -> O(n^2), Large message overhead. Take-Over by higher ID process. 
        - Ring Algorithm -> O(n). If next node is crashed, need to find next alive node.

<br><hr><br>

<h3>✅Transaction✅</h3>

Transaction is a unit of program execution that accesses and possibly updates various data items.

**⭐Required Properties of a Transaction : ACID**
- **Atomicity :** updates of partially executed transaction should not be reflected in database.
- **Consistency :** After successful transaction, database must be consistent
- **Isolation :** Transaction must be unaware of other concurrently running transactions
- **Durability :** After successful transaction, updates to the database must persist, even if there are failures

**⭐Transaction states**
- Active, Partially committed, Failed, Aborted, Committed

**⭐Schedule**
- sequences of instructions
- specify chronological order in which instructions of concurrent transactions are executed

**⭐Serializability**
- For a schedule to be serializable, it has to equivalent to a serial schedule
- Conflict Equivalent : S transformed into S` by a series of swaps of non-conflicting instructions
- Conflict Serializability via precedence graph

**⭐For Concurrency Control, all schedules must be:**
- Conflict Serializable
- Recoverable
- Cascadeless

<br><hr><br>
<h3>✅Indexing & B+ tree✅</h3>

- Pros & Cons
- Index evaluation : Access type & time, Insertion & deletion time, Space overhead
- Primary/clustering index, Secondary index
- Sparse & Dense index
- Multilevel index
- B+ tree properties
- Query, Insert & delete in B+ tree

<br><hr><br>
<h3>✅Hadoop✅</h3>

- HDFS (Distributed File System) -> NameNode, DataNode
- MapReduce (Map & Reduce) -> Jobtracker, Tasktracker : YT views count
- Count occurrences of given words using MapReduce
    - <img src = "https://drive.google.com/uc?id=16E1uLDLHBAK95B-_YC8qq99UogJ4e1VJ" alt = "Word occurrence count process via Hadoop" align = "center" width="70%">
- Latest Apache Spark