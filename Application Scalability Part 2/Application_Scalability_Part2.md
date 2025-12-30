# Replication 

Replication means copying and keeping the same data or system in multiple places so that it stays available, reliable, and faster to access. making duplicate copies to ensure backup, availability, and fault tolerance.

---


## Data Replication

Data replication means copying the same data to multiple locations or servers.

- High availability
- Backup & fault tolerance
- Faster data access

**Example:** Database data copied from a primary server to replica servers.

![Logo](https://media.geeksforgeeks.org/wp-content/uploads/20251023184754625074/frame_3167.webp)


---

## Component Replication

Component replication means running multiple instances (copies) of the same software component or service.

- Load balancing
- High availability
- System reliability

**Example:** Multiple instances of a web server, API service, or microservice running at the same time.

![Logo](https://chatgpt.com/backend-api/estuary/content?id=file_00000000e07c7209a0423fff83bf7c8f&ts=490852&p=fs&cid=1&sig=94da3282492bdc240f46a3ffba56ac2da3858f80c2c85c5807b62808cbdec4db&v=0)


---


## Stateless

Stateless means the system does NOT remember previous requests.
Each request is independent.

### Example

- HTTP request
- REST API
- Public website

Every time the user sends a request, all data must be sent again.


## Stateful

Stateful means the system remembers previous interactions and stores user data/state.

### Example

- Login session
- Shopping cart
- Database connection

The system keeps user information between requests.



**Stateless**  no memory
**Stateful**  has memory

## Stateless VS Statefull

![Logo](https://miro.medium.com/v2/resize:fit:2000/format:webp/1*xYvS7mMWe-u3ehzm58O78A.png)


---

## Master Slave (Primary–Secondary)

Master Slave (Primary–Secondary) is a system architecture where one main node controls data, and other nodes copy and depend on it.

### Master / Primary

- Main server
- Handles writes (insert, update, delete)
- Source of truth

### Slave / Secondary

- Replica server(s)
- Copies data from the master
- Usually handles read operations
- Cannot write directly (in most setups)

### Why use it?

- High availability
- Load balancing (reads from slaves)
- Backup & fault tolerance

### Example (Database)

- Primary DB → writes data
- Secondary DB → reads data (replicated)

![Logo](https://media.geeksforgeeks.org/wp-content/uploads/20241113120736852523/master-slave-architecture.webp)


---

## Master-to-Master (Peer-to-Peer) Architecture

###  Overview
Master-to-Master Architecture (also known as Peer-to-Peer) is a system design where multiple servers act as masters simultaneously.  
Each server can read and write data, and changes are replicated among all nodes.


### How It Works
- All nodes have equal authority
- Data written on one master is replicated to other masters
- There is  single point of failure


### Advantages
- High Availability
- Load Balancing for both reads and writes
- Fault Tolerant (system continues working if one node fails)


### Challenges
- Data Conflicts (same data updated on multiple nodes)
- Complex Conflict Resolution
- Harder to manage and maintain



### Use Cases / Examples
- Distributed Databases
- Multi-region Systems
- Technologies:
  - Apache Cassandra
  - CouchDB
  - Multi-Master MySQL


### Summary
 In Master-to-Master architecture, every node is a master, and all nodes can read and write data. 
