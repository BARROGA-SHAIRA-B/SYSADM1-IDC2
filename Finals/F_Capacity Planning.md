![image](https://github.com/user-attachments/assets/2b29a3b8-5449-4465-be78-36a8e55d9790)


# SYSADM1 -- Capacity Management & Planning

**Part 2. Network Scalability Analysis**

Recall the e-commerce website scenario we discussed earlier. Given the
expected surge in traffic, analyze the provided network topology
diagram. Identify potential bottlenecks and areas where scalability
might be a concern. Propose specific strategies to improve the
network\'s scalability and performance to ensure a seamless user
experience during the peak traffic period. Consider factors such as
increased user demand, new applications, and security threats.

![image](https://github.com/user-attachments/assets/0e0c770a-ffd5-422d-b447-c720989ee597)


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

![image](https://github.com/user-attachments/assets/194c5fe5-0ea5-4144-a7b1-0188510770b3)


2.  **Backup Edge Router**

> The installation of a backup edge router guarantees continuity in the
> event that the primary router malfunctions.

![image](https://github.com/user-attachments/assets/f572fc6d-fd04-48bc-8845-6ed728b2b1bf)


3.  **Redundant Multilayer and Layer 2 Switches**

Using redundant Layer 2 and Layer 3 core switches enhances fault
tolerance and traffic distribution.

![image](https://github.com/user-attachments/assets/10b23038-5d05-4e56-9413-52d8c08d02c0)


4.  **Additional Layer 2 Switches in the Access Layer**

More devices can be connected to the network by adding extra Layer 2
switches at the access layer.

![image](https://github.com/user-attachments/assets/5ff0dcbd-e962-4929-9110-cdbc922daabb)


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

![image](https://github.com/user-attachments/assets/706c7c8a-4bfe-49c1-8f16-c0d41b4118b1)


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

![image](https://github.com/user-attachments/assets/e68d60e5-3b41-4721-b56d-92037e21eb57)


2.  **Layer 3

![image](https://github.com/user-attachments/assets/78e5834d-399b-46cd-b95c-4e37072db441)


3.  **Layer 2 Switch**

![image](https://github.com/user-attachments/assets/9a3442b4-f4cd-4628-abf5-48399a7dab70)


4.  **Firewall**

![image](https://github.com/user-attachments/assets/7e5a095a-a9f5-4e62-89b4-620a8aa8e1be)


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

![image](https://github.com/user-attachments/assets/23fff374-3092-4922-98ad-a1807805fbc5)
