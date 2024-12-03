+-------------------------------+---------------------------+----------+
| ![](vertopal_c6d81f           |                           |          |
| a9111f41158bd3f35728d2336f/me |                           |          |
| dia/image6.png){width="2.4in" |                           |          |
| h                             |                           |          |
| eight="0.5881944444444445in"} |                           |          |
|                               |                           |          |
| SCHOOL OF INFORMATION AND     |                           |          |
| TECHNOLOGY                    |                           |          |
+===============================+===========================+==========+
| NAME:                         | DATE PERFORMED:           | /50      |
|                               |                           |          |
| BARROGA, SHAIRA B.            | DECEMBER 3, 2024          |          |
|                               |                           |          |
| MERCADO, CASSIE KYM M.        |                           |          |
+-------------------------------+---------------------------+----------+
| Section: BSIT -- IDC2         | DATE SUBMITTED: DECEMBER  |          |
|                               | 3, 2024                   |          |
+-------------------------------+---------------------------+----------+

# SYSADM1 -- Capacity Management & Planning

**Part 2. Network Scalability Analysis**

Recall the e-commerce website scenario we discussed earlier. Given the
expected surge in traffic, analyze the provided network topology
diagram. Identify potential bottlenecks and areas where scalability
might be a concern. Propose specific strategies to improve the
network\'s scalability and performance to ensure a seamless user
experience during the peak traffic period. Consider factors such as
increased user demand, new applications, and security threats.

![](vertopal_c6d81fa9111f41158bd3f35728d2336f/media/image3.png){width="5.052917760279965in"
height="3.8255161854768156in"}

**Network Analysis**

**Potential Bottlenecks**

1.  **ISP Dependency**

> The network\'s connectivity is provided by a single ISP. The network
> as a whole will not have access to outside resources if the ISP goes
> down. The network is extremely susceptible to ISP interruptions due to
> this lack of redundancy.

2.  **Edge Router Vulnerability**

> During times of high traffic, the single edge router could get
> overloaded. All devices and services would experience a total loss of
> network connectivity in the event of its breakdown. As a result, the
> infrastructure develops a critical single point of failure.

3.  **Layer 3 Switch Limitation**

> If there is heavy traffic, the central Layer 3 switch may become a
> bottleneck. Communication between VLANs and linked servers would be
> disrupted in the event of this device failing. This makes it a
> critical dependency for the network\'s overall functionality.

4.  **Layer 2 Switches**

> For connectivity, each VLAN is dependent on an individual Layer 2
> switch. All of the devices in that VLAN would be unable to access the
> network if the switch malfunctioned or was overloaded. The likelihood
> of localized network disruptions is increased by this reliance on a
> single device.

5.  **Server Capacity**

> The network may not be able to manage a significant spike in traffic
> with just five servers. Due to limited processing and storage
> capacity, performance issues are likely to occur during times of high
> usage. The server configuration is not scalable enough to accommodate
> increasing needs.

**Security Risks**

**Lack of a Firewall**

> There is no firewall on the network to filter both inbound and
> outbound traffic. As a result, the infrastructure becomes vulnerable
> to external threats including malware, denial-of-service attacks, and
> unauthorized access. The network is significantly more susceptible to
> cyberattacks in the absence of this crucial security layer.

**Capacity Limitations**

1.  **Limited Server Resources**

> The current servers are unable to efficiently manage heavy traffic
> volumes. Due to resource exhaustion, the network may experience delays
> or interruptions during times of high demand. This restriction makes
> it more challenging for the system to function reliably when there
> exists significant traffic.

2.  **Scalability Limitations**

> Only two PCs can be connected to each server, which limits the
> network\'s capacity to grow. Due to this restriction, additional
> devices cannot be added. This lack of adaptability will cause
> operational issues as the company grows.

**Scalability Planning**

**Proposed Solutions**

1.  **Additional ISP**

> The addition of a secondary ISP offers redundancy and guarantees
> network connectivity in the event that the first ISP fails.

+-----------------------------------+-----------------------------------+
| **Benefits**                      | **Drawbacks**                     |
+===================================+===================================+
| -   Offers redundancy to          | -   Maintaining two ISP contracts |
|     > guarantee uninterrupted     |     > raises operating expenses.  |
|     > internet access in the      |                                   |
|     > event of an ISP outage.     | -   Increases network complexity  |
|                                   |     > by requiring extra          |
| -   Enhances network              |     > configuration for load      |
|     > dependability and lowers    |     > balancing or failover.      |
|     > the possibility of total    |                                   |
|     > outages.                    |                                   |
|                                   |                                   |
| -   Enhances performance during   |                                   |
|     > times of high traffic by    |                                   |
|     > supporting load balancing.  |                                   |
+-----------------------------------+-----------------------------------+

