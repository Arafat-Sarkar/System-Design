# System Reliability

System reliability is the ability of a system to consistently perform correctly and remain available over time, even when failures occur.

## Key Characteristics

#### Large number of components:
The system is made up of many independent components or services working together.

#### Large number of component instances:
Each component may run in multiple instances (replicas) to handle load and improve fault tolerance.

#### In short:
A reliable system keeps working correctly by managing many components and their multiple instances, even when some fail.

---

## Types of Failure

#### Partial failure:
Some parts of the system fail while others continue to work. The system is not completely down, but certain features may not respond correctly.

#### Independent failure:
One component or service fails without directly causing other components to fail. Other parts of the system continue operating normally.

#### Single point of failure:
A single component whose failure can bring down the entire system. If this component fails, the whole system stops working.

---

## Challenges in Large-Scale Distributed Systems

#### Increased chance of partial failure:
As the system grows, more services and instances are involved. This increases the likelihood that some components will fail at any time.

#### Cascading effects:
A failure in one service can spread to other dependent services, causing a chain reaction and impacting the whole system.

#### Identifying single points of failure:
It becomes difficult to detect components whose failure can bring down the entire system, especially in complex architectures.

#### Mitigation strategies:
Systems must use techniques like redundancy, retries, timeouts, circuit breakers, and monitoring to reduce the impact of failures.

---

## Reliability Engineering
Reliability Engineering is the discipline of designing, building, and maintaining systems to ensure they operate correctly and consistently over time, even in the presence of failures.

#### Key Points:
- Focuses on system availability, fault tolerance, and failure prevention.
- Uses techniques like redundancy, monitoring, testing, and recovery mechanisms.
- Aims to minimize downtime and ensure users can trust the system to work as expected.

---

## Reliability, Availability, and Fault Tolerance

### Reliability

#### Definition: 
The ability of a system to perform correctly and consistently over time.

#### Focus: 
Preventing failures and ensuring the system behaves as expected.

#### Example: 
A payment service processes transactions without errors for 99.99% of the time.

### Availability 
Measures how much a system is up and accessible to users.  
It tells us the reliability of a system from a user perspective.  

There are two common ways to measure it: Time-Based and Request-Based.


#### 1. Time-Based Availability 
The proportion of time a system is operational and available during a specific period.  

##### Formula:
Availability = (720 / (720 + 8)) × 100 ≈ 98.9%  


##### Example:  
- A server is up for 720 hours in a month and down for 8 hours.  



#### 2. Request-Based Availability
The proportion of successful requests served by a system out of the total requests received.

##### Formula:
Availability (Request-Based) = (Successful Requests / Total Requests) × 100%


##### Example:  
- A web service receives 10,000 requests in a day. 9,950 requests were successful. 

##### Summary:  
- Time-Based: Focuses on system uptime.  
- Request-Based: Focuses on user experience and success of requests.

---

## High Availability
Ensuring a system is up and accessible most of the time with minimal downtime.  

#### Types/Key Points:  
- Redundancy: Multiple instances of services/components.  
- Failover: Automatic switching to backup systems if one fails.  
- Load Balancing: Distributes traffic to avoid overloading a single resource.  

### Cost of Availability
The expense required to achieve a certain level of system availability.  

#### Key Points:  
- Higher availability → higher cost (more servers, backups, monitoring).  
- Balance between cost vs benefit is important.  

### Business Impact
How system availability affects business outcomes.  

#### Key Points:  
- High availability: Better customer satisfaction, uninterrupted service, higher revenue.  
- Low availability: Lost revenue, unhappy users, reputational damage. 

---

## The nines of availability


![Logo](https://www.globalcallforwarding.com/wp-content/uploads/2022/04/high-availability-chart.png)

---


## Fault Tolerance
Fault Tolerance is the ability of a system to continue functioning correctly even when some of its components fail. It ensures that failures do not cause the entire system to crash and minimizes downtime for users.

### Key Aspects of Fault Tolerance

#### Detect Partial Failures:
- Continuously monitor components to identify when a service, server, or module is failing or behaving abnormally.
- Use health checks, logging, alerts, and monitoring tools to detect issues early.

#### Handle Partial Failures:
- Prevent the failure from affecting other parts of the system.
- Techniques include isolation of services, retries, circuit breakers, and fallback mechanisms.
- Example: If a payment service fails, the system can temporarily route requests to a backup service.

#### Recover from Partial Failures:
- Restore the failed component or switch to a backup to resume normal operation.
- Includes automatic failover, redundancy, replication, and data recovery strategies.

---

## Designing Fault Tolerance
Designing Fault Tolerance involves building systems that keep running even when failures occur.

### Key Techniques

#### Redundancy / Replica:
Use multiple instances of components or services so that if one fails, others take over.

#### Fault Detection:
Continuously monitor components to detect failures early using health checks, alerts, or monitoring tools.

#### Recovery:
Restore failed components or switch to backups quickly to resume normal operation.

---

## Single Point of Failure (SPOF)
A Single Point of Failure is any component, service, or part of a system whose failure can bring down the entire system. If that component fails, the whole system becomes unavailable.

### Key Points

#### Critical Risk:
- SPOFs are high-risk points in the system because a failure there affects all users.
- Example: A single database server powering all services — if it fails, the application stops working.

#### Common SPOFs:
- Hardware: Single servers, switches, or routers.
- Software: Monolithic services with no backup.
- Network: Single network paths or gateways.
- Human dependency: Critical operators or processes handled by only one person.

#### Detection:
- Identify SPOFs by mapping system dependencies and asking: “If this fails, what stops working?”

#### Mitigation / Solutions:
- Redundancy: Add duplicate components (servers, databases, network paths).
- Failover mechanisms: Automatically switch to backup components if primary fails.
- Load balancing: Distribute traffic across multiple resources to avoid overloading one.
- Decoupling services: Reduce dependency on a single component wherever possible.

#### Impact:
- SPOFs can cause downtime, data loss, and business disruption.
- In large distributed systems, avoiding SPOFs is critical for reliability and high availability.

---

## Fault Tolerance Design
Designing a fault-tolerant system involves detecting, handling, and recovering from failures to keep the system running reliably.

### Fault Models

#### Response Failure:
The system gives an incorrect response instead of the correct one.

#### Timeout Failure:
The system does not respond within the expected time.

#### Incorrect Response Failure:
The system responds, but the data or result is wrong.

#### Crash Failure:
The component stops working completely and becomes unresponsive.

#### Arbitrary Response Failure (Byzantine Failure):
The system behaves unexpectedly or maliciously, giving random or inconsistent results.
