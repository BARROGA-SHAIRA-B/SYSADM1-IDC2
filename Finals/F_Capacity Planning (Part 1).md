+----------------------------------+------------------------+----------+
| ![](vertopal_                    |                        |          |
| d00a2946151b4b999db4ff1698bdeafc |                        |          |
| /media/image1.png){width="2.4in" |                        |          |
| height="0.5881944444444445in"}   |                        |          |
|                                  |                        |          |
| SCHOOL OF INFORMATION AND        |                        |          |
| TECHNOLOGY                       |                        |          |
+==================================+========================+==========+
| NAME:                            | DATE PERFORMED:        | /50      |
|                                  |                        |          |
| BARROGA, SHAIRA B.               | NOVEMBER 28, 2024      |          |
|                                  |                        |          |
| MERCADO,CASSIE KYM M.            |                        |          |
+----------------------------------+------------------------+----------+
| Section:                         | DATE SUBMITTED:        |          |
|                                  |                        |          |
| BSIT - IDC2                      | NOVEMBER 28,2024       |          |
+----------------------------------+------------------------+----------+

# SYSADM1 -- Capacity Management & Planning

## Part 1. A Simulated Dataset for Capacity Planning Exercise

**Scenario:** A mid-sized e-commerce website is expecting a significant
surge in traffic due to an upcoming holiday
sale.![](vertopal_d00a2946151b4b999db4ff1698bdeafc/media/image2.png){width="4.749564741907261in"
height="2.4791666666666665in"}

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