2.  **Backup Edge Router**

> The installation of a backup edge router guarantees continuity in the
> event that the primary router malfunctions.

+-----------------------------------+-----------------------------------+
| **Benefits**                      | **Drawbacks**                     |
+===================================+===================================+
| -   Increases fault tolerance by  | -   Increases the expense of      |
|     > guaranteeing that network   |     > buying and maintaining a    |
|     > connectivity is maintained  |     > second router.              |
|     > in the event that the       |                                   |
|     > primary router              | -   Makes network configuration   |
|     > malfunctions.               |     > more challenging and        |
|                                   |     > requires proper redundancy  |
| -   Allows load sharing, which    |     > configuration.              |
|     > lessens the strain on the   |                                   |
|     > main router when traffic is |                                   |
|     > heavy.                      |                                   |
|                                   |                                   |
| -   Increases the overall uptime  |                                   |
|     > and resilience of the       |                                   |
|     > network.                    |                                   |
+-----------------------------------+-----------------------------------+

3.  **Redundant Multilayer and Layer 2 Switches**

Using redundant Layer 2 and Layer 3 core switches enhances fault
tolerance and traffic distribution.

+-----------------------------------+-----------------------------------+
| **Benefits**                      | **Drawbacks**                     |
+===================================+===================================+
| -   Increases fault tolerance by  | -   Necessitates a large outlay   |
|     > guaranteeing continuous     |     > of funds for extra          |
|     > communication between       |     > hardware.                   |
|     > linked devices and VLANs.   |                                   |
|                                   | -   Makes setting up and          |
| -   Effectively manages increased |     > maintaining redundancy      |
|     > traffic loads by dividing   |     > techniques like link        |
|     > traffic over several        |     > aggregation and spanning    |
|     > routes.                     |     > trees more difficult.       |
|                                   |                                   |
| -   Lessens the effect of         |                                   |
|     > individual switch failures  |                                   |
|     > and improves network        |                                   |
|     > dependability.              |                                   |
+-----------------------------------+-----------------------------------+

4.  **Additional Layer 2 Switches in the Access Layer**

More devices can be connected to the network by adding extra Layer 2
switches at the access layer.

+-----------------------------------+-----------------------------------+
| **Benefits**                      | **Drawbacks**                     |
+===================================+===================================+
| -   Enhances scalability and      | -   Higher hardware expenses and  |
|     > future-proofs the           |     > more room is needed for the |
|     > infrastructure by making it |     > positioning of the switch.  |
|     > simpler to add new devices  |                                   |
|     > to the network.             | -   Additional configuration and  |
|                                   |     > cabling may be needed,      |
| -   Distributes device            |     > which would increase the    |
|     > connections over several    |     > deployment effort.          |
|     > switches, lowering the      |                                   |
|     > possibility of access layer |                                   |
|     > overload.                   |                                   |
|                                   |                                   |
| -   Balances traffic loads,       |                                   |
|     > improving network           |                                   |
|     > performance.                |                                   |
+-----------------------------------+-----------------------------------+

**Evaluation of Solutions**

Based on the traffic increase and system specifications, the following
scalability strategies are proposed to optimize the network's
performance, reliability, and security during peak hours:

1.  **Additional ISP**

> **Hardware Upgrade:** By adding a second ISP, we can provide network
> redundancy and assist distribute traffic load. This solution addresses
> the potential network failure due to ISP downtime, a critical
> vulnerability in the current infrastructure.
>
> **Software Configuration:** To guarantee continuous service during
> periods of high traffic, set up load balancing protocols and failover
> procedures between the two ISPs.
>
> **Network Optimization:** By dynamically modifying the load
> distribution between ISPs, bandwidth management with dual ISPs can be
> adjusted to prevent network congestion during the anticipated spike in
> traffic.

2.  **Backup Edge Router**

> **Hardware Upgrade:** By installing a backup edge router, network
> traffic will be redirected through the secondary device in the event
> that the original router fails, preventing complete connectivity loss.
>
> **Software Configuration:** To smoothly manage the active/standby
> roles of the routers, redundant routing protocols such as HSRP or VRRP
> should be put into place.
>
> **Network Optimization:** To prevent a single point of failure in the
> edge network, traffic load can be divided across the primary and
> backup routers.

