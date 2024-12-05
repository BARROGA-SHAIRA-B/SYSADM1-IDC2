![image](https://github.com/user-attachments/assets/aa93197c-d605-448a-bbee-6be1ec710147)


# SYSADM1 -- Capacity Management & Planning

## Part 1. A Simulated Dataset for Capacity Planning Exercise

**Scenario:** A mid-sized e-commerce website is expecting a significant
surge in traffic due to an upcoming holiday
sale.
![image](https://github.com/user-attachments/assets/5e5aab21-34b8-42a6-ad88-6523499e4903)


### [Projected Traffic Increase]{.underline}

-   **Expected Peak Traffic:** 5x the normal peak traffic

-   **Peak Time:** 12:00 PM - 3:00 PM on the sale day

### [System Specifications]{.underline}

-   **Server Count:** 5

-   **CPU Cores per Server:** 8

-   **RAM per Server:** 32GB

-   **Network Bandwidth per Server:** 1Gbps

### [Additional Considerations]{.underline}

-   **New Product Launch:** A highly anticipated product will be
    > released during the sale.

-   **Marketing Campaign:** A major marketing campaign will be launched
    > to promote the sale.

-   **Potential Cyber Threats:** Increased traffic can attract malicious
    > actors.

Tasks:

1.  Review the provided server performance data and identify potential
    > bottlenecks

> The potential bottlenecks are the following:

A.  **CPU Utilization Bottleneck**

> According to the existing server configuration, CPU consumption rises
> noticeably at times of increased demand, suggesting that the servers\'
> processing capacity is almost at its limit. This implies that
> complicated processes like processing user queries, handling database
> requests, and managing background functions concurrently under a large
> traffic surge may be beyond the capabilities of the CPU. Particularly
> during high-concurrency events like a flash sale, the servers may
> encounter throttling if the load increases dramatically, which could
> lead to slower request handling and even crashes.

B.  **Memory Utilization Issue**

> Potential inefficiencies in the system\'s management of memory-based
> operations, including caching or database query handling, are
> indicated by the rising memory usage during peak periods. This can
> indicate a lack of efficient caching techniques or poorly optimized
> queries. Memory saturation brought on by increased traffic may force
> the system to use disk-based storage, which is slower and might result
> in lag in user experience and delays in data retrieval.

C.  **Network Bandwidth Limitations**

> The servers appear to be getting close to their bandwidth capacity
> during periods of high demand, based on the present network activity.
> A spike in traffic would probably overload the network, leading to
> slower data transfer speeds and interrupted service, especially when
> activities like streaming product photos or videos are involved.
> Additionally, this might affect server-to-server communication, which
> could negatively impact the functionality of distributed systems like
> databases or APIs that are essential for transactions and real-time
> data updates.

D.  **Response Time Degradation**

> A combination of CPU, memory, and network resource congestion is shown
> in the increased response times during periods of high activity. This
> suggests that the system has trouble effectively managing multiple
> requests at once, most often as a result of queue backlogs or conflict
> over shared resources like databases. Response delays may get worse
> with a large spike in traffic, which could result in timeout errors,
> abandoned transactions, and a general decline in client satisfaction.
> This emphasizes that in order to lower latency, both capacity increase
> and system optimization are required.

2.  Brainstorm possible solutions to address the identified bottlenecks.
    > Propose potential solutions considering hardware and
    > software-based solutions.

> Our solutions to address the identified problems are the following:

A.  **Horizontal Scaling, Code Optimization, and Auto-Scaling (Solution
    > for CPU Utilization Bottleneck)**

> To spread the load over an additional set of resources, use horizontal
> scaling by adding extra servers. Optimize database queries and
> application code to lessen the processing load on each server. As
> traffic spikes, more resources will be dynamically allocated if
> auto-scaling based on CPU thresholds is enabled.
>
> Justification: By distributing the workload across several servers,
> the burden on individual CPUs is lessened. Code optimization increases
> efficiency by ensuring that each operation consumes the least amount
> of processing power required. Auto-scaling guarantees sufficient
> resources during periods of high demand while avoiding
> overprovisioning during off-peak hours.

B.  **Caching Mechanisms and Upgrading Server RAM (Solution for Memory
    > Utilization Issue)**

> Programs like Redis or Memcached can store frequently requested data
> in memory to optimize caching methods. Review and improve database
> queries as well to cut down on memory usage. Upgrade server RAM or use
> memory-efficient programming techniques for long-term scalability.
>
> Justification: Caching speeds up response times and saves memory by
> reducing the need to frequently query the database. Optimized queries
> lower the amount of RAM needed to analyze data. Upgrading hardware
> guarantees that the system can manage heavy loads in extreme
> situations without depending on slower disk-based storage.

C.  **Improving APIs and Enhancing Network Bandwidth (Solution for
    > Network Bandwidth Limitations)**

> Improve APIs to minimize payload size and compress data to reduce
> bandwidth requirements. Additionally, enhance the network bandwidth
> capacity to handle the projected peak load.
>
> Justification: Optimized APIs and data compression reduce bandwidth
> usage. By expanding network bandwidth, the system can handle spikes in
> traffic without experiencing bottlenecks.

D.  **Load Balancing, Asynchronous Processing, and Stress Testing
    > (Solution for Response Time Degradation)**

> A load balancer can prioritize important tasks during periods of high
> traffic and divide traffic evenly among servers. Utilize asynchronous
> processing for non-essential operations to free up resources for user
> requests in real time. Furthermore, conduct stress testing to find and
> address system bottlenecks prior to the sale.
>
> Justification: By preventing any server from becoming overloaded, load
> balancing enhances response speeds in general. The system can
> prioritize urgent tasks while postponing less critical ones due to
> asynchronous processing. Stress testing finds and fixes weak points in
> the system in advance, preparing it to withstand anticipated demands.

3.  Discuss the pros and cons of each proposed solution by filling out
    > the table below.

![image](https://github.com/user-attachments/assets/7eba7404-88d5-4092-ba9d-7c3bc8804e9e)
![image](https://github.com/user-attachments/assets/8cf9ff6b-8363-42f2-b684-0d2dfc5b9333)
![image](https://github.com/user-attachments/assets/3cbb8e80-3d01-421d-adaa-6ba0cca7b4fc)




Grading Rubric:

 ![image](https://github.com/user-attachments/assets/0ecda830-4ace-4072-b764-bb0ed9337ca7)