+-----------+-----------+-----------+-----------+-----------+-----------+
| *         | **Pros**  | **Cons**  | **Cost**  | **Com     | **        |
| *Proposed |           |           |           | plexity** | Potential |
| S         |           |           |           |           | Impact on |
| olution** |           |           |           |           | System    |
|           |           |           |           |           | Perf      |
|           |           |           |           |           | ormance** |
+===========+===========+===========+===========+===========+===========+
| H         | Di        | Requires  | H         | Moderate  | This      |
| orizontal | stributes | a         | orizontal | to High,  | solution  |
| scaling,  | load      | dditional | scaling:  | as        | sign      |
| code      | evenly    | servers,  |           | imp       | ificantly |
| opti      | across    | i         | Ranges    | lementing | improves  |
| mization, | multiple  | ncreasing | from      | aut       | system    |
| and       | servers.  | op        | \$100 -   | o-scaling | pe        |
| enabling  |           | erational | \$1000    | and       | rformance |
| aut       | Prevents  | costs.    | per month | o         | by        |
| o-scaling | single    |           | depending | ptimizing | reducing  |
|           | server    | Aut       | on the    | code can  | the risk  |
|           | overload. | o-scaling | cloud     | be        | of CPU    |
|           |           | needs     | provider  | te        | bot       |
|           | Aut       | cloud     | (AWS,     | chnically | tlenecks, |
|           | o-scaling | infra     | Azure,    | complex.  | ma        |
|           | dy        | structure | Google    |           | intaining |
|           | namically | and       | Cloud)    |           | respo     |
|           | adjusts   | confi     | and the   |           | nsiveness |
|           | resources | guration. | number of |           | even      |
|           | based on  |           | a         |           | under     |
|           | traffic.  | Code      | dditional |           | high      |
|           |           | opt       | servers   |           | traffic,  |
|           | Improves  | imization | required. |           | and       |
|           | system    | requires  |           |           | ensuring  |
|           | re        | de        | Code      |           | high      |
|           | liability | velopment | opti      |           | avai      |
|           | and       | effort    | mization: |           | lability. |
|           | avai      | and time. |           |           |           |
|           | lability. |           | Typically |           |           |
|           |           |           | \$500 -   |           |           |
|           |           |           | \$5000    |           |           |
|           |           |           | depending |           |           |
|           |           |           | on the    |           |           |
|           |           |           | c         |           |           |
|           |           |           | omplexity |           |           |
|           |           |           | of the    |           |           |
|           |           |           | code and  |           |           |
|           |           |           | developer |           |           |
|           |           |           | rates.    |           |           |
|           |           |           |           |           |           |
|           |           |           | Auto      |           |           |
|           |           |           | -scaling: |           |           |
|           |           |           |           |           |           |
|           |           |           | \$200 -   |           |           |
|           |           |           | \$2000    |           |           |
|           |           |           | per month |           |           |
|           |           |           | depending |           |           |
|           |           |           | on the    |           |           |
|           |           |           | cloud     |           |           |
|           |           |           | infrastr  |           |           |
|           |           |           | ucture\'s |           |           |
|           |           |           | resources |           |           |
|           |           |           | and       |           |           |
|           |           |           | scaling   |           |           |
|           |           |           | req       |           |           |
|           |           |           | uirements |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| Implement | Caching   | Caching   | Database  | Moderate  | This      |
| caching,  | reduces   | requires  | query     | for       | solution  |
| optimize  | memory    | setup,    | opti      | caching;  | improves  |
| database  | usage by  | confi     | mization: | High for  | response  |
| queries,  | storing   | guration, |           | RAM       | times by  |
| and       | f         | and       | \$1000 -  | upgrades  | reducing  |
| upgrade   | requently | mai       | \$5000    | and       | memor     |
| RAM       | accessed  | ntenance. | for       | database  | y-related |
|           | data.     |           | c         | opti      | issues,   |
|           |           | RAM       | onsulting | mization. | ensuring  |
|           | Optimized | upgrades  | or        |           | smoother  |
|           | queries   | are       | de        |           | ap        |
|           | reduce    | hardware- | velopment |           | plication |
|           | memory    | dependent | work to   |           | per       |
|           | needed    | and can   | optimize  |           | formance, |
|           | for       | be        | queries.  |           | and       |
|           | p         | costly.   |           |           | enhancing |
|           | rocessing |           | RAM       |           | user      |
|           | data.     | Database  | upgrades: |           | ex        |
|           |           | query     |           |           | perience. |
|           | RAM       | opt       | For 32GB  |           |           |
|           | upgrades  | imization | of RAM    |           |           |
|           | provide   | requires  | per       |           |           |
|           | more      | expertise | server,   |           |           |
|           | resources | and time. | \$100 -   |           |           |
|           | for       |           | \$500 per |           |           |
|           | handling  |           | server.   |           |           |
|           | traffic.  |           | For 5     |           |           |
|           |           |           | servers,  |           |           |
|           |           |           | this can  |           |           |
|           |           |           | range     |           |           |
|           |           |           | from      |           |           |
|           |           |           | \$500 -   |           |           |
|           |           |           | \$2500    |           |           |
|           |           |           | depending |           |           |
|           |           |           | on server |           |           |
|           |           |           | specs and |           |           |
|           |           |           | hardware  |           |           |
|           |           |           | p         |           |           |
|           |           |           | roviders. |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| Compress  | Data      | Co        | Data      | Moderate  | This      |
| data,     | co        | mpression | com       | for       | solution  |
| optimize  | mpression | and API   | pression: | com       | greatly   |
| APIs, and | minimizes | opt       |           | pression, | improves  |
| upgrade   | bandwidth | imization | \$500 -   | High for  | data      |
| b         | usage.    | require   | \$3000 in | API       | transfer  |
| andwidth. |           | de        | initial   | opti      | speeds,   |
|           | API       | velopment | de        | mization. | reduces   |
|           | opt       | time.     | velopment |           | latency,  |
|           | imization |           | and       |           | and       |
|           | reduces   |           | in        |           | ensures   |
|           | data      |           | tegration |           | the       |
|           | transfer, |           | costs.    |           | system    |
|           | improving |           |           |           | can       |
|           | ef        |           | API       |           | handle    |
|           | ficiency. |           | opti      |           | increased |
|           |           |           | mization: |           | traffic   |
|           | Upgrading |           |           |           | without   |
|           | bandwidth |           | \$500 -   |           | network   |
|           | supports  |           | \$3000    |           | co        |
|           | higher    |           | for       |           | ngestion. |
|           | traffic   |           | de        |           |           |
|           | loads.    |           | velopment |           |           |
|           |           |           | time to   |           |           |
|           |           |           | optimize  |           |           |
|           |           |           | API       |           |           |
|           |           |           | calls.    |           |           |
|           |           |           |           |           |           |
|           |           |           | Bandwidth |           |           |
|           |           |           | upgrade:  |           |           |
|           |           |           |           |           |           |
|           |           |           | For       |           |           |
|           |           |           | upgrading |           |           |
|           |           |           | to 1Gbps  |           |           |
|           |           |           | or higher |           |           |
|           |           |           | b         |           |           |
|           |           |           | andwidth, |           |           |
|           |           |           | monthly   |           |           |
|           |           |           | costs     |           |           |
|           |           |           | could     |           |           |
|           |           |           | range     |           |           |
|           |           |           | from      |           |           |
|           |           |           | \$1000 -  |           |           |
|           |           |           | \$5000    |           |           |
|           |           |           | per month |           |           |
|           |           |           | depending |           |           |
|           |           |           | on the    |           |           |
|           |           |           | service   |           |           |
|           |           |           | provider  |           |           |
|           |           |           | and       |           |           |
|           |           |           | location. |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+
| Implement | Load      | Load      | Load      | Moderate  | This      |
| load      | balancing | balancing | b         | to High,  | solution  |
| b         | di        | requires  | alancers: | depending | enhances  |
| alancing, | stributes | conf      |           | on the    | system    |
| use       | traffic   | iguration | Cost: For | confi     | r         |
| asy       | evenly,   | and       | a         | gurations | esilience |
| nchronous | avoiding  | mo        | cl        | and the   | by        |
| pr        | server    | nitoring. | oud-based | system\'s | reducing  |
| ocessing, | overload. |           | load      | current   | latency   |
| and       |           | Asy       | balancing | arch      | and       |
| conduct   | Asy       | nchronous | service   | itecture. | ensuring  |
| stress    | nchronous | p         | (e.g.,    |           | smooth    |
| testing.  | p         | rocessing | AWS ELB), |           | handling  |
|           | rocessing | co        | it can    |           | of        |
|           | frees up  | mplicates | cost      |           | c         |
|           | resources | code and  | \$20 -    |           | oncurrent |
|           | for       | system    | \$500 per |           | user      |
|           | real-time | design.   | month,    |           | requests, |
|           | requests. |           | depending |           | leading   |
|           |           | Stress    | on the    |           | to better |
|           | Stress    | testing   | traffic   |           | pe        |
|           | testing   | requires  | and       |           | rformance |
|           | i         | dedicated | r         |           | under     |
|           | dentifies | r         | esources. |           | high      |
|           | system    | esources, |           |           | traffic   |
|           | w         | time, and | Asy       |           | co        |
|           | eaknesses | tools.    | nchronous |           | nditions. |
|           | before    |           | pr        |           |           |
|           | traffic   |           | ocessing: |           |           |
|           | peaks.    |           |           |           |           |
|           |           |           | De        |           |           |
|           |           |           | velopment |           |           |
|           |           |           | and setup |           |           |
|           |           |           | could     |           |           |
|           |           |           | cost      |           |           |
|           |           |           | between   |           |           |
|           |           |           | \$1000 -  |           |           |
|           |           |           | \$5000    |           |           |
|           |           |           | depending |           |           |
|           |           |           | on the    |           |           |
|           |           |           | c         |           |           |
|           |           |           | omplexity |           |           |
|           |           |           | and       |           |           |
|           |           |           | in        |           |           |
|           |           |           | tegration |           |           |
|           |           |           | needs.    |           |           |
|           |           |           |           |           |           |
|           |           |           | Stress    |           |           |
|           |           |           | testing:  |           |           |
|           |           |           |           |           |           |
|           |           |           | For using |           |           |
|           |           |           | tools     |           |           |
|           |           |           | like      |           |           |
|           |           |           | L         |           |           |
|           |           |           | oadRunner |           |           |
|           |           |           | or        |           |           |
|           |           |           | JMeter,   |           |           |
|           |           |           | stress    |           |           |
|           |           |           | testing   |           |           |
|           |           |           | can range |           |           |
|           |           |           | from      |           |           |
|           |           |           | \$500 -   |           |           |
|           |           |           | \$2000    |           |           |
|           |           |           | per month |           |           |
|           |           |           | for       |           |           |
|           |           |           | cl        |           |           |
|           |           |           | oud-based |           |           |
|           |           |           | testing   |           |           |
|           |           |           | envi      |           |           |
|           |           |           | ronments. |           |           |
+-----------+-----------+-----------+-----------+-----------+-----------+

Grading Rubric:

  -------------------------------------------------------------------------------
  Criteria           Excellent \| 10pts Good \| 7pts        Needs Improvement \|
                                                            4pts
  ------------------ ------------------ ------------------- ---------------------
  **Problem          Accurately         Identifies the main Identifies a problem
  Identification**   identifies the     problem and         but lacks clarity or
                     primary problem    provides a basic    accuracy.
                     and provides a     explanation.        
                     detailed                               
                     explanation.                           

  **Solution         Proposes multiple  Proposes one or two Proposes a solution
  Proposal**         relevant solutions relevant solutions  but lacks feasibility
                     and provides       but lacks detailed  or relevance.
                     detailed           explanation.        
                     explanations,                          
                     including                              
                     potential                              
                     drawbacks and                          
                     benefits.                              

  **Evaluation of    Provides a         Provides a basic    Does not evaluate the
  Solutions**        thorough           evaluation of the   proposed solutions or
                     evaluation of the  proposed solutions, provides a
                     proposed           but lacks depth.    superficial
                     solutions,                             evaluation.
                     considering                            
                     factors like cost,                     
                     complexity, and                        
                     potential impact.                      

  Score:                                                    /30
  -------------------------------------------------------------------------------