3.  **Redundant Multilayer and Layer 2 Switches**

> **Hardware Upgrade:** Adding redundant Layer 2 and Layer 3 switches
> ensures fault tolerance and better traffic distribution across VLANs.
> This redundancy helps manage traffic surges by ensuring the network
> remains operational even during failures.
>
> **Software Configuration:** Implementing Spanning Tree Protocol (STP)
> for loop prevention and configuring link aggregation to increase
> bandwidth between switches would help in optimizing traffic handling.
>
> **Network Optimization:** The additional switches can handle growing
> traffic demands by distributing it across more devices, preventing
> bottlenecks in the network.

4.  **Additional Layer 2 Switches in the Access Layer**

> **Hardware Upgrade:** Better traffic distribution across VLANs and
> fault tolerance are ensured by adding redundant Layer 2 and Layer 3
> switches. By guaranteeing that the network continues to function even
> in the event of failures, this redundancy aids in the management of
> traffic surges.
>
> **Software Configuration:** To optimize traffic handling, link
> aggregation should be configured to maximize bandwidth between
> switches and Spanning Tree Protocol (STP) should be implemented for
> loop prevention.
>
> **Network Optimization:** By spreading traffic among more devices, the
> extra switches can manage increasing traffic demands and avoid network
> bottlenecks.

5.  **Additional Servers for VLAN Distribution**

> **Hardware Upgrade:** To better distribute workloads and handle
> anticipated traffic spikes, additional servers have been deployed to
> various VLANs. The following VLANs now include the servers:

-   **VLAN 1:** Web, Database, Load Balancer, Caching, Security,
    > Application, Email, File, DHCP, Backup

```{=html}
<!-- -->
```
-   **VLAN 2:** Web, Database, Load Balancer, DNS, File, Backup

-   **VLAN 3:** Web, Database, Load Balancer, Cloud, File, Backup

> **Software Configuration:** The new servers should be configured to
> optimize load balancing and ensure redundancy. This involves
> efficiently allocating services and traffic among the additional
> servers in every VLAN.
>
> **Network Optimization:** By adding extra servers, the network can
> manage heavier loads and guarantee that services are accessible even
> during periods of high traffic.

**Proposed Design\
**

**Network Diagram**

![](vertopal_c6d81fa9111f41158bd3f35728d2336f/media/image7.png){width="7.027083333333334in"
height="4.055555555555555in"}

**Network Design**

1.  **Core Layer**

> The Routers handle all routing, load balancing, and inter-VLAN
> routing.

2.  **Distribution Layer**

> The Layer 3 switches connect edge switches, ensuring efficient traffic
> distribution.

3.  **Access Layer**

> The Layer 2 switches provide end-device connectivity, including PCs,
> servers, and networked devices.

4.  **Security Layer**

> The network is secured with firewall systems deployed strategically.

5.  **Backup**

> Backup switches will provide redundancy, ensuring the availability of
> services in case of a failure

**Configuration Details**

1.  **Router**

> ![](vertopal_c6d81fa9111f41158bd3f35728d2336f/media/image2.png){width="3.676389982502187in"
> height="3.3031517935258092in"}

2.  **Layer 3
    > Switch**![](vertopal_c6d81fa9111f41158bd3f35728d2336f/media/image5.png){width="2.932292213473316in"
    > height="2.5915365266841643in"}

> ![](vertopal_c6d81fa9111f41158bd3f35728d2336f/media/image4.png){width="1.921875546806649in"
> height="4.49044728783902in"}

3.  **Layer 2 Switch**

> ![](vertopal_c6d81fa9111f41158bd3f35728d2336f/media/image1.png){width="3.9531255468066493in"
> height="6.223637357830271in"}

4.  **Firewall**

> ![](vertopal_c6d81fa9111f41158bd3f35728d2336f/media/image8.png){width="4.515625546806649in"
> height="3.951172353455818in"}

**Implementation**

1.  **Planning**

-   Before integrating the new topology, we must review the existing
    > network to understand the devices, connections, and configurations
    > used.

-   Identify critical systems that may be impacted by the changes and
    > ensure hardware compatibility with the new topology.

-   Confirm the IP addressing scheme and update the VLAN configuration
    > to avoid conflicts with existing VLANs, while planning IP address
    > ranges for the new VLANs.

-   Backup all current device configurations, including network
    > topology, IP addresses, NAT settings, and ACLs, to ensure a smooth
    > transition.

2.  **Hardware setup**

-   Ensure all the hardware required for the new topology is available
    > and configured with the necessary software versions.

-   Check for sufficient ports and capacity to support the topology.

-   Install and physically connect the Layer 3 switches, Layer 2
    > switches, and firewall devices to the network.

3.  **Device configuration**

-   Set up NAT/PAT for internal devices to communicate with the outside.

-   Configure NAT/PAT for internal traffic to go to the internet.

-   Apply static or dynamic routing as needed.

-   Configure ACLs for controlling inbound and outbound traffic.

-   Set up the VLANs for each department or function (Customer,
    > Management, Marketing).

-   Assign IP addresses to each VLAN interface (SVI) and enable routing
    > between them.

-   Configure HSRP (Hot Standby Router Protocol) for high availability
    > between Layer 3 switches.

-   Enable trunking between Layer 2 and Layer 3 switches.

-   Set up access ports for user devices and assign them to the
    > appropriate VLAN.

-   Configure port security to limit the number of MAC addresses per
    > port.

-   Enable trunking between Layer 2 and Layer 3 switches.

-   Set up the Firewall interfaces (inside and outside).

-   Create ACLs to allow specific traffic and deny unauthorized traffic.

-   Integrate the firewall with the Layer 3 switch and router for
    > security between internal and external networks.

4.  **Testing and validation**

-   Test the new devices in an isolated environment to ensure that they
    > function as expected.

-   Verify that Layer 3 switching and NAT/PAT work for internal devices.

-   Ensure the firewall rules are correctly blocking unauthorized
    > traffic and permitting authorized services.

-   Ensure routing between VLANs is operational.

-   Verify that trunking works properly.

-   Ensure that traffic flows smoothly between VLANs and that routing is
    > working as expected.

-   Verify that HSRP is functioning between the Layer 3 switches to
    > ensure redundancy.

-   Test internet access through the firewall and ensure NAT is working.

-   Test bandwidth utilization to ensure the network can handle peak
    > traffic without bottlenecks.

-   Validate latency and jitter to ensure minimal delay between devices
    > in the network.

-   Test firewall rules and ACLs to ensure that only authorized traffic
    > is allowed.

-   Perform penetration testing to verify that no security holes remain
    > after integrating the new topology.

-   Simulate a failover scenario to confirm that HSRP or another
    > redundancy mechanism works.

5.  **Monitoring**

-   Ensure all devices are properly connected to the new VLANs and can
    > access necessary services.

-   Monitor network traffic for any performance issues

-   Ensure NAT, firewall, and routing configurations are stable.

-   Assign a support team to troubleshoot and resolve any issues

-   Continuously monitor the network using network monitoring tools for
    > alerts on any disruptions.

**Evaluation and Justification**

The proposed solutions aim to address the network\'s scalability,
reliability, and security in the face of increased traffic during peak
periods. Below is a thorough evaluation of each proposed solution,
considering key factors such as cost, complexity, and potential impact.

1.  **Additional ISP**

> **Cost:** Higher operating costs will result from adding a second ISP
> because it will be required to pay for additional bandwidth and
> maintain two different contracts. Even though this can be quite
> costly, the improvement in network performance and dependability
> during periods of high traffic makes it desirable.
>
> **Complexity:** Setting up two ISPs complicates the network
> configuration, particularly when it comes to load balancing and
> failover procedures. Routing protocols (such BGP or OSPF) must be
> configured correctly and with seamless failover, which calls for
> thorough preparation and experience.
>
> **Potential Impact:** Adding a second ISP significantly improves the
> network\'s resilience and guarantees continuous service even in the
> event that one ISP goes down. The network can use load balancing to
> lessen congestion during periods of high traffic, which will enhance
> user experience and preserve service continuity.

2.  **Backup Edge Router**

> **Cost:** The purchase and maintenance of a backup edge router
> represent a moderate cost increase. Nonetheless, this expense is
> required to guarantee network continuity in the event of router
> failures, particularly during times of high demand when the likelihood
> of failure is raised.
>
> **Complexity:** Adding a second router adds further intricacy to the
> network architecture. This involves setting up failover management
> routing protocols like HSRP or VRRP and making sure traffic is
> appropriately split between the primary and backup routers.
>
> **Potential Impact:** By guaranteeing network connectivity even in the
> case of router failure, a backup edge router significantly improves
> fault tolerance. This lowers the possibility of a single point of
> failure, which is essential for preserving service availability, and
> guarantees little interruption during instances of high traffic.

3.  **Redundant Multilayer and Layer 2 Switches**

> **Cost:** The initial hardware investment required to enable redundant
> core switches is expensive. Costs are further increased by the
> continuous configuration and maintenance of these devices.
>
> **Complexity:** Configuring network protocols like STP (Spanning Tree
> Protocol), link aggregation, and even Virtual LANs (VLANs) adds
> complexity to the process of setting up redundant switches. Network
> professionals with the required abilities are needed to manage this
> redundancy and make sure it performs without loops or unwanted
> downtime.
>
> **Potential Impact:** Better fault tolerance and traffic distribution
> are offered by this system. Through the establishment of additional
> communication channels between devices and VLANs, the network can
> better manage higher traffic loads. Additionally, redundancy improves
> availability by reducing the possibility that a single switch failure
> may affect the network.

4.  **Additional Layer 2 Switches in the Access Layer**

> **Cost:** As it requires purchasing extra hardware as well as updating
> the wiring infrastructure, adding more Layer 2 switches at the access
> layer comes at a considerable cost.
>
> **Complexity:** The configuration of this solution becomes more
> complicated, particularly when it comes to load balancing among
> switches, link aggregation, and VLAN design. In contrast to other
> solutions, the complexity is manageable.
>
> **Potential Impact:** More devices can be supported and the traffic
> load can be distributed more equally across the access layer due to
> the additional switches. As the network expands, this scalability will
> be essential for avoiding congestion and possible access layer
> overloads, which could impair network performance as a whole.

5.  **Additional Servers for VLAN Distribution**

> **Cost:** It takes an initial substantial investment in both hardware
> and software configurations to add servers to each VLAN. These extra
> servers will also require continuing resource management and
> maintenance, which will cost funds.
>
> **Complexity:** Workload distribution, load balancing, and failover
> settings must all be carefully considered while configuring the new
> servers within each VLAN. To guarantee seamless functioning, proper
> integration with current systems is crucial.
>
> **Potential Impact:** The network\'s capacity to manage more traffic
> and offer fault tolerance inside each VLAN is enhanced by the
> additional servers. By distributing services like load balancing,
> database, and web hosting among several servers, it is possible to
> prevent any one server from becoming a bottleneck and enhance system
> performance even during periods of high traffic.

**Conclusion**

By incorporating these solutions, the current network\'s major
bottlenecks and scalability issues will be resolved. The network can
manage the anticipated peak traffic during the product launches and sale
events due to the suggested solutions. These solutions also greatly
improve network resilience, fault tolerance, and performance during
high-traffic hours.

  ------------------------------------------------------------------------------
  Criteria          Excellent \| 10pts Good \| 7pts        Needs Improvement \|
                                                           4pts
  ----------------- ------------------ ------------------- ---------------------
  **Network         Accurately         Identifies key      Identifies some basic
  Analysis**        identifies         network components  network components
                    potential          and some potential  but lacks a
                    bottlenecks,       bottlenecks.        comprehensive
                    security risks,                        analysis.
                    and capacity                           
                    limitations.                           

  **Scalability     Proposes multiple  Proposes some       Proposes limited
  Planning**        relevant solutions relevant            scalability
                    and provides       scalability         strategies.
                    detailed           strategies but      
                    explanations,      lacks detail.       
                    including                              
                    potential                              
                    drawbacks and                          
                    benefits.                              

  **Evaluation of   Proposes           Provides a basic    Does not evaluate the
  Solutions**       comprehensive      evaluation of the   proposed solutions or
                    scalability        proposed solutions, provides a
                    strategies,        but lacks depth.    superficial
                    including specific                     evaluation.
                    recommendations                        
                    for hardware                           
                    upgrades, software                     
                    configurations,                        
                    and network                            
                    optimizations.                         

  **Proposed        Provides a         Provides a basic    Does not provide a
  Design**          detailed and       design but lacks    clear and detailed
                    well-justified     specific details    design.
                    design, including  and justifications. 
                    network diagrams,                      
                    configuration                          
                    details, and                           
                    implementation                         
                    plans.                                 

  **Evaluation and  Provides a         Provides a basic    Does not evaluate the
  Justification**   thorough           evaluation of the   proposed solutions or
                    evaluation of the  proposed solutions, provides a
                    proposed           but lacks depth.    superficial
                    solutions,                             evaluation
                    considering                            
                    factors like cost,                     
                    complexity, and                        
                    potential impact.                      

  Score:                                                   /50
  ------------------------------------------------------------------------------
